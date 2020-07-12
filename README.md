# PRIDIT
*PRIDIT* is an unsupervised, nonparametric risk/fraud/suspiciouness ranking technique and can also be used as an aggregation method   
I found this interesting but could not find a ready implementation in python so here is a python implementation of the PRIDIT algorithm

See a brief overview of why its a good option to consider for risk & for aggregation  below 
Further down is info on how the algo works 

## RISK/FRAUD Scoring 
Data backed risk evaluation benefits from two major things 
1. **Not being dependent on training data**  - Fraud tends to be relatively rare and having past fraud data is not always possible. This makes classification or NN based techniques impossible to use. PRIDIT being unsupervised does not require any training data or prior fraud information. 
2. **Degree of belongingness to the risk group** instead of black & white classification i.e. the degree of suspiciousness. This allows for rank ordering rows based on degree of suspiciousness and also allows for using this for further analysis i.e. correlate with demographic variables


## AGGREGATION 
It is an alternative to weighted averages or composite scores and other aggregation techniques and is more accurate in a broader set of cases

3. **Is not strongly tied to an assumed distribution** - It does not make any assumptions of the distribution of data, for example logistic assumes normally distributed data. PRIDIT usually assumes the distribution of the response variable so is effectively a distribution free method
4. **Can handle categorical data** - Since the method converts input data into ordinal data , It works well with categorical and continuous mix of data and can work on all categorical data too. So it does not make any assumptions about the data generating process.  
.... For example 2 different territory managers collect data on a process . There is always a risk of difference in the way in which the data is collected.  For example territory 1 reports 83% doctors having prescribed salicylic acid where as territory 2 reports 75% prescribe salicylic acid , PRIDIT method just considers that territory 1 has more prescriptions than territory 2 but ignores the magnitude of the difference.
*Caveat* - So this makes using PRIDIT on larger data sets more robust than on small data sets.
5. **Is robust in handling missing data** - PRIDIT is a relative measure. which means if missing data is present, especially if data missing is similarly missing in many rows,  is not a big challenge as long as the  % is not too high.

## PRIDIT has two parts

1 -- **RIDIT** score calculation -- RIDIT is shorter version to the phrase "Relative to an Identified Distribution". This is a reference to the point made earlier that PRIDIT does not assume a distribution like LOGIT does.

2 -- **P**CA on the RIDIT scores -- PCA is calculated on the RIDIT scores to find the eigen vector/value which captures the biggest variance.  

Making the technique's name P(ca) + RIDIT.

A point to note though while interpreting the results is -- In PRIDIT PCA is applied and the first Principle component is picked. The first principle component captures the most variance & usually will be representative of the kind of variables used, if most of the variables used are risk related then the PRIDIT score could be called a risk indicator. If most of the variables are Quality related then the PRIDIT score can be a proxy /composite quality indicator



Credit to Brock for coming up with RIDIT in 1958 https://www.jstor.org/stable/2527727  
and to the implementation @ The Journal of Risk and Insurance, 2002, Vol. 69, No. 3, 341-371
