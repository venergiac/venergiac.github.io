---
layout: post
title:  "Harnessing Generative AI for Interactive System Failure Diagnostics: A User-Centric Approach to Streamlined Problem Solving and Maintenance"
date:   2024-11-15 00:00:00 +0100
categories: code
---

Industrial machinery, including gas turbines and compressors, plays a critical role in driving key industries such as energy, fertilizer, and refineries. However, unplanned events can have far-reaching consequences, resulting in substantial production losses, increased emissions, and significant financial burdens. This work introduces a novel framework that leverages generative artificial intelligence for automated Root Cause Analysis (RCA) in turbomachinery. Facing the challenges of traditional RCA, which is expert-intensive and time-consuming, our work adopts a Large Language Model (LLMs) and information retrieval methods to translate natural language descriptions of failures into structured insights. A comprehensive knowledge base, populated with operational log data and expert- validated solutions, empowers the LLM to perform in-context learning and iterative diagnosis. By employing a hybrid search mechanism, our work identifies the most probable failure symptom and guides the user through a series of questions to pinpoint the root cause. Ultimately, the system generates a comprehensive troubleshooting report containing the root cause, mitigation strategies, and relevant references, enabling efficient and informed corrective actions. This approach promises to significantly reduce reliance on domain experts given the limited expertise available in the industry and address the entry-level gab, and improve the speed and accuracy of RCA, leading to enhanced operational efficiency and cost savings in industries reliant on high-performance turbomachinery.

* GenAI-driven Root Cause Analysis (RCA): uses LLMs to diagnose failures in industrial turbomachinery such as gas turbines and compressors.
* Large industrial knowledge base: grounds the diagnostic process on 30,000+ historical failure cases and expert-validated solutions.
* Hybrid retrieval + semantic clustering: embeddings and hierarchical clustering reduce the search space and organize similar failure scenarios into a decision-tree structure.
* Interactive diagnosis: the LLM dynamically generates Yes/No questions, using human feedback to progressively narrow possible failure modes and root causes.
* Actionable output: generates a structured troubleshooting report including root cause, mitigation actions, and references, aiming to reduce diagnosis time, expert dependency, downtime, and maintenance costs.

{% highlight bibtex %}
@inproceedings{vitale2024harnessing,
  title={Harnessing generative ai for interactive system failure diagnostics: A user-centric approach to streamlined problem solving and maintenance},
  author={Vitale, M and Youssef, A and Mishra, P and Shetty, S and Sharma, M and Vanzo, G and Veneri, G and Vieri, L and Bettini, A},
  booktitle={Abu Dhabi International Petroleum Exhibition and Conference},
  pages={D011S020R006},
  year={2024},
  organization={SPE}
}
{% endhighlight bibtex %}