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
How is number of impression associated with spending? 
<img width="914" alt="Screen Shot 2021-03-04 at 1 12 32 AM" src="https://user-images.githubusercontent.com/70459912/109919845-5c8b6300-7c87-11eb-8a9a-b130fb539afe.png">
<img width="768" alt="Screen Shot 2021-03-04 at 1 13 44 AM" src="https://user-images.githubusercontent.com/70459912/109919849-5dbc9000-7c87-11eb-81cf-8c0140842836.png">
The simple linear regression model for impression and spending is Impressions = 317.22*(SpendingInUSD)-125125. It means that a dollar difference in spending over the political campaign is associated with 317.22 difference in number of views by Snapchat users. The R square is 0.6168, which means that 61.68% of the data falls on the prediction line. The R square value is low, which suggests that the model can not accurately predict the number of impressions based on advertiser's spending. The standard error of residual is 1769707, which is a large number and symbolizes that the linear regression model doesn't fit the data that well. On the other hand, the p value is 0, which is less than 0.01 and means that the model is statistically significant and there is evidence suggesting that the association predicted by the model is not due by chance. The F significance is approximately 0, which also indicates that the impressions and spendings are related. 


