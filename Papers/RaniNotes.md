# Recent Techniques of Clustering Time Series Data: A Survey: Notes

## Abstract: 

* Three types of ts clustering
	* raw data
	* feature based
	* model based
* We will summarize the state of the field as of 2012

## Introduction

> what is time series clustering?

Unsupervised classification of a set of unlabeled time series into groups or clusters, where each group is more or less homogeneous.
 
 Two types of clustering:
 * Shape level:
 	* Based on multiple time series
* Structural level:
	* Based on a single, very long time series 


## Major issues with time series clustering:

* High dimensionality
* Temporal order issues
* Noise

## Three types again:

1. Temporal-Proximity-Based Clustering:
	* Works directly on raw data, either in frequency or time domain
2. Representation-Based Clustering:
	* Works indirectly with features extracted from the raw data
3. Model-Based Clustering:
	* Works on the models built from the raw data (pretty wild)


## Making an effective model;

There are two techniques for making an effective time series clustering model:

1. Representation methods
	* Discrete Fourier Transform
	* Single Value Decompostion
	* Discrete Cosine Transformation
	* Discrete Wavelet Transformation
	* Piecewise Aggregation
	* etc.
	* There are a lot of these
	* These reduce the dimensionality of the series
2. Distance Measued
	* At least 12 of these
	* Cool things like DTW, ED, LCSS, DISSIM, SpADe etc.


# Temporal-Proximity Clustering

This useually works with raw data

* The big point of contention here is the distance/similarity measure for time series data


[Kumar](KumarSeasonalPatterns.pdf): Distance function based on independent models of data errors and clustered hierarchically, grouping time series into seasonal sequences with a good number of clusters. Data must be preprocessed to remove nonseasonal factors and nomralized.

[Liao(1)](Liao-TwoSteps.pdf): Two step procedure for clustering multivariate time series of equal or unequal or unequal length:
	1. k-means or fuzzy c-means(FCM) to time stripped data, in order to convert it into a univariate series with discrete values. The times are then added back in to the dataset, making it a time series again. 
	2. On the converted variable, employ k means or FCM to group the converted time series, expressed essentially as probability matrices into clusters. Euclidean distances are used in step one, where various distance measures are used in step 2

[Liao(2)](LiaoBattle.pdf) Evaluated several clustering algorithhms on multivariate time series, with the objective to form a discrete number of battle states (cool)

[Moller-Level](MollerFuzzyFuzzyShortTime.pdf) Proposes a new distance metric for short time series, using relative change in amplitude, to fuzzy cluster short unevenly sampled time series

[Shumway](ShumwayDiscriminant.pdf) Used locally stationary versions of probability divergence to give statistics for meaasuring the difference between non stationary time series. They were able to distinguish earthquakes from explosion using this methof combined with hierarchical clustering.


Niennatrakil showed that dynamic time warping is not a good tool in conjunction with k means, and instead K-mediods should be used.

[Bidari](BidariGenes.pdf) created a new approach to cluster time series gene expressions, finding funcitonal patterns of time series ising FCM and k-means clustering. Pearson correlation extracted expression patterns, and henes are clusterd by k means and FCM according to their time series expressions. Them, gene behavior patterns were extracted from their clusters.New features are then defined, and then by calculating correlation between the newly calculated features and found new interconnections between the genes.

[Kremer] Split time series into disjoint, equal length intervals and then density based clustering was used, with dynamic time warping, in order to detect the influence of climate change

[Yin] proposed an encoded-bitmap-apporach based swap on top of k means to improve classical time series clustering. He used time series of traffic flow data, refining the clusters with the swap trick. The proposed method was shown to perform better on the change trend of time series than simple k means.

[Hautamaki] defined a proripe as an optimization problem, and proposed a solution to it, using trandom swap and hierarchical clustering follwed by fine tuning with k means, provifing large imporvements over k mediods

[Chandrakala] proposed a density based method for clustering variabnle lenfth multivariate time series, ising the DBSCAN alforithm with euclidean distance. The proposed method performs very well and handles outliers well.

[nie] analyzed time series using normalized longest common subsequence, which is normally used in comparing text. He developed it with a new algorithm to calculate the similarity of time series It used the sum of all common subsequences instead of the longest common subsequence. The results lead to an improved performance overall

[khan] applied k means to stock data into three groups, sead, slow, and fast, and then applied the most frequent pattern algoiruthm to find frequencies of values of the corresponding item. It showed that this can generate useful patterns from large stock data

[Songpol] Intoduced resampled and hybrid DTW,  as well as Contrast Enhanced Dynamic Time Warping, that reduces the effects of single points.

[WU] propised a data stream clustering method for stocks, with online clustering first, and offline macro clustering. The online clustering extracted data dlow characteristics, while the bulk of the work was done offline. I do not quite understand this

[Zhang] used computational verb clustering in a few steps on stock data, in order to find intra day trends. First round of CVY cateforized the stock market data, and second round was computational verb k means, which refined the trends. This worked really well.

[Wu] introduced an algotihm that used stock information in conjunction with time series subsequences for mining patternse within stock sectors. He used stream sliding windows, a training window and an evaluation window. It detected significant sectors in the training window, and built patterns for the significant ones. It then used the evaluation window to detect whether the ppattern extracted was real or not. The patterns found were not bad at all, better than dbscan.

[Shi] Proposed an unascerained c means clustering which was more robust to noise than fuzzy c means

[Nanda] Found a way t use SOM and FCM to cluster and classify stocks, minimizing portfolio risks

![](https://i.imgur.com/7cVDBB2.png)

# Representation based clustering
