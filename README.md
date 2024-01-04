# A/B Testing a Marketing Campaign

The purpose of this project was to use data from an A/B test to determine the best marketing campaign based on sales amongst three groups.

## [Dataset](https://www.kaggle.com/datasets/chebotinaa/fast-food-marketing-campaign-ab-test)

The dataset is made up of the following columns:

- MarketID: identifier
- MarketSize: size of market area by sales
- Location: location id of store
- AgeOfStore: how old the store is
- Promotion: which group the store belongs to (out of three groups)
- week: week for promotion
- SalesInThousands: Sales amount for the store

## Methodologies
After doing a short exploration of the dataset, I divided the data by group (1 is the control group, while 2 and 3 are two test groups). I then checked for assumptions of distributions and homoscedasticity. While the samples did not seem to come from normal distributions, the assumption of homoscedasticity was met, based on Levene's test.

![](/images/ab1.png)
![](/images/ab2.png)

Although the normality assumption was not met, due to the large sample size and homoscedasticity, an ANOVA can still provide reliable results. This ANOVA did produce a statistically significant p-value. In addition, to be sure, a Kruskal-Wallis test was also performed since this is a non-parametric test and it does not make assumptions about normality; this test also produced stastically significant results, which meant that we rejected the null hypothesis that the difference in population means is 0. 

After these tests, it was time for a post-hoc test which could allow us to understand which of the groups had this significant difference. For this purpose, Tukey's test was used, and the results showed a statistically significant difference between the group with the lowest average in sales (group 2) and the other two groups. However, the same could not be said between group 1 and 3.


## Conclusion
Since the control group and group 3 did not show a statistically significant difference, assuming that group 1 is the control group, I would recommend the fast food chain sticks with their original plan rather than focusing extra efforts on a marketing campaign that does not seem to provide better results, and instead other solutions that could offer better results could be explored.
