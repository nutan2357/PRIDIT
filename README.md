# PRIDIT
PRIDIT is an unsupervised, nonparametric aggregation technique

*PRIDIT* is an unsupervised, nonparametric aggregation technique.

It is an alternative to weighted averages or composite scores and other aggregation techniques and is more accurate in a broader set of cases

- It does not make any assumptions of the distribution of data, for example logistic assumes normally distributed data. PRIDIT usually assumes the distribution of the response variable so is effectively a distribution free method

- Since the method converts input data into ordinal data , It works well with categorical and continuous mix of data and can work on all categorical data too. So it does not make any assumptions about the data generating process.

o For example 2 different territory managers collect data on a process . There is always a risk of difference in the way in which the data is collected.  For example territory 1 reports 83% doctors having prescribed salicylic acid where as territory 2 reports 75% prescribe salicylic acid , PRIDIT method just considers that territory 1 has more prescriptions than territory 2 but ignores the magnitude of the difference.

o So this makes using PRIDIT on larger data sets more robust than on small data sets.

- PRIDIT is also unsupervised which means it needs no training data. The other methods in unsupervised cases would be to identify outliers through say a Chi-Sq test etc

- PRIDIT being a relative measure missing data , especially if data missing is similarly missing in many rows,  is not a big challenge as long as the missing % is not too high.

PRIDIT has two parts

1 -- **RIDIT** score calculation -- RIDIT is shorter version to the phrase "Relative to an Identified Distribution". This is a reference to the point made earlier that PRIDIT does not assume a distribution like LOGIT does.

2 -- **P**CA on the RIDIT scores -- PCA is calculated on the RIDIT scores to find the eigen vector/value which captures the biggest variance.  

Making the technique's name P(ca) + RIDIT.

A point to note though while interpreting the results is -- In PRIDIT PCA is applied and the first Principle component is picked. The first principle component captures the most variance & usually will be representative of the kind of variables used, if most of the variables used are risk related then the PRIDIT score could be called a risk indicator. If most of the variables are Quality related then the PRIDIT score can be a proxy /composite quality indicator
