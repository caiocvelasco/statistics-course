# Econometric Model and Statistical Inference

## 1. Identifying the Problem  
We aim to study the relationship between household income and food expenditure. In practical terms, we often ask: given one variable's value, can we predict the other's?

## 2. Economic Theory as a Basis  
Economic theory posits that expenditure on goods depends on income:
- Y Weekly food expenditure per person (dependent variable).  
- X: Weekly household income (independent variable).  
Economic theory describes the average behavior of groups, not individuals. For example, car sales (Y) include both a systematic part (predictable) and a random error component \( e \), reflecting omitted factors and inherent uncertainty:  
\
$Y = f(P, \ldots) + e$


## 3. Econometric Modeling  
To investigate relationships like income and expenditure, we:
- Build an economic model (theoretical foundation).  
- Develop an econometric model for empirical analysis.  
The econometric model specifies both the systematic portion (e.g., functional form from theory) and the random component \( e \). A simple linear form assumes:  
\[
Y = \beta_1 + \beta_2 X + e
\]
Where:  
- \( \beta_1 \): The intercept.  
- \( \beta_2 \): The slope.  
- \( e \): The error term, capturing deviations from the linear relationship.  

**Why Assume a Linear Relationship?**  
A linear relationship is assumed because of its simplicity and interpretability. It represents a constant rate of change, making it easy to model and understand. Professor Sanford Weisberg from the University of Minnesota highlights that linear regression is foundational in statistics, providing a simple framework for estimating relationships between variables and showing broad empirical success.

## 4. Specification and Functional Form  
Specification involves defining the model’s structure, including:  
- Choice of variables (e.g., income and expenditure).  
- Functional form (e.g., linear, quadratic).  
The functional form determines how the variables relate. For instance, a linear form assumes:  
\[
Y = \beta_0 + \beta_1 X + e
\]  
Correct specification is critical to avoid omitted variables, multicollinearity, or other biases.

## 5. Statistical Foundation: Population, Parameters, and Randomness  
The Model:  
The simple linear regression model is represented as:  
\[
E(Y | X) = \mu_{Y | X} = \beta_1 + \beta_2 X
\]  
Here:  
- \( E(Y | X) \): The expected value of \( Y \) given \( X \).  
- \( \beta_1 \): The intercept.  
- \( \beta_2 \): The slope.  
Real-world data points \( (X, Y) \) are not perfectly aligned on the regression line; instead, values of \( Y \) are distributed around their mean \( E(Y | X) \) for each given \( X \).

## 6. Decomposition of \( Y \): Systematic and Random Components  
Regression analysis decomposes each observation of \( Y \) into two parts:  
- Systematic component:  
\[
E(Y | X) = \beta_1 + \beta_2 X
\]  
- Random component: The error term \( e = Y - E(Y | X) \), accounting for deviations from the mean.  
Key Characteristics:  
- \( Y \) and \( e \) are random variables with probability distributions.  
- \( Y \) is observable, while \( e \) is unobservable.  
- The error term \( e \) represents factors influencing \( Y \) that are not included in the model (e.g., other economic variables).  
The full model becomes:  
\[
Y = \beta_1 + \beta_2 X + e
\]

## 7. Questions and Expectations  
**Question of Interest**:  
If weekly income \( X \) increases by $100, how much will average weekly food expenditure \( Y \) rise?

**What Do We Expect?**  
As income varies across households, we expect changes in average food expenditure. This is captured in the conditional probability density function \( f(Y | X) \).

## 8. Key Points for Statistical Inference  
Using the econometric model, we:  
- Estimate parameters \( \beta_1, \beta_2 \) to understand the systematic relationship.  
- Predict outcomes for given input values.  
- Test hypotheses (e.g., does higher income lead to higher average food expenditure?).

## 9. How Good Are These Estimates?  
- This question is not answerable directly because we will never know the true values of the population parameters \( \beta_1 \) or \( \beta_2 \).  
- The least squares estimates are numbers that may or may not be close to the true parameter values, and we will never know for sure.  
- Instead of asking about the quality of individual estimates, we focus on the quality of the least squares estimation procedure.  
  - If we were to collect another sample of data (say, a different set of 40 households), we would get different estimates for \( \beta_1 \) and \( \beta_2 \), even with the same income distribution. This sampling variation is unavoidable because household food expenditures are random variables.  
  - The least squares estimators \( \beta_1 \) and \( \beta_2 \) are also random variables, as their values depend on the random sample. This leads to the following questions:  
    - What are the expected values, variances, and distributions of these estimators?  
    - How do the least squares estimators compare with other estimation methods? Could other estimators produce more accurate estimates with higher probability?  
- **Unbiased Estimator and Sampling Variance**:  
  - The repeated sampling interpretation of \( E(\cdot) \) provides insight into the concept of unbiasedness. An unbiased estimator produces accurate results on average, even if individual estimates vary.  
  - Over many samples, the average of the estimates for \( \beta_2 \) will equal the true value of \( \beta_2 \).  
  - While individual estimates may not be close to the true value, the least squares estimator is unbiased.  
  - This sampling property is important because it ensures that the estimator is "correct" on average, even if not for every sample. The variability of these estimates, driven by the random sampling of households, is measured by the sampling variance.

## 10. The Probability Distribution of the LS Estimators \( \beta_1 \) and \( \beta_2 \)  
- The properties of the least squares estimators do not depend on the normality assumption SR6.  
- If we assume that the error terms \( e_i \) are normally distributed with mean zero and variance \( \sigma^2 \), then the least squares estimators are also normally distributed.  
- **What if the errors are not normally distributed?**  
  - Sometimes, we can still make valid statements about the probability distribution of the estimators, thanks to the **Central Limit Theorem (CLT)**.  
  - The applicability of the CLT depends on factors like the smoothness, symmetry, or skewness of the error distributions, as well as the sample size.  
  - **Large Sample Properties**: In practice, the CLT allows regression analysis to proceed even when the population is not normally distributed, as long as the sample size is large enough.

## 11. Interval Estimation  
**Main Point**:  
When discussing "confidence intervals," our confidence lies in the procedure used to construct the interval, not any single interval estimate. Interval estimation provides a range of values within which the true parameter \( \beta_2 \) is likely to fall, reflecting the precision of our estimate. These are often called *interval estimates* rather than "confidence intervals" to avoid confusion.  

**Interval Estimate: Step by Step**:  
- Assume the least squares estimators \( \beta_1 \) and \( \beta_2 \) have normal distributions.  
- Standardize them → \( Z \) follows a normal distribution.  
- From the standard normal table, the probability between -1.96 and 1.96 is 0.95. We substitute \( Z \) into the formula and rearrange:  
  \[
  P\left( -1.96 \leq Z \leq 1.96 \right) = 0.95
  \]  
  This defines an interval with 95% probability of containing \( \beta_2 \).  
- The interval endpoints are random variables, so we call it an *interval estimator*. Each sample will yield a different interval estimate.

- There’s a 5% chance the interval does not capture the true \( \beta_2 \), akin to rolling dice where a small chance exists that the sum won't exceed a certain value.

- In repeated sampling, 95% of intervals will contain the true \( \beta_2 \). The random variable "interval estimator" \( \beta_2 \pm 1.96 \cdot \text{SE}(\beta_2) \) will contain the true parameter with 95% probability.

- If the variance \( \sigma^2 \) of the error term is unknown, we estimate it from the sample, replacing \( \sigma^2 \) with \( \hat{\sigma}^2 \), and the resulting formula is:  
  \[
  \beta_2 \pm t_{1-\alpha/2} \cdot \hat{\text{SE}}(\beta_2)
  \]  
- The **t-distribution** arises when we estimate \( \sigma^2 \). This comes from the assumptions of the simple linear regression model, where the least squares estimators are normal. Standardizing them leads to the t-distribution, which is used for interval estimation and hypothesis testing.