
### Statistics for AB testing ###
What is an A/B test?
An A/B test consists of taking two comparable groups of users and exposing them to two different versions (the control and a variation) of a software experience. By doing that and measuring how each of the groups interacts with the software we hope to infer which of the two versions best serves its purpose.

#### Some relevant statistics concepts

* ##### Overall Evaluation Criterion (OEC)
Also called Primary Goal (in Optimizely and other tools) or Dependent variable, in statistics terminology. It’s a quantitative measure that defines the experiment’s objective. Ex. Conversion rate.
Null hypothesis (Ho)
* The hypothesis that the OECs for the variants are not different in fact, and that any observed differences during the experiment are due to random fluctuations. The goal of our split-test is to reject this null hypothesis, and therefore conclude with statistical significance that an observed difference in the OECs is not due to random fluctuations. Failing to reject the Null hypothesis doesn’t mean it is true, means no conclusion can be drawn.
(Most of the statistics used in A/B testing come from the field of Statistical hypothesis testing.)



|------------------|------|--------|---|---|
| Possinble action | H true | H faalse |   |   |
| A                |      |        |   |   |
| b                |      |        |   |   |


* P-value
In the context of Null hypothesis testing, the p-value for a given observed result represents the probability obtaining such result (or any result more extreme than that) only due to random fluctuations, assuming the Null hypothesis is true.
For the purpose of A/B testing, we can say the p-value represents the probability of observing a given OEC difference (or any difference more extreme than that) between variants due only to random fluctuations, assuming the OECs are in reality the same for both.
Also:
The P-value is not the probability of the null-hypothesis being true — it is calculated assuming the null hypothesis is true to start with.
On Optimizely p-value is not made visible and instead the concept “Statistical Significance status” is mentioned. This value represents the probability of a given observed difference not being due to chance.
* Significance level (SL)
Set in the beginning of the experiment, the significance level (traditionally set to 1% or 5%) is the probability threshold under which the null hypothesis can be rejected. In other words, if a given OEC difference has p-value smaller than the significance level, we’ll conclude the OECs are not the same for the variants and, therefore, believe there’s causality between the change and the effect. In other words, we can say variant B’s OEC is statistically significantly different from the control’s OEC.
Significance level is also the probability of rejecting the Null hypothesis when this hypothesis is true (called Type I error or false positive).
As an example, setting the SL of an A/B test to 0.05 (or 5%) means that even for statistically significant results, there’s a 5% risk of concluding there’s a difference between the variations when in fact there is not.
Note: Optimizely uses different terminology here and allows an Optimizely-significance value to be set for each project (default 10%). According to the documentation, the Optimizely-significance value represents 1-pvalue, which means that to set the SL to 0.05 this value must be chosen to be 95%.
* Power
On the contrary of SL which focuses on assessing the down-side of the experiment (probability of error and no-error), Power represents the probability of correctly rejecting the null hypothesis or obtaining a true-positive.
In other words, statistical Power is the likelihood that an experiment will detect an effect if there is in fact an effect to be detected.
The power of an experiment is influenced by a number of factors (such as sample size) and 80% is a typical desired value. Experiments with low power will never be conclusive in practical terms.
Standard deviation
The standard deviation (σ — greek ‘sigma’) is a measure that is used to quantify the amount of variation or dispersion of a set of data values, in other words it represents how much ‘spread-out’ the data points are. In the context of A/B testing, we look at the distribution of observed OECs.
Conversion events, such as purchases or registrations, can be modelled as a Bernoulli trial with probability (p)= conversion rate. In that case, the standard deviation (σ) is given by:

* Minimum sample size
For a desired Power (probability of detecting a true-positive if it exists) and a sensitivity Δ (the amount of change we want to detect, ex. 5% of control value) we can estimate a minimum sample size that‘s needed to achieve that. A useful formula, for a Power = 80% is the following:

where n is the number of users in each variant. That means that to detect a change Δ with 80% probability, we’ll need n users in each variant.
Such estimation is interesting to understand how long a given experiment we’re planning is likely to take in order to detect the change we’re looking for, if it exists. As can be seen from the formula above, n depends on the square of σ which means we can reduce the minimum sample size by choosing an OEC with lower variability (ex. conversion rate instead of purchase value).
Perhaps even more relevant, this formula tells us that small changes are harder to detect. Which means that great ideas will hardly be missed but also that A/B testing is often not a suitable/efficient way to make small incremental improvements.
Confidence intervals
The Confidence interval is a range of values that is likely to contain the actual effect of the variant on the OEC of the control. Just as an example, a 95% confidence interval (that is, an interval that has 95% probability of containing the actual effect) could be calculated as:

where OB and OA are the average value of the observed OECs and sigma-d is an estimation of the standard deviation of the difference. In practice though, tools such as Optimizely calculate this interval automatically.
Looking at the confidence interval gives us an insight of potential up and down-side of the experiment. It allows us to say, with a given probability (in the case above at least 95%), that the true difference between OECs is not higher than the higher bound of the interval. That can support, the decision of stopping the test because the upside is very likely lower than what we were hoping to achieve.
However, we might not be able to tell significantly if the test represents, or not, an improvement for the OEC — that conclusion can only be made if the whole interval is positive and does not contain 0.
