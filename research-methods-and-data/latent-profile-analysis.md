---
description: 'Seleeke Flingai January 15, 2019'
---

# Latent Profile Analysis

Clustering methods are useful to create subgroups of observations based on observable data. For example, housing submarkets can be revealed based on “clustered” characteristics shared by some neighborhoods and not by others 

* These submarkets can provide a useful lens to view our region
  * Neighborhoods from across the region can better grasp their similarities and differences 
  * The diversity of neighborhoods can be visualized 
  * Policies and programs can be targeted to address neighborhood needs more efficiently

### Latent Profile Analysis

Latent Profile Analysis \(LPA\) is a statistical classification technique that sorts individuals into unobserved, or “latent,” classes based on observed continuous variables. LPA is a useful procedure for describing relatively homogeneous subgroups within a larger heterogeneous population.[`[1]`](latent-profile-analysis.md#footnotes)

Latent profile analysis has many distinct advantages over traditional clustering analysis techniques \(see Wang and Hanges \(2011\) for extended discussion\). First, LPA is a probabilistic classification procedure, meaning that each individual’s probability of being a member of any given class is explicitly computed – as is the level of uncertainty. The probability of class membership is based on an individual’s values for the observed variables used in the analysis. By extension, any _additional_ individuals from the population not included in the initial analysis can be probabilistically assigned to a class based on its observed variables – a benefit not possible with many traditional clustering techniques. Secondly, variables on different scales do not need to be standardized or transformed prior to conducting LPA. Lastly, model fit criteria for LPA models are less arbitrary and more statistically rigorous than those of traditional cluster analysis, owing in part to the use of the maximum-likelihood method of estimating model parameters in LPA.[`[2]`](latent-profile-analysis.md#footnotes)

In this study we tested several different LPA models, each distinguished by the number of clusters assessed and the parameterization of the variance-covariance matrix. Starting with a one-class model and adding a latent class to each successive model, we estimated solutions for up to nine classes. All models were estimated with R version 3.5.0 software; R packages “mclust” version 5.4.3 and “tidyLPA” version 1.0.2 were used to conduct the analysis.

We then substantially reduced the number of possible profile solutions using model fit criteria and substantive considerations from internal stakeholders knowledgeable about regional housing dynamics. Ultimately, we chose the 7-class LPA solution with a class-invariant, diagonal variance-covariance matrix structure[`[3]`](latent-profile-analysis.md#footnotes) as the best LPA model.

#### Determining the number of classes

We examined nine model fit statistics to evaluate candidate profile solutions: Log likelihood \(LL\), Akaike’s Information Criterion \(AIC\), consistent AIC \(CAIC\), Bayesian Information Criterion \(BIC\), sample-size adjusted BIC \(SABIC\), Approximate Weight of Evidence Criterion \(AWE\), entropy, and the bootstrap likelihood ratio test \(BLRT\). Model fit criteria for LPA and other finite mixture models are extensively discussed in articles by Masyn[`[4]`](latent-profile-analysis.md#footnotes)and Nylund, Asparouhov, and Muthén.[`[5]`](latent-profile-analysis.md#footnotes) Generally, the optimal LPA model has lower values of AIC, CAIC, BIC, SABIC, and AWE relative to other candidate models; a higher value of entropy compared to other candidate models; and a statistically significant BLRT \(p &lt; 0.05\). Parsimony \(i.e. choosing fewer rather than a greater numbers of classes\) and substantive considerations \(i.e. theory and/or subject matter expertise\) should be used to choose the best model when comparing candidate solutions with similar model fit statistics and differing numbers of classes.

Model fit criteria were calculated for models of 1 to 9 classes across four variance-covariance parameterizations: class-invariant, diagonal \(hereafter referred to as model parameterization A\); class-varying, diagonal \(B\); class-invariant, unrestricted \(C\); and class-varying, unrestricted \(D\). For model parameterizations B and D, the models failed to converge after 4 and 3 classes, respectively, for all model fit criteria. Based on internal stakeholder conversations, these 4- and 3- class models failed to adequately represent the diversity of housing submarkets in the region and were therefore dropped from further analysis. For model parameterizations A and C, the models converged for all tested class sizes, but model fit failed to demonstrably improve after 7 classes. Therefore, the 7-class class-invariant, diagonal \(A\) and 7-class class-invariant, unrestricted \(C\) models were chosen as the top two candidate LPA models based on fit criteria. After additional internal stakeholder discussions, the 7-class class-invariant, diagonal \(A\) model was ultimately selected as the most representative submarket clustering model of all candidate LPA solutions.

### Footnotes

`1.` Masyn, K. E. \(2013\). Latent class analysis and finite mixture modeling. In T. D. Little \(Ed.\), Oxford library of psychology. The Oxford handbook of quantitative methods: Statistical analysis \(pp. 551-611\). New York, NY, US: Oxford University Press.

`2.` Wang, W., and Hanges, P. J. \(2011\). Latent class procedures: Applications to organizational research. Organizational Research Methods 14\(1\):24-31.

`3.` Wang, W., and Hanges, P. J. \(2011\). Latent class procedures: Applications to organizational research. Organizational Research Methods 14\(1\):24-31. Variances for a given variable do not vary across classes, and covariances are assumed to be 0 Ibid. 

`4.` Ibid.

`5.` Nylund, K. L., Asparouhov, T., and Muthén, B. O. \(2007\). Deciding on the number of classes in latent class analysis and growth mixture modeling: A Monte Carlo simulation study. Structural Equation Modeling 14\(4\):535-569.

### LPA Summary Statistics 

**Table 1.** Descriptive Statistics

| Variable | Mean | Std Dev | Min | Max |
| :--- | :--- | :--- | :--- | :--- |
| Housing Unit Density \(units per square mile\) | 5,265.6 | 7,206.5 | 88.2 | 59,345.5 |
| Median Household Income \($\) | 89,968.3 | 37,650.2 | 16,094 | 228,438 |
| Households with Income 0-35K \(%\) | 23.4 | 12.9 | 2.6 | 74.9 |
| Households with Income 35-75K \(%\) | 22.7 | 7.5 | 5.4 | 45.5 |
| Households with Income 75-100K \(%\) | 11.4 | 4.2 | 1.5 | 23.2 |
| Households with Income 100K + \(%\) | 42.5 | 17.3 | 4.8 | 81.7 |
| Households with Income 150K+ \(%\) | 24.8 | 15.2 | 0 | 68.7 |
| Median Contract Rent \($\) | 1,301.9 | 476.1 | 0 | 3,297 |
| Median Home Value \($\) | 560,761.9 | 240,372.7 | 147,000 | 1,899,000 |
| Renter-Occupied Housing Units \(%\) | 42.7 | 24.2 | 1.8 | 98.1 |
| Residential Sales Purchased by Business Buyers \(%\) | 13.3 | 10.1 | 0 | 80 |
| Residential Foreclosure Activity \(%\) | 2.6 | 3.2 | 0 | 20 |
| Cash Sales \(%\) | 22.7 | 10.7 | 0 | 83.3 |
| Change in Residential Home Sales from 2003-2007 to 2012-2016 \(%\) | -11.1 | 18.6 | -66.3 | 117.9 |
| Vacant Units \(%\) | 6.1 | 4.1 | 0 | 29.4 |
| HUD Subsidized Housing Units \(%\) | 2.7 | 6.4 | 0 | 54.6 |
| Three-Bedroom Units \(%\) | 51.2 | 21.6 | 1.9 | 95.8 |
| Units Built 1959 or Earlier \(%\) | 58 | 21.2 | 4 | 95.6 |
| Units Built 1960-1999 \(%\) | 33.4 | 18 | 3.3 | 88.5 |
| Units Built 2000 or Later \(%\) | 8.6 | 8.3 | 0 | 55 |
| 1 Unit \(%\) | 47.7 | 30 | 0 | 100 |
| 2-4 Units \(%\) | 25.9 | 21.8 | 0 | 87.6 |
| 5+ Units \(%\) | 26.1 | 22.8 | 0 | 99.2 |
| Change in Median Home Value \(%\) | 48.6 | 48.4 | -43.8 | 753.8 |
| Change in Median Contract Rent \(%\) | 18.8 | 39.3 | -100 | 421.2 |
| Change in Renters \(%\) | 3.4 | 43.4 | -85.6 | 634.2 |
| Change in Population \(%\) | 9.7 | 16.8 | -22 | 166.4 |
| Change Housing Unit Density \(%\) | 43.8 | 129.1 | -32.1 | 1,652.2 |

\*\*\*\*

**Table 2**. Summary of submarket characteristics – model-based medians for each submarket \(Latent Profile Analysis\)

| Variable | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Housing Unit Density \(units per square mile\) |  16,076 |  8,040 |  6,512 |  1,475 |  1,176 |  1,188 |  16,076 |
| Median Household Income \($\) |  91,964 |  39,183 |  70,264 |  85,481 |  155,551 |  80,024 |  91,964 |
| Households with Income 0-35K \(%\) |  22.7 |  45.9 |  24.9 |  19.3 |  11.8 |  22.0 |  22.7 |
| Households with Income 35-75K \(%\) |  19.1 |  27.3 |  27.0 |  24.5 |  11.8 |  25.3 |  19.1 |
| Households with Income 75-100K \(%\) |  10.2 |  7.5 |  12.5 |  13.1 |  7.9 |  13.8 |  10.2 |
| Households with Income 100K + \(%\) |  47.1 |  16.6 |  35.1 |  41.9 |  69.0 |  37.6 |  47.1 |
| Households with Income 150K+ \(%\) |  30.8 |  6.8 |  14.6 |  21.5 |  51.6 |  19.9 |  30.8 |
| Median Contract Rent \($\) |  1,882 |  990 |  1,269 |  1,164 |  1,667 |  1,406 |  1,882 |
| Median Home Value \($\) |  810,000 |  416,926 |  534,625 |  430,000 |  942,000 |  363,500 |  810,000 |
| Renter-Occupied Housing Units \(%\) |  65.5 |  77.3 |  56.7 |  28.8 |  17.9 |  42.4 |  65.5 |
| Residential Sales Purchased by Business Buyers \(%\) |  16.4 |  17.6 |  14.6 |  10.0 |  14.5 |  8.6 |  16.4 |
| Residential Foreclosure Activity \(%\) |  - |  2.6 |  1.6 |  2.1 |  - |  3.0 |  - |
| Cash Sales \(%\) |  37.9 |  27.3 |  19.6 |  19.6 |  20.2 |  22.2 |  37.9 |
| Change in Residential Home Sales from 2003-2007 to 2012-2016 \(%\) |  \(22.7\) |  \(30.9\) |  \(18.5\) |  \(6.0\) |  1.6 |  \(12.7\) |  \(22.7\) |
| Vacant Units \(%\) |  8.5 |  6.6 |  6.2 |  4.8 |  4.8 |  4.7 |  8.5 |
| HUD Subsidized Housing Units \(%\) |  1.3 |  7.7 |  - |  - |  - |  - |  1.3 |
| Three-Bedroom Units \(%\) |  16.9 |  30.2 |  42.0 |  59.3 |  78.1 |  47.1 |  78.0 |
| Units Built 1959 or Earlier \(%\) |  64.2 |  57.0 |  75.9 |  62.2 |  69.8 |  32.9 |  33.1 |
| Units Built 1960-1999 \(%\) |  27.7 |  34.8 |  18.6 |  30.4 |  22.8 |  53.7 |  53.5 |
| Units Built 2000 or Later \(%\) |  3.9 |  8.3 |  3.9 |  4.7 |  7.7 |  14.8 |  10.3 |
| 1 Unit \(%\) |  6.3 |  12.8 |  24.1 |  66.6 |  79.8 |  51.1 |  86.4 |
| 2-4 Units \(%\) |  19.2 |  30.3 |  53.9 |  15.9 |  9.8 |  9.6 |  3.4 |
| 5+ Units \(%\) |  70.0 |  49.2 |  20.1 |  15.4 |  7.9 |  37.5 |  7.2 |
| Change in Median Home Value \(%\) |  75.0 |  65.4 |  57.3 |  31.3 |  38.7 |  24.5 |  15.6 |
| Change in Median Contract Rent \(%\) |  27.2 |  14.4 |  24.2 |  9.7 |  11.8 |  18.3 |  13.5 |
| Change in Renters \(%\) |  \(6.1\) |  \(0.3\) |  \(5.2\) |  \(3.8\) |  \(7.9\) |  17.6 |  \(0.7\) |
| Change in Population \(%\) |  6.8 |  9.3 |  6.0 |  3.7 |  5.4 |  14.8 |  8.8 |
| Change Housing Unit Density \(%\) |  23.1 |  17.5 |  6.6 |  6.2 |  2.6 |  29.4 |  11.7 |

|  |
| :--- |


**Table 3**. Fit Statistics for Latent Class Analysis Profiles \(Class-Invariant, Diagonal Model\)

| Classes | LL | AIC | AWE | BIC | CAIC | Entropy | BLRT \(_p_\) |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | -98214.6 | 196541.1 | 197325.8 | 196794.5 | 196850.5 | 1 | NA |
| 2 | -95970.5 | 192110.9 | 193303 | 192495.4 | 192580.4 | 0.955626 | 0.009901 |
| 3 | -95161.3 | 190550.5 | 192150 | 191066.2 | 191180.2 | 0.943141 | 0.009901 |
| 4 | -94311.1 | 188908.3 | 190915.1 | 189555.1 | 189698.1 | 0.956014 | 0.009901 |
| 5 | -93770.7 | 187885.3 | 190299.5 | 188663.4 | 188835.4 | 0.956939 | 0.009901 |
| 6 | -93470.6 | 187343.2 | 190164.8 | 188252.4 | 188453.4 | 0.949103 | 0.009901 |
| 7 | -93229.8 | 186919.5 | 190148.5 | 187960 | 188190 | 0.950698 | 0.009901 |
| 8 | -92528.8 | 185575.6 | 189211.8 | 186747.2 | 187006.2 | 0.965318 | 0.009901 |
| 9 | -92294.7 | 185165.3 | 189209 | 186468.1 | 186756.1 | 0.964846 | 0.009901 |

_Note_. LL = Log likelihood; AIC = Akaike’s Information Criterion; AWE = Approximate Weight of Evidence Criterion; BIC = Bayesian Information Criterion; CAIC = Consistent Akaike’s Information Criterion; BLRT = Bootstrapped Log Likelihood Ratio Test

### Other Clustering Methods Considered

{% tabs %}
{% tab title="Latent class analysis \(LCA\)" %}
**Latent class analysis \(LCA\)**

Identifies unobservable groups/categories within a population using observed variables/indicators 

* **Uses**: usually categorical indicators \(e.g. survey response questions\) – continuous indicators would need to be transformed into some categorical representation \(e.g. quintiles\) 
* **Steps:** Choose the number of classes \(e.g., clusters\), run analysis, then test at different class specifications \(e.g., start at two classes, then test at three, then four…\) Optimal model is chosen based on information on fit \(e.g., log likelihood\). Bootstrap likelihood ratio test is also used 
* **Output** The probability of a response to EACH item in the inventory for each latent class. In other words, you’ll see the probability that members of each class had of choosing a given response for each variable
{% endtab %}

{% tab title="k-medoids clustering" %}
#### k-medoids clustering 

_\(used by Institute of Housing Studies at DePaul University for housing submarket analysis in Chicago – city and regional\)_

**Medoid** – the central-most point of a cluster; the object of a cluster whose average dissimilarity to all the objects in the cluster is minimal Unlike the means and medians used in k-means and k-median clustering, the medoid is an actual data point within the data set – the “most representative” point in a cluster More robust to noise and outliers than k-means Steps \(using Partitioning around Medoids \(PAM\) algorithm\): Initiation: select k of the n data points as medoids \(k is selected a priori\) Associate each data point with its closest Medoid \(the “assign” step\) For each medoid m and non-medoid point o, swap m and o, then assign data points to the closest swapped medoid \(o\) as in Step 2. If the “cost” of this new configuration \(the sum of pairwise dissimilarities\) is less than the cost with m as the medoid, then keep o as the new medoid and iterate this process until convergence. If the cost is more with o than with m as the medoid, then undo the swap. Iterate until convergence. \(the “update” step\) ****

**Pros:** Medoid is an actual instance from the dataset, unlike the means and medians used in k-means and k-medians clustering, making the algorithm more reliable for discrete data sets Better at finding clusters than k-means due to more rigorous “update” step 

**Cons: T**he number of clusters k is an input parameter, chosen by the investigator; inappropriate choice of k can lead to poor results More computationally intensive than k-means
{% endtab %}

{% tab title="Factor Analysis" %}
#### Factor Analysis \(and Principal Components Analysis\)

Often, a major component of datasets used for clustering are unobserved “latent” variables that are composed of many observed proxy variables 

* For example, the latent variable of “housing quality,” a rather abstract concept that could be measured in various ways, is often proxied by many observable variables \(e.g. building material, code violations, surrounding vacancies, crime rate\) that researchers contend make up the components of “housing quality” 
* These latent variables can be estimated by using factor analysis \(FA\) – indeed, a number of housing submarket analyses perform a form of factor analysis before clustering 

**Why use FA?** The idea is that a measure composed of multiple individual indicators can explain an abstract concept like housing quality better than the indicators would individually \(e.g., by reducing measurement error\) 

**How it’s used** \(example: Lisa K. Bates, 2006\): using confirmatory factor analysis, Bates defines “housing quality” as a construct containing 12 distinct dimensions – 5 individual indicators and 7 variables composed of multiple indicators. The factor scores estimated by CFA are then used as variables in the cluster analysis at the block group level. 

Principal components analysis \(PCA\) is also used, but PCA and FA are different 

* **FA** estimates factors, the underlying constructs \(e.g., “housing quality”\) that can’t be directly measured 
* **PCA** helps reduce the number of variables in a variable set to the “principal components,” which still explain the same amount of variance as the larger variable set, but with fewer variables – it’s primarily a variable reduction tool
{% endtab %}

{% tab title="k-means clustering" %}
#### k-means clustering

Relatively common and easy-to-use clustering method 

Steps: 

* **Initiation**: k initial “means” are randomly generated within the data domain 
* **Expectation**: Data points are assigned to the nearest mean to form k clusters – “nearest” mean is measured by Euclidian distance \(the “assign” step\) 
* **Maximization**: The centroid of each of the k clusters becomes the new “mean” Why k-means? Because the mean of the Euclidian distances between each point in a cluster and the cluster “mean” is used to calculate the updated location of the centroid \(the “update” step\) 
* **Repeat Steps 2-3** until convergence into highly-defined clusters has been reached

**Pros:** Computationally efficient 

**Cons:** The number of clusters k is an input parameter, chosen by the investigator; inappropriate choice of k can lead to poor results Poor handling of outliers \(logic: arithmetic means handle outliers worse than medians\) Tendency to produce equal-sized clusters can lead to bad results \(see below\)

![](../.gitbook/assets/image%20%281%29.png)
{% endtab %}

{% tab title="k-medians clustering" %}
#### k-medians clustering

Similar to k-means in approach, but uses medians instead of means. This allows the algorithm to better handle outliers and noise than k-means \(just as medians are better at handling outliers than arithmetic means\) Here, the median determines the centroid, not the mean 

**Pros:** Better handling of outliers than k-means \(logic: medians handle outliers better than arithmetic means\) 

**Cons:** The number of clusters k is an input parameter, chosen by the investigator; inappropriate choice of k can lead to poor results
{% endtab %}

{% tab title="k-means vs. k-medoids clustering" %}
Despite starting at the same initial points, the k-means algorithm has trouble finding the clusters apparent in the data compared to the k-medoids algorithm.

k-means: 1a – 1f

k-medoids: 2a – 2h

![](../.gitbook/assets/image%20%289%29.png)

The k-means algorithm asks “what is the centroid of the current cluster?” This question uses the mean of distances between the initial “mean” and the points within the cluster. The random location of the initial mean – and the distribution of the within-cluster distances from the mean – can heavily sway where the resulting centroid is placed \(since a number of outliers can heavily sway a mean in a way that they don’t sway medians or the medoid algorithm\). \(See Figure 1a-b for evidence of how the “outliers” of the upper right corner affect the brown and purple clustering decisions of the algorithm.\)

In the end, the k-means algorithm creates a pair of clusters where only one makes sense \(top left corner of data points\), and it combines what should be two clusters into one large cluster \(bottom left corner of data points\).

The k-medoids algorithm does a better job of handling the data points by asking “What data point minimizes the distance within the current cluster?” By keeping the algorithm tied to data points, it somewhat “restrains” where the updated medoid can be placed by naturally down-weighing outliers compared to closer points within a cluster. This more often results in “truer” and more representative clusters!
{% endtab %}

{% tab title="Ward’s method " %}
#### Ward’s method 

_\(used by Lisa K. Bates in housing submarket analysis of Philadelphia – city and regional\)_

A form of hierarchical clustering Agglomerative \(“bottom up”\): each data point starts as its own cluster, and clusters are merged as one moves higher up the hierarchy Divisive \(“top down”\): the entire dataset is one cluster, which is broken down into smaller clusters as you move down the hierarchy Ward’s method is a criterion used in agglomerative hierarchical clustering Goal: to minimize intra-cluster variance At each step, find the pair of clusters that leads to the minimum increase in the total within-cluster variance after merging

While Ward’s method generally involves the use of any objective function \(whichever is best for the investigator’s purposes\), the commonly known “Ward’s method” is Ward’s minimum variance method Objective function: minimize the error sum of squares \(the weighted sum of squares of differences between each average of y-values corresponding to the same x-value and the corresponding fitted y-values, the weight in each case being simply the number of observed y-values for that x-value.

•While Ward’s method generally involves the use of any objective function \(whichever is best for the investigator’s purposes\), the commonly known “Ward’s method” is Ward’s minimum variance method

Objective function in Ward’s minimum variance method: minimize the error of the squares

Error sum of squares – the weighted sum of squares of differences between each average of y-values corresponding to the same x-value and the corresponding fitted y-values, the weight in each case being simply the number of observed y-values for that x-value.

                ****∑〖𝑤𝑒𝑖𝑔ℎ𝑡×〖\(𝑙𝑜𝑐𝑎𝑙 𝑎𝑣𝑒𝑟𝑎𝑔𝑒 −𝑓𝑖𝑡𝑡𝑒𝑑 𝑣𝑎𝑙𝑢𝑒\)〗^2 〗

\(In other words, for a given data point, find the average y values of the points clustered around the given data point, and compare it to the fitted y values, taking the difference. Square this difference \(square of error\), multiply it by a weight equal to the number of points clustered around the given data point, and take the sum of this calculation. Create clusters that minimize this sum!\)
{% endtab %}

{% tab title="Latent transition analysis \(LTA\)" %}
#### Latent transition analysis \(LTA\)

* Shows how members move across classes over time
  * Could be useful to see how neighborhoods have changed from one typology to another \(instead of using variables of change \(e.g., change in home values\) to encapsulate neighborhood change into a single cross-sectional look at the current neighborhood typology\)
* requires longitudinal data
* [Penn State University has great technical resources on this](https://methodology.psu.edu/ra/lta)
{% endtab %}
{% endtabs %}

### Example 

{% tabs %}
{% tab title="Philadelphia " %}
#### Lisa K. Bates, Philadelphia \(city & metropolitan area\)

**Goal:** segment the housing market by product type and quality in a way that allows a prediction of house prices. Bates does this by examining “the dimensions of housing quality that segment the housing market”

> “Housing quality is a multi-dimensional construct that is best represented as a set of latent variables.”

Bates uses a two-part process:
{% endtab %}

{% tab title="Part 1: Confirmatory Factor Analysis " %}
Constructing a “housing quality” construct out of observable variables using confirmatory factor analysis

**Geography**: block group level for city of Philadelphia 

**Estimates** “twelve distinct dimensions to the housing quality concept” _\(**bold** = latent variables constructed via CFA\)_

|   | Dimensions |
| :---: | :--- |
| **1** | **Wealth and home equity** |
| **2** | **Physical blight**  |
| **3** | **Market rate renters** |
| **4** | **Subsidized renters** |
| **5** | **Poverty and deprivation** |
| **6** | **Crime** |
| **7** | **School quality** |
| 8 | Non-residential land uses \(commercial and industrial, measured as two separate indicators\) |
| 9 | Racial demographics \(proportion of block group that is black – reflects household preferences for racial heterogeneity or homogeneity in their housing choices\)  |
| 10 | Building type \(proportion of rowhouses\) |
| 11 | Neighborhood change indicators \(house price appreciation and population change\) |
| 12 | Access to central business district \(distance of block group to Center City\) |
{% endtab %}

{% tab title="Part 2: Ward’s method" %}
Using Ward’s method to cluster neighborhoods based on the latent and observable variables measured in part 1.

* Factor scores and observable variables are assigned for each block group 
* These factor scores are entered into Ward’s method for hierarchical clustering
{% endtab %}

{% tab title="Results" %}
![](../.gitbook/assets/image%20%282%29.png)

![](../.gitbook/assets/image%20%288%29%20%281%29.png)

![](../.gitbook/assets/image%20%284%29.png)
{% endtab %}
{% endtabs %}

### Evaluation and assessment

{% tabs %}
{% tab title="Internal evaluation" %}
* Clustering is evaluated based on the data of the clustering itself 
* Helps to determine effectiveness of the clustering, but not whether the clusters are valid. Internal evaluation does not tell us whether our clusters are true to the world, only whether the clustering was “done well” 
* Main criteria: cluster method that produces clusters with high similarity within clusters and low similarity between clusters are highly rated
* Methods ****
  * Silhouette 
    * value between -1 and +1, with values closer to +1 suggesting good clustering and values closer to -1 suggesting that a data point should be in a neighboring cluster. 0 suggests values on border of two clusters 
    * Useful for helping determine the number of natural clusters in the data – too many or too few clusters will be reflected in the average silhouette value of the entire dataset 
  * Other methods: Dunn Index; Davies-Bouldin index
{% endtab %}

{% tab title="External evaluation" %}
* Clustering validity is tested based on comparing the clustering results – the “training” data, if you will – to data that has already been labeled by class – the “test” data, if you will 
  * A machine learning approach – comparing training data to test data in order to see how well your clustering algorithm can predict the results of the test dataset. 
  * Perhaps useful if you have a decent number of neighborhoods already labeled by class, but you have a large amount of observations that are unlabeled by class but have other variables necessary to estimate what class they will belong to 
  * Requires a large dataset that will allow you to partition your data into a training and a test dataset
  * Manual evaluation Often will involve human expert assessment of the clustering results Subjective, but relies on human experience to assess whether clustering results are valid Very valuable form of assessment, especially because it allows for participatory research opportunities with those in communities that are being classified
{% endtab %}

{% tab title="Manual evaluation" %}
* Often will involve human expert assessment of the clustering results 
* Subjective, but relies on human experience to assess whether clustering results are valid 
* Very valuable form of assessment, especially because it allows for participatory research opportunities with those in communities that are being classified
{% endtab %}

{% tab title="Indirect assessment" %}
* Simply asks: Is this clustering analysis even useful? Do people understand it, and can it be used for the intended purpose? 
* Internal and external stakeholder conversations are invaluable as early in the process as possible to help make the analyses useful when the end product is produced
{% endtab %}
{% endtabs %}

### Conclusion

Factor analysis may be a useful first step in capturing abstract concepts such as housing quality in our analysis. Several clustering methods have been used to create subgroups from observable data 

* k-means, k-medoids and Ward’s method have been used in various published housing submarket analyses 
  * k-medoids seems to be more rigorous than k-means 
* Several forms of evaluation and assessment should be used to assess clustering effectiveness, validity, and usefulness

|  |  |
| :--- | :--- |
| k-means | [https](https://www.datanovia.com/en/lessons/k-means-clustering-in-r-algorith-and-practical-examples/)[://](https://www.datanovia.com/en/lessons/k-means-clustering-in-r-algorith-and-practical-examples/)[www.datanovia.com/en/lessons/k-means-clustering-in-r-algorith-and-practical-examples/](https://www.datanovia.com/en/lessons/k-means-clustering-in-r-algorith-and-practical-examples/) \(includes R code for implementation\) |
| k-means |  [https](https://www.coursera.org/lecture/cluster-analysis/3-4-the-k-medoids-clustering-method-nJ0Sb)[://](https://www.coursera.org/lecture/cluster-analysis/3-4-the-k-medoids-clustering-method-nJ0Sb)[www.coursera.org/lecture/cluster-analysis/3-4-the-k-medoids-clustering-method-nJ0Sb](https://www.coursera.org/lecture/cluster-analysis/3-4-the-k-medoids-clustering-method-nJ0Sb) \(also includes information on k-medoids, k-medians, and others\) |
| k-medoids | [https](https://www.datanovia.com/en/lessons/k-medoids-in-r-algorithm-and-practical-examples/)[://www.datanovia.com/en/lessons/k-medoids-in-r-algorithm-and-practical-examples](https://www.datanovia.com/en/lessons/k-medoids-in-r-algorithm-and-practical-examples/)[/](https://www.datanovia.com/en/lessons/k-medoids-in-r-algorithm-and-practical-examples/) \(includes R code for implementation\) |
| Ward’s method  | [https://www.stat.cmu.edu/~cshalizi/350/lectures/08/lecture-08.pdf](https://www.stat.cmu.edu/~cshalizi/350/lectures/08/lecture-08.pdf
) |
| Ward’s method  | [https://arxiv.org/pdf/1111.6285.pdf](https://arxiv.org/pdf/1111.6285.pdf
) |
| \(LCA\) and \(LTA\) | [https://methodology.psu.edu/ra/lca/teacherscorner](https://methodology.psu.edu/ra/lca/teacherscorner
) |



