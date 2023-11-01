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

### Sensor Virtualization for Anomaly Detection of Turbo-Machinery Sensors—An Industrial Application

*Shetty, Sachin, Valentina Gori, Gianni Bagni, and Giacomo Veneri. 2023*

[Document](/documents/sachin2023.pdf)


We apply a Granger causality and auto-correlation analysis to train a recurrent neural network (RNN) that acts as a virtual sensor model. These models can be used to check the status of several hundreds of sensors during turbo-machinery units’ operation. Checking the health of each sensor is a time-consuming activity. Training a supervised algorithm is not feasible because we do not know all the failure modes that the sensors can undergo. We use a semi-supervised approach and train an RNN (LSTM) on non-anomalous data to build a virtual sensor using other sensors as regressors. We use the Granger causality test to identify the set of input sensors for a given target sensor. Moreover, we look at the auto-correlation function (ACF) to understand the temporal dependency in data. We then compare the predicted signal vs. the real one to raise (in case) an anomaly in real time. Results report 96% precision and 100% recall.

![algorithm](/images/sensor_anomalies.png)

{% highlight bibtex %}
@Article{engproc2023039096,
AUTHOR = {Shetty, Sachin and Gori, Valentina and Bagni, Gianni and Veneri, Giacomo},
TITLE = {Sensor Virtualization for Anomaly Detection of Turbo-Machinery Sensors&mdash;An Industrial Application},
JOURNAL = {Engineering Proceedings},
VOLUME = {39},
YEAR = {2023},
NUMBER = {1},
ARTICLE-NUMBER = {96},
URL = {https://www.mdpi.com/2673-4591/39/1/96},
ISSN = {2673-4591},
ABSTRACT = {We apply a Granger causality and auto-correlation analysis to train a recurrent neural network (RNN) that acts as a virtual sensor model. These models can be used to check the status of several hundreds of sensors during turbo-machinery units&rsquo; operation. Checking the health of each sensor is a time-consuming activity. Training a supervised algorithm is not feasible because we do not know all the failure modes that the sensors can undergo. We use a semi-supervised approach and train an RNN (LSTM) on non-anomalous data to build a virtual sensor using other sensors as regressors. We use the Granger causality test to identify the set of input sensors for a given target sensor. Moreover, we look at the auto-correlation function (ACF) to understand the temporal dependency in data. We then compare the predicted signal vs. the real one to raise (in case) an anomaly in real time. Results report 96% precision and 100% recall.},
DOI = {10.3390/engproc2023039096}
}
{% endhighlight %}

Also see anomalies definition from [Anomaly Detection Definition](https://jugsi.blogspot.com/2023/10/timeseries-anomaly-detection-definitions.html)

{% highlight bibtex %}
@book{veneri2018,
  title={Hands-on industrial Internet of Things: create a powerful industrial IoT infrastructure using industry 4.0},
  author={Veneri, Giacomo and Capasso, Antonio},
  year={2018},
  publisher={Packt Publishing Ltd}
}
{% endhighlight %}


## More
[Scholar](https://scholar.google.it/citations?user=B40SHWAAAAAJ&hl=it)