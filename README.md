# Snap_PoliticalAds2020_Regression_Analyses
Constructing and interpreting simple linear regression and multiple linear regression models of the 2020 political ads on snap
## Background
Snapchat allows advertisers to create [political and election-related ads](https://www.snap.com/en-US/ad-policies/political) to promote candidates or specific parties, encourage people to vote, present ballot measures, and so on. All the ads are compliant with all applicable laws and regulations and the ads are encouraged to be positive rather than attacking other candidates' personal life. We will be looking the dataset in [Snap Political Ads Library](https://snap.com/en-US/political-ads) for 2020 and analyze how the number of times the ads has been viewed, or impressions, are associated to the amount the advertiser has spent, the displayed duration of the ads, and the ads' targeted gender in the United States. 
## Business Questions
How is the impression of the ads associated with the amount the advertiser spent over the campaign, the length of time the ads were displayed, and the targeted gender of the ads in the United States in 2020?
## Open Data
The data was downloaded from [Snap Political Ads Library](https://www.snap.com/en-US/political-ads)
The [dataset](https://github.com/ireneliu0106/Snap_PoliticalAds2020_Regression_Analyses/blob/main/PoliticalAds2020.xlsx) used in the analysis contains the information about all 12730 political ads on snapchat in 2020, including ad ID, ad URL, amount advertisers spend, impressions, start date, end date, gender, age bracket, etc. The complete list of column headers and the explanations can be found [here](https://github.com/ireneliu0106/Snap_PoliticalAds2020_Regression_Analyses/blob/main/PoliticalAds-data-explanations.txt).
## Data Analysis
Here are the Excel file for data analysis and the step-by-step descriptions of Excel data analysis

__How is number of impressions associated with spending?__
<img width="914" alt="Screen Shot 2021-03-04 at 1 12 32 AM" src="https://user-images.githubusercontent.com/70459912/109919845-5c8b6300-7c87-11eb-8a9a-b130fb539afe.png">
<img width="768" alt="Screen Shot 2021-03-04 at 1 13 44 AM" src="https://user-images.githubusercontent.com/70459912/109919849-5dbc9000-7c87-11eb-81cf-8c0140842836.png">

The simple linear regression model for impression and spending is Impressions = -125125+317.22*(SpendingInUSD). It means that a dollar difference in spending over the political campaign is associated with 317.22 difference in number of views by Snapchat users. The R square is 0.6168, which means that 61.68% of the data falls on the prediction line. The R square value is low, which suggests that the model can not accurately predict the number of impressions based on advertiser's spending. The standard error of residual is 1769707, which is a large number and symbolizes that the linear regression model doesn't fit the data that well. On the other hand, the p value is 0, which is less than 0.01 and means that the model is statistically significant and there is evidence suggesting that the association predicted by the model is not due by chance. The F significance is approximately 0, which also indicates that the impressions and spendings are related. 

__How is the number of impressions associated with spending, days the ads are displayed, and whether or not the ads target both genders?__
<img width="767" alt="Screen Shot 2021-03-04 at 8 53 47 AM" src="https://user-images.githubusercontent.com/70459912/109974058-2a99f100-7cc7-11eb-81c8-7b59b15edf76.png">

As seen from the table, the multiple regression model is Impressions = -498872.12+313.702*(SpendingInUSD)+9000.153*(DaysDisplayed)+194863.713*(TargetingBothGenders). The model suggests that when we control for the days of ads displayed and whether or not the ads target both genders, a one-unit difference in the USD spent is associated with a 313.702 unit difference in the number of impressions. On the other hand, when we control for the amount spent in USD and whether or not the ads target both genders, a one day difference in the ad displayed is associated with 9000.153 difference in the number of impressions. Lastly, when we control for the the amount spent in USD and number of days the ad is displayed, ads that target both genders have on average a 194863.713 difference in impressions than ads that target only one gender. The p-values for these independent variables are all less that 0.001, so we can say that there is sufficient evidence suggesting that the associations described above appear in the population. 

The R square value of this multiple linear regression model is 0.6236, which means that 62.36% of the data falls on the regression line. The model provides a fair prediction, although not totally accurate, of impressions based on spending, days the ads are displayed, and targeted gender. The standard error of residual is 1754044, which means that the number of impressions is quite spread out around its mean value. In addition, the F significance is 0, suggesting that the probability that none of the independent variables in the model is not significant is 0. 

__What are the correlations of impressions, spending, days the ads are displayed, and whether or not the ads target both genders?__

<img width="872" alt="Screen Shot 2021-03-04 at 9 38 06 AM" src="https://user-images.githubusercontent.com/70459912/109979882-620b9c00-7ccd-11eb-8fb9-6171239ece50.png">

For our purposes, we will only look at how spending, days the ads are displayed, and whether or not the ads target both genders are correlated with the impressions of the ads. As shown in the table, all three independent variables are positively correlated with the impressions, with the correlation between impressions and spending being the highest.

## Business Answer
Based on our analyses, there is an association between the impressions, amount spent over the campaign, days the ads are displayed, and whether or not the ads target both genders. In order to get more impressions on the ads in Snapchat, it is recommended that the advertisers invest more on the campaign, display the ads longer, and target both genders. The simple linear regression and multiple linear regression models provide fair predictions of the expected difference in impressions in correspondance with the change in the independent variables investigated. Advertisers can use these models to get a general idea of how many impressions they can get, which is quite useful. For future studies, one can look at if the impressions of ads on Snapchat has actual impacts on the voters' decisions and the election results. This can provide a more comprehensive view of whether displaying ads on Snapchat is worth it. 


