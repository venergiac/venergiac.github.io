---
layout: post
title:  "Train LLAMA-2 on a Small GPU"
date:   2024-01-09 00:00:00 +0100
categories: code
---

Training a LLM model is hard without GPU but we can use LORA and QLORA 

4-bit quantization via QLoRA allows efficient finetuning of huge LLM models on consumer hardware while retaining high performance. This improves accessibility and usability for real-world applications.

QLoRA quantizes a pre-trained language model to 4 bits and freezes the parameters. A

During fine-tuning, gradients are backpropagated through the frozen 4-bit quantized model into only the Low-Rank Adapter layers. 

The 4-bit quantization does not hurt model performance.

## Quantization

In this post we use 4bit quantization



   pip install bitsandbytes

   ...

   quant_config = BitsAndBytesConfig(
		load_in_4bit=True,
		bnb_4bit_quant_type="nf4",
		bnb_4bit_compute_dtype=getattr(torch, "float16"),
		bnb_4bit_use_double_quant=False,
   )
   
   
   
## Training parameters

	pip install peft_params

	...

	peft_params = LoraConfig(
		lora_alpha=16,
		lora_dropout=0.1,
		r=64,
		bias="none",
		task_type="CAUSAL_LM",
	)
	
	
	training_params = TrainingArguments(
		output_dir="./results",
		num_train_epochs=1,
		per_device_train_batch_size=4,
		gradient_accumulation_steps=1,
		optim="paged_adamw_32bit",
		save_steps=25,
		logging_steps=25,
		learning_rate=2e-4,
		weight_decay=0.001,
		fp16=False,
		bf16=False,
		max_grad_norm=0.3,
		max_steps=-1,
		warmup_ratio=0.03,
		group_by_length=True,
		lr_scheduler_type="constant"
	)
	
	trainer = SFTTrainer(
		model=model,
		train_dataset=dataset,
		peft_config=peft_params,
		dataset_text_field="text",
		max_seq_length=None,
		tokenizer=tokenizer,
		args=training_params,
		packing=False,
	)
	
## Prepare Docker

Below how to configure the docker to run on RTX A3000

### Base Image
	FROM nvidia/cuda:12.1.1-base-ubuntu20.04

### Set environment variables
	

### Install system dependencies
	RUN apt-get update
	RUN apt-get install -y \
			git \
			python3-pip \
			python3-dev \
			python3-opencv \
			libglib2.0-0

### Install PyTorch and torchvision
	RUN pip3 install torch torchvision torchaudio -f https://download.pytorch.org/whl/cu121
		
### Install any python packages you need
	COPY requirements.txt requirements.txt
	RUN python3 -m pip install notebook accelerate peft bitsandbytes transformers trl tensorboard
   
## Full code 

full code is there

https://github.com/venergiac/training_LLAMA-2_QLORA

Buil docker:

    docker compose build
	
Start docker:

    docker compose run
	
Open the jupyter and check it with nvidia-smi.