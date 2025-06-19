# Multivariate Data Analysis

This project is summarising Chapter 4, Multivariate Distributions, from Applied Multivariate Statistical Analysis (Sixth Edition) by Härdle, Simar and Fengler. Statistical analysis often requires tools to effectively handle and interpret multivariate data. In this project, we will explore the essential probability tools and techniques for understanding and analyzing multivariate data, such as the distributions, transformations and sampling methods.

In this project, we have learned the fundamental tools in multivariate analysis, including various distributions, sampling methods, as well as copula. Gaussian Copula and Gumbel-Hougaard Copula were applied to the Apple and Google stock data to capture dependencies between variables. The analysis highlighted Gumbel Copula’s strength in capturing tail dependence, a critical feature for modelling tail-heavy data which are commonly observed in real-world stock markets. 

## Implementation
![image](https://github.com/user-attachments/assets/cde1784a-4a7c-4807-aab0-6a02e583e514) <br>
*Fig. 1*

We analyse the adjusted closing prices of Apple (AAPL) and Google (GOOGL) from January 1st 2019 to January 1st 2024, focusing on their daily log returns. The log return distributions of Apple and Google appear similar, as shown in Fig. 1 (left). Both distributions have mean close to 0 and standard deviation approximately 0.02, indicating no significant daily directional bias and have similar levels of volatility. The kurtosis is 5.4 for Apple and 4.1 for Google, both greater than 3, implying heavier tails and higher peaks compared to the normal distribution, as reflected in Fig. 1 (left). 

Fig. 1 (right) shows the joint distribution of Apple and Google log returns, highlighting the dependence structure between the two assets, motivating the use of copula models to explore the relationship further, especially in the tails of the distribution where extreme events may occur.

We transform the log returns onto a uniform scale to fit Gaussian Copula and Gumbel-Hougaard Copula models. The Gaussian Copula has a fitted correlation parameter of 0.68, indicating moderate linear dependence between the log returns of Apple and Google, the upper tail dependence value is calculated as -0.83, reflecting weak upper tail dependence in extreme scenarios. The Gumbel Copula has fitted θ parameter of 1.96 which indicates the model captures strong upper tail dependence, where extreme positive events for a stock are more likely to coincide with similar events for the other.

![image](https://github.com/user-attachments/assets/faa4af02-2eb5-4478-969b-40af21a2732b)
<br>
*Fig. 2*

Fig. 2 shows the contour plot of Gaussian Copula (left) and Gumbel Copula (right) on the uniform scaled-data. The Gaussian Copula shows elliptical contours, representing symmetrical dependence and limited tail behaviour. The Gumbel Copula contours are more focused at the corners, capturing tail dependence (extreme events) more effectively.
The models are evaluated using Akaike Information Criterion (AIC), where the AIC for Gaussian Copula and Gumbel Copula are 6087 and -705 respectively. The significantly lower AIC of the Gumbel Copula indicates a much better fit to the data, especially since the marginal distributions exhibit heavy tails. This highlights the Gumbel Copula's strength in modelling extreme events and tail dependence compared to the Gaussian Copula. 

![image](https://github.com/user-attachments/assets/da25f8bc-fafe-4f4e-9713-abc5f5662f79)<br>
*Fig. 3*

In Fig, 3, synthetic data generated from the copula models is compared with the observed data (left), on a uniform scale. The Gumbel Copula (right) better replicates the characteristics of the actual data, especially in the tails, while the Gaussian Copula (middle) struggles to capture the extreme behaviour. This further confirms the Gumbel Copula's suitability for modelling heavy-tailed distributions and tail dependence in financial time series.

