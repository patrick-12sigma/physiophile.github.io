---
layout: post
title: Average Precision vs Average Recall
date: 2018-5-11
categories: [Deep Learning]
---

AR and AP are two metrics commonly used in object detection.

# Average Precision (AP)

AP is the average of precision at various recall positions. It can also be viewed as the AUC of the Precision-Recall curve. 

AP can be reported at a certain IoU threshold, or even further averaged over a number of IoU thresholds.

```
Average Precision (AP) @[ IoU=0.50 ]
```

or

```
Average Precision (AP) @[ IoU=0.50:0.95 ]
```

# Average Recall (AR)
First introduced in the paper [What makes for effective detection proposals?](https://arxiv.org/pdf/1502.05082.pdf), AR is a metric to evaluate how good a region (bbox) proposal network is. 

AR is the average of recall at various IoU thresholds (usually from 0.5 to 0.95). It can also be viewed as the AUC of the Recall-IoU curve. Despite similar names to AP, AR concerns only recall but not false positives. Therefore, adding a bbox that does not have any overlap with the groundtruth will not hurt AR. (Note that if recall at IoU = 0 is also calculated, AR will be hugely impacted.) There is no AR at a specific recall -- simply just use recal in that case.

```
Average Recall (AR) @[ IoU=0.50:0.95 ]
```
