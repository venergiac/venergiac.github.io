---
layout: page
title: My Publications
permalink: /publication/
---

## 2023

### Combining Thermodynamics-based Model of the Centrifugal Compressors and Active Machine Learning for Enhanced Industrial Design Optimization

*Ghiasi, Shadi and Pazzi, Guido and Del Grosso, Concettina and De Magistris, Giovanni and Veneri, Giacomo*

[Document](/documents/ghiasi2023combining.pdf)

The design process of centrifugal compressors requires applying an optimization process which is computationally expensive due to complex analytical equations underlying the compressor's dynamical equations. Although the regression surrogate models could drastically reduce the computational cost of such a process, the major challenge is the scarcity of data for training the surrogate model. Aiming to strategically exploit the labeled samples, we propose the Active-CompDesign framework in which we combine a thermodynamics-based compressor model (i.e., our internal software for compressor design) and Gaussian Process-based surrogate model within a deployable Active Learning (AL) setting. We first conduct experiments in an offline setting and further, extend it to an online AL framework where a real-time interaction with the thermodynamics-based compressor's model allows the deployment in production. ActiveCompDesign shows a significant performance improvement in surrogate modeling by leveraging on uncertainty-based query function of samples within the AL framework with respect to the random selection of data points. Moreover, our framework in production has reduced the total computational time of compressor's design optimization to around 46% faster than relying on the internal thermodynamics-based simulator, achieving the same performance.

![algorithm](/images/algorithm.png)

![results](/images/results.png)


{% highlight bibtex %}
@inproceedings{ghiasi2023combining,
  title={Combining Thermodynamics-based Model of the Centrifugal Compressors and Active Machine Learning for Enhanced Industrial Design Optimization},
  author={Ghiasi, Shadi and Pazzi, Guido and Del Grosso, Concettina and De Magistris, Giovanni and Veneri, Giacomo},
  booktitle={1st Workshop on the Synergy of Scientific and Machine Learning Modeling@ ICML2023},
  year={2023}
}
{% endhighlight %}