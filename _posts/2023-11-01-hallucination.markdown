---
layout: post
title:  "Hallucinations on LLM detection"
date:   2023-03-01 13:46:14 +0100
categories: code
---

In the context of LLMs, “hallucination” refers to a phenomenon where the model generates text that is incorrect, nonsensical, or not real. Bias refers to the bias learnt during training.

# Type of Hallucinations
* Factual Inaccuracies: The LLM produces a statement that is factually incorrect.

* Unsupported Claims: The LLM generates a response that has no basis in the input or context.

* Nonsensical Statements: The LLM produces a response that doesn’t make sense or is unrelated to the context.

* Improbable Scenarios: The LLM generates a response that describes an implausible or highly unlikely event.

# Measure Hallucinations
How to detect hallucination issue?

## Measure NER
Check if a new named entity (NE) is present in the text != from the ground truth.

Simple code:

{% highlight python %}

import nltk
from nltk.tokenize import word_tokenize
from nltk.tag import pos_tag

import nltk
nltk.download('averaged_perceptron_tagger')

def check_hallucination_by_NE(source_text, generated_text, verbose=False, pattern = 'NP: {<DT>?<JJ>*<NN>}', acceptable_ne=['NNP']):

    cp = nltk.RegexpParser(pattern)
    
    def ne(sent):
        sent = nltk.word_tokenize(sent)
        sent = nltk.pos_tag(sent)
        return cp.parse(sent)
    
    source_ne = ne(source_text)
    generated_ne = ne(generated_text)
    
    def filter_ne(ne_list):
        ret = []
        for _ne in ne_list:
            if (len(_ne) ==2) and (_ne[1] in acceptable_ne):
                ret.append(_ne[0])
                
        return ret
    
    source_ne = filter_ne(source_ne)
    generated_ne = filter_ne(generated_ne)
    
    if len(generated_ne)<=0:
        return -1
    
    score = 0
    for _ne in generated_ne:
        if (verbose):
            print(_ne)
        if _ne in source_ne:
            score +=1
    
    return score / len(generated_ne)
    

{% endhighlight %}


and now try it

{% highlight python %}
%time
check_hallucination_by_NE("President Biden was born USA", "President Biden was born France", verbose=True)
{% endhighlight %}