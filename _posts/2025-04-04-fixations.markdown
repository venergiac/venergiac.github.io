---
layout: post
title:  "Eye Fixations identification using ML"
date:   2025-04-04 00:00:00 +0100
categories: article
---

![fixations xgboost](fixations_xgboost.png)

Eye movements are an essential part of human vision as they drive the fovea and, consequently, visual attention toward a region of interest in the space. The fixations and saccades are the main features of eye movements; fixations are samples of points around a centre point (centroid) with long duration (≫50 ms); these eye fixations are intercalated by rapid eye jumps (saccade), which can be defined as rapid eye movement with velocities that may be higher than 500 deg/s and duration about 20–40 ms [veneri2011].

Eye fixation identification is the process of distinguishing periods when a person’s gaze is stationary, indicating focused attention on a specific point in the visual field. 

# Building Fixations identification based on XGBoost

XGBoost (eXtreme Gradient Boosting) è una libreria di machine learning open source che implementa un algoritmo di gradient boosting. È particolarmente noto per la sua velocità, efficienza e prestazioni, rendendolo una scelta popolare per la risoluzione di vari problemi di machine learning.

Since XGboost is not an algorithm that analyzes individual data points independently of the time sequence it is not suitable for this kind of problems, but with some tricks it is possible to make it “compatible”.

The trick is very simple, just add some additional columns that calculate some features in the neighborhood of the point x,y. Inspired by the CDT algorithm we added the variance in the neighborhood of 50 points and the difference with the previous 50 points. This operation, known as features engineering, adds information about the previous and next points.

The xgboost muste be trained before using it, we did it using a samples of 40 human gazes labeled manually. The model is available here https://github.com/venergiac/eye_fixation_identification .



To work with xgboost we can use the following line of code:

    import pandas as pd
    df = pd.read_csv("test.csv",sep=" ", names=["x","y","t","p"])
    xytp = df.values

    import xgbfix
    fix = xgbfix.extract_fixations(xytp[:,0],xytp[:,1], xytp[:,2])

The results is shown at the beginning of this page.

Github:
1. [github](https://github.com/venergiac/eye_fixation_identification)

