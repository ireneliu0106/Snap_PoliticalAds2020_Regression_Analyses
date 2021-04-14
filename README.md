# Snap_PoliticalAds2020_Regression_Analyses
Constructing and interpreting simple linear regression and multiple linear regression models of the 2020 political ads on Snapchat
## Background
Snapchat allows advertisers to create [political and election-related ads](https://www.snap.com/en-US/ad-policies/political) to promote candidates or specific parties, encourage people to vote, present ballot measures, and so on. All the ads are compliant with all applicable laws and regulations and the ads are encouraged to be positive rather than attacking other candidates. We will be looking at the dataset in [Snap Political Ads Library](https://snap.com/en-US/political-ads) for 2020 and analyze how the number of times ads have been viewed, or impressions, is associated to the amount the advertiser has spent, the number of days the ads are displayed on Snapchat, and the ads' targeted gender in the United States. Note that only data with an end date available on the dataset is considered in this analysis.
## Business Questions
How is the impression of the ads associated with the amount the advertiser spent over the campaign, the length of time the ads were displayed, and the targeted gender of the ads in the United States in 2020?
## Open Data
The data was downloaded from [Snap Political Ads Library](https://www.snap.com/en-US/political-ads).
The [dataset](https://github.com/ireneliu0106/Snap_PoliticalAds2020_Regression_Analyses/blob/main/PoliticalAds2020.xlsx) used in the analysis contains the information about all 12730 political ads on snapchat in 2020, including ad ID, ad URL, amount advertisers spend, impressions, start date, end date, gender, age bracket, etc. The complete list of column headers and the explanations can be found [here](https://github.com/ireneliu0106/Snap_PoliticalAds2020_Regression_Analyses/blob/main/PoliticalAds-data-explanations.txt). The dataset that contains information on Snapchat political ads from 2018 to 2020 can be downloaded [here]().
## Data Analysis
Here are the [Excel file for data analysis](https://github.com/ireneliu0106/Snap_PoliticalAds2020_Regression_Analyses/blob/main/PoliticalAds_Analysis.xlsx), the [step-by-step descriptions of Excel data analysis](https://github.com/ireneliu0106/Snap_PoliticalAds2020_Regression_Analyses/blob/main/Step-by-step%20instructions%20of%20Excel%20data%20analysis), and [python file for data analysis](https://github.com/ireneliu0106/Snap_PoliticalAds2020_Regression_Analyses/blob/main/2021_04_13_MiniProject4.ipynb)

__How is number of impressions associated with spending in 2020?__

<img width="914" alt="Screen Shot 2021-03-04 at 1 12 32 AM" src="https://user-images.githubusercontent.com/70459912/109919845-5c8b6300-7c87-11eb-8a9a-b130fb539afe.png">
<img width="768" alt="Screen Shot 2021-03-04 at 1 13 44 AM" src="https://user-images.githubusercontent.com/70459912/109919849-5dbc9000-7c87-11eb-81cf-8c0140842836.png">

The simple linear regression model for impression and spending is Impressions = -125125+317.22*(SpendingInUSD). It means that a dollar difference in spending over the political campaign is associated with 317.22 difference in number of views by Snapchat users. The R square is 0.6168, which means that 61.68% of the data falls on the prediction line. The R square value is not high, which suggests that the model might not accurately predict the number of impressions based on advertiser's spending. The standard error of the residuals is 1769707, which is a large number and symbolizes that the linear regression model doesn't fit the data that well. On the other hand, the p value is 0, which is less than 0.001 and means that the model is statistically significant and there is evidence suggesting that the association predicted by the model is not due by chance. The F significance is approximately 0, which also indicates that the impressions and spendings are related. 

__How is the number of impressions associated with spending, days the ads are displayed, and whether or not the ads target both genders?__

<img width="767" alt="Screen Shot 2021-03-04 at 8 53 47 AM" src="https://user-images.githubusercontent.com/70459912/109974058-2a99f100-7cc7-11eb-81c8-7b59b15edf76.png">

As seen from the table, the multiple regression model is Impressions = -498872.12+313.702*(SpendingInUSD)+9000.153*(DaysDisplayed)+194863.713*(TargetingBothGenders). The model suggests that when we control for the days of ads displayed and whether or not the ads target both genders, a one-unit difference in the USD spent is associated with a 313.702 unit difference in the number of impressions. On the other hand, when we control for the amount spent in USD and whether or not the ads target both genders, a one day difference in the ad displayed is associated with 9000.153 difference in the number of impressions. Lastly, when we control for the the amount spent in USD and number of days the ad is displayed, ads that target both genders have on average a 194863.713 difference in impressions compared to ads that target only one gender. The p-values for these independent variables are all less that 0.001, so we can say that there is sufficient evidence suggesting that the associations described above appear in the population. 

The R square value of this multiple linear regression model is 0.6236, which means that 62.36% of the data falls on the regression line. The model provides a fair prediction, although not totally accurate, of impressions based on spending, days the ads are displayed, and targeted gender. The standard error of residual is 1754044, which means that the number of impressions is quite spread out around its mean value. In addition, the F significance is 0, suggesting that the probability that none of the independent variables in the model is not significant is 0. 

__What are the correlations of impressions, spending, days the ads are displayed, and whether or not the ads target both genders?__

<img width="872" alt="Screen Shot 2021-03-04 at 9 38 06 AM" src="https://user-images.githubusercontent.com/70459912/109979882-620b9c00-7ccd-11eb-8fb9-6171239ece50.png">

For our purposes, we will only look at how spending, days the ads are displayed, and whether or not the ads target both genders are correlated with the impressions of the ads. As shown in the table, all three independent variables are positively correlated with the impressions, with the correlation between impressions and spending being the highest.

__How is the number of impressions associated with spending in 2020?__

<img width="1213" alt="Screen Shot 2021-04-14 at 2 11 17 PM" src="https://user-images.githubusercontent.com/70459912/114758764-56c77980-9d2b-11eb-9af9-f8f44d2ced43.png">

This plot was generated with plotly express in Python. The result obtained was similar to excel, with the simple linear regression model of Impressions = -89683.9 + 321.452*(SpendingInUSD).  It means that a dollar difference in spending over the political campaign is associated with 321.452 difference in number of views by Snapchat users. Also, the R-squared value was 0.601, meaning that 60.1% of the data falls on the prediction line. Although the slopes and the intercepts were a little different from the excel model, both models show a positive correlation between spending and numbers of impressions.

__What is the trend of total number of impressions from 2018 to 2020?__

<img width="1206" alt="Screen Shot 2021-04-14 at 2 25 37 PM" src="https://user-images.githubusercontent.com/70459912/114760429-4adcb700-9d2d-11eb-865b-7ff5c3374b48.png">

As shown in the plot generated from plotly express, there is a significant increase in the total number of Snapchat ad impressions from 2018 to 2020. This means that more political ads are viewed by Snapchat users over the years and Snapchat has become a commonly used platform for political advertisement. 

## Comparison of Python and Excel Analysis
The plots generated with python and excel give similar results. However, the interactive component of the python plot enable the viewers to directly see the predicted number of impressions by spending without calculating it manually. The python plot also displays the values on each dot, so the viewers do not have to estimate them from the axis. Although the results generated from both python and excel are te same, the interactive component of python plots make it easier for the viewers to understand the details of the analysis. The html files can be downloaded from [here](https://colab.research.google.com/drive/1_4O3SiM8DxIZKDGmt07CRDESE9LEE1pz#scrollTo=C_GC05IXJGCz)

## Business Answer
Based on our analyses, there is an association between the impressions, amount spent over the campaign, days the ads are displayed, and whether or not the ads target both genders. In order to get more impressions on the ads in Snapchat, it is recommended that the advertisers invest more on the campaign, display the ads longer, and target both genders. The simple linear regression and multiple linear regression models provide fair predictions of the expected difference in impressions in correspondance with the change in the independent variables investigated. In addition, there is a clear trend that the total number of impression are increasing since 2018. This implies that Snapchat has become a common platform for political ads and more Snapchat users are exposed to political ads through Snapchat. Advertisers can take such trend into consideration and use the regression models to get a general idea of how many impressions they can get based on their investments and the design of the ads. For future studies, one can look at how the impressions of ads on Snapchat impacted the voters' decisions and the election results. This can provide a more comprehensive view of whether displaying ads on Snapchat will postively influence the political campaign.
