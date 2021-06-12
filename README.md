# Project-1

<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Presentation%20Title.png"></p>

#### Primary Libraries Used: Pandas, Matplotlib, Seaborn & Plotly Express

#### APIs Used: Quandl & Alpaca

### Project Description 
In this project, we sought to utilize datasets from Fannie Mae, the St. Louis Fed, the economic data repository Quandl as well as the stock trading platform Alpaca (mortgage backed security perfomance data) to present a clear picture of the mortgage industry since the beginning of the new millenium. We wanted to see whether today's lending environment resembled that of the 2000s, given that low interest rates preceded an asset bubble that finally burst in 2008. After that crisis, as well as during the pandemic; the Federal Reserve lowered interest rates through a program known as quantitative easing to stave off deflation. In the report below, we attempt to evaluate whether or not these low interest rates could lead to another housing bubble in light of four questions. We then make recommendations based on our evaluation.  
 
 ### Key Questions:
- What is the impact of low interest rates on the housing market?
- What is the impact of low interest rates on loan quality overall?
- What correlations exist between low interest rates and other data points?
- What is the impact of low interest rates on mortgage backed securities?

### Executive Summary of Findings
What we found is that [we now have a K-shape housing boom (source: Axios)](https://www.axios.com/housing-bubble-federal-reserve-intervention-1ac8151e-d8f3-4984-af23-23414932a32b.html). As we will attempt to show that low interest rates and have lead to soaring single-family home prices, ushering in a highly competitive housing market in which only well-heeled qualifying buyers can be competitive. In addition, we attempt to argue that *low interest rates correlate directly to soaring single-family housing prices*, which in turn *lead to degraded loan quality* as well as *stagnating returns for mortgage backed securities*. 

### Part 1: Preparing the Data
After downloading our data in CSV format from our various sources in CSV (comma separated value) format from the year 2000 through 2020. We then used the Pandas library to aggregate our data into a consolidated dataframe. Afterward, we cleaned it by dropping any null values and displaying the new dataframe to check our work. This portion of our project can be found in the notebook called 'DataClean.ipynb' in the solution directory. In addition, we reset the index several times in our 'DataAnalysis.ipynb' notebook. We recognize that it is duplicative, but it was a lot easier for us to call the initial combined dataframe and work with a different instance each time than worrying about alterations made to said dataframe as our code flows throughout the notebook. Ultimately, it comes down to individual programmming style in our opinion.

### Part 2: Data Visualization
Our data analysis notebook incorporates three primary visualization libraries in Python. In this section, we visualize the CSV data from Fannie Mae and the St. Louis FedThey are: Matplotlib, Seaborn and Plotly Express. The resulting visuals are shown in sequential order below and arranged by visualization library. Bear in mind that we did not use every visual generated in the 'DataAnalysis.ipynb' file for presentation purposes.

#### Matplotlib Area & Line Plots
The first visualization libarary we used is Matplotlib, which allowed us to create area and line plots to display trends in our data. 


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Case-Schiller_vs_Interest_Rate_Plot.png"></p>
As you can see, there is a pronounced inverse correlation between interest rates and housing prices. This makes sense because increase access to credit allows homebuyers to bid up prices. The extent to which the two are correlated will be quantified in the corresponding heatmap correlation below.


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Federal_Funds_Rate_vs_Interest_Rate_Plot.png"></p>
This visual shows us just how large a footprint the Federal Reserve has in setting interest rates. We see here that the two rates follow a similar trajectory. The data is clear on this point, when the Federal Funds rate goes up or down, so do interest rates on 30-year fixed rate mortgages. The exact correlation is quantified in the corresponding heatmap in the following section.


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Loan_Volume_vs_Interest_Rate_Plot.png"></p>
This plot also makes sense in that expanded access to credit means that more people apply for it. Bear in mind that this only represents a slice of the overall market. The data we used only shows Fannie Mae's loan volume. It is contrasted directly with Freddie Mac's nationwide average 30-year fixed rate which was obtained from the St. Louis Fed. As with the other plots, this comparison has a corresponding heatmap correlation in the section below.


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/FICO_Score_vs_Interest_Rate_Plot.png"></p>
This visual is very telling. Since the 2008 meltdown, borrower FICO scores have actually *gone up*. Today's borrowers do not appear to be the subprime borrowers of the 2000s. We can thank an enhanced regulator environment and tightened underwriting standards for this trend. However, it begs the question of whether or not public policy and underwriting standards are making home loans out of reach for a wide swath of the population in favor of more well-heeled borrowers. In addition, it forces us to evaluate how overall loan quality has been impacted in light of this trend. In addition, how tightly these trends are correlated will be evaluated in a heatmap in the section below.


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Weighted_LTV_vs_FICO_Plot.png"></p>
As you can see, the past decade has brought with it a trend toward higher loan to value ratios. In today's environment, borrowers can expect their home's value to appreciate substantially over the life of their loan. But this visual begins to show is that although today's crop of borrowers have better credit, they are forced to finance an every larger share of their home loan. This is due in large part to trends in the housing market, such as *historically low interest rates*. This is just one of the myriad delimmas facing lenders in this low interest rate environment. There is an accompanying heatmap correlation in the section below.


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Weighted_Interest_Rate_vs_LTV_Plot.png"></p>
As stated above, as interest rates have plummeted, loan to value ratios have begun to climb. We weighted the data in order to display the relationship between the two datapoints. In the heatmap correlation below, we unweight the data and *attempt to demonstrate* that there is in fact an inverse correlation.


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Investor_vs_Cashout_Plot.png"></p>
Cash-out refinances by investors were a another objective of ours. Our hypothesis was that real estate speculators such as house flippers would have caused the rate of cash-out refinances to increase. In the heatmap section below, we show that there is a correlation. But as the visual above demonstrates, the practice did not cause a massive spike in of cash-out refinance volume relative to the 2000s.


#### Seaborn Heatmaps
The second visual library we utilized is Seaborn, which allowed us to show the correlations between various elements of our dataset in the form of a heatmap. As you will see, all of our heatmaps by and large have the same range of 1 to -1. The 'hotter' one datapoint appears relative to another, the more they correlate. On the other hand, the closer a datapoint is to -1, the greater the inverse relationship relative to the other datapoint.


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Case-Schiller_vs_Interest_Rate_Heatmap.png"></p>
As you can see, there is an inverse correlation between home prices and interest rates. The surprising part is that it is not as pronounced as we predicted. There is definitely still a significant mathematical relationship. This likely means that interest rates are not in and of themselves a silver bullet. Other factors are at play, such as availability of housing stock.

<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Federal_Funds_Rate_vs_Interest_Rate_Heatmap.png"></p>
Here we see a much tigher positive correlation, albeit not a perfect one. This corroborates our findings above. To the average financial services professional, this may seem like common sense. However, we need to show that the data back up our assumptions. And in terms of our assumption regarding the impact of the Federal Reserve on interest rates, they do.


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Loan_Volume_vs_Interest_Rate_Heatmap.png"></p>
This finding is a bit more suprising. As you can see, there is a slight inverse correlation. However it is not as sharp as the corresponding plot above would have had you believe. That being said, a statistically significant relationship exists nonetheless.

<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/FICO_Score_vs_Interest_Rate_Heatmap.png"></p>
This finding is a bit more jarring. We already knew from the visual above that there is an inverse correlation between higher borrower FICO scores and lower interest rates. This heatmap reveals how acute that inverse correlation is. As we have now shown in 2 visuals, there is strong evidence that the current regulatory and lending environment benefits more well-heeled borrowers who have better credit. This is a far cry from the days of subprime lending nearly 2 decades ago. 


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Weighted_LTV_vs_FICO_Heatmap.png"></p>
Here we see a soft inverse correlation between borrower FICO scores and loan to value ratios. As the scientific maxim goes: "correlation does not imply causation." But it should give lenders a quick pause for concern. There is a modest correlation and as we saw in the visual above, borrower loan to value ratios, which represent the amount being lent versus the appraised value of the home are now higher than they were at the height of the housing bubble in the 2000s.


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Weighted_Interest_Rate_vs_LTV_Heatmap.png"></p>
And now for a moment of intellectual honesty. This finding actually challenges the main cusp of our argument. There is an inverse correlation of less and -.1 between interest rates and loan to value ratio. This might cause the reader to reject our findings, however I would urge them to consider our other findings with regard to increased loan to value ratios. What this tells us is that our assumptions may have been incorrect, but it further reinforces that there is a lopsided housing market in place. 


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Investor_vs_Cashout_Heatmap.png"></p>
This was actually a bit of a surprise as well. We were not expecting an inverse relationship between the occurance rate of cash out refinances and origination of loans for investor properties. Based on our research, cash out refinances are a popular tool among real estate investors to tap into the equity of their properties and finance improvements. More research is resquired in the future. Bear in mind that Federal Housing Finance Agency [has instituted a 7% cap on second homes and investment properties](https://www.housingwire.com/articles/white-house-aware-of-issues-over-investment-properties/), which may be playing a role here.


#### Secondary Axis Plots
The third visual library we implemented was Plotly Express which allowed us to show inverse correlations in stark review with secondary axis plots. As you can see, these plots have two Y-axes.  


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Debt_to_Income_Ratio_vs_FICO_Plot.png"></p>
As you can see from this chart, borrower FICO scores and loan to value ratios fluctuate on a fairly cyclical basis. They dip during the early 2010s following the 2008 meltdown and begin to climb throughout the last decade. It also shows that borrowers with better credit have been able to take advantage of historically low interest rates. In addition, it shows the inverse correlation between borrower FICO scores and loan to value ratios in sharper contrast than the seaborn heatmap above. 


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Number_of_Loans_Originated_vs_FICO_Plot.png"></p>
Here we see a tight correlation between loan volume and borrower FICO scores. What this tells us is that the borrowers who have who have been able to take advantage of low interest rates are those who have better credit and therefore in better financial shape. This comports with our findings above.

<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Case-Schiller_vs_Prapayment_Percentage_Plot.png"></p>
As you can see from this visual, there appears to be an inverse correlation between the case-schiller home price index and the rate at which loans are prepaid. This strikes at the heart of our hypothesis that an asset bubble is forming even though the borrower's in today's market are generally more financially well-off than those of the 2000s. 

### Part 3: APIs
We implemented two APIs as part of our analysis. They were Quandl for macroeconomic data and Alpaca for stock price data. In the jupyter lab notebook labeled 'DataAnalysis.ipynb,' we also used environmental variables for said APIs. Take note that in order to run our code, you will need to make sure the variable name in your (dot)env file matches the local variable called in our program so that the API key will be read. 
 
 #### Plots with the Quandl API
The first was the Quandl API to pull quartly data for the Case-Schiller Home Price Index and National Average Interest rates on a quarterly basis. We did this because increase our sample size within our 20-year time frame. This allowed us to verify the validity of our initial findings vis-a-vis single-family home prices and interest rates. 
 

<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Quandl_Quarterly_Case-Schiller_vs_Interest_Rate_Plot.png"></p>
By increasing our sample size, we were able to better show the inverse relationship between interest rates and home prices. The point of this was to satisfy the technical requirements with regard to APIs (Application Programming Interfaces) while also giving us a larger sample size. In this case, we pulled quarterly data as opposed to simply annual data. Regardless, this visual backs up our earlier findings in this area.


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Quandl_Quarterly_Case-Schiller_vs_Interest_Rate_Heatmap.png"></p>

We applied the same methodology with APIs to create a seaborn heatmap. It shows an inverse for the nominal home price index, but it is not as tighly correlated in terms of the real home price index. More research is required to clarify why this is so. Otherwise, this heatmap is nearly identical to our earlier seaborn heatmap above for interest rates and the case-schiller index.

#### Alpaca API & Montecarlo Simulations
Finally, we used the Alpaca API to pull daily stock price data for the four [largest mortgage backed security ETFs (exchange traded funds)](https://etfdb.com/etfdb-category/mortgage-backed-securities/) in order to run Montecarlo simulations. Mortgage backed securities (MBSs) are bundles of mortgages traded on financial markets that gained notoriety during the 2008 metldown. Montecarlo simulations allow us to simulate potential cummulative returns in the future based on past performance data. For our simulation, we composed a sample portfolio of the iShares MBS ETF (NASDAQ: MBB), the Vanguard Mortgage-Backed Securities ETF (NASDAQ: VMBS), the First Trust Low Duration Opportunities ETF (NASDAQ: LMBS) and the SPDR Portfolio Mortgage Backed Bond ETF (NYSEARCA: SPMB). We then weighted each of these assets equally and simulated their cumulative returns over the next 5-10 years based on past performance during the 2010s.


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Mortgage_Backed_Securities_ETF_Montecarlo_5_Year.png"></p>
This visual shows the simulated cumulative returns of a hypothetical portfolio containing an equal number of shares of the MBS ETFs listed above. As you can see, the cumulative returns over a 5 year period are well below 2 percent, which is the federal reserve's annual target rate for inflation. This is important because mortgage backed securities are a fixed-income financial product. This means that as interest rates fall, so do yields on MBSs.


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Mortgage_Backed_Securities_ETF_Montecarlo_10_Year.png"></p>
As you can see, even over a 10 year period, the returns are still less than 2 percent. We think that part of the reason for this trend is that lower interest rates lead to lower yields, which combined to increased loan volume places downward pressure on the price of MBSs. Unless interest rates increase, then we expect this trend to continue for the foreseable future.

### Conclusions:
- What is the impact of low interest rates on the housing market? 
As we have shown, low interest rates have lead directly to soaring asset prices. These rates have allowed well-heeled borrowers to compete for scarce housing stock which has sent prices soaring over the past few years. In every sense of the word, we have a runaway housing market. The momentum behind it has been building for quite some time. 

- What is the impact of low interest rates on loan quality overall?
We have also demonstrated that although overall borrower creditworthiness has increased, there is a concerning trend in loan to value ratio as well as debt to income ratio. This trend ties in directly to access to credit, which allows potential homebuyers to bid up the price of housing. This purchasing power comes at the expense of their initial equity in the property as well as the requirement to obtain mortgage insurance when the loan to value ratio exceeds 78 percent.

- What correlations exist between low interest rates and other data points?
We showed that there has been an uptick in loan volume. We also showed inverse correlations, such as borrower FICO scores. There is also a similar trend in rates of prepayment and interest rates overall.

- What is the impact of low interest rates on mortgage backed securities?
As we showed with our Montecarlo simulations, there is downward pressure on the price and return of MBSs. Lenders are making up for the lower interest rates by originating more loans. That may help them generate interest income for their institution as well as shareholders, but it also means that a higher proportion of lower yield MBSs are entering financial markets. Bear in mind, however, that the current yield on the 10 year T note is 1.5 percent.

### Recommendations:
- Enhance current underwriting standards by decreasing loan to value limits.
- Adjust debt to income limits in anticipation of a housing market correction.
- Limit relationship with real estate investors to mitigate adverse exposure to speculation based losses.
- Limit origination of cash out refinances in anticipation of correction which could leave borrowers underwater.

### Epilogue
At the outset of our project, we gave the fictitious financial institution we were making recommendations to the name "George Bailey Financial, N.A." It was an homage to the 1946 Frank Capra film *It's a Wonderful Life* starring Jimmy Stewart. In the film, Bailey runs a building and loan outfit that aids the residents of Bedford Falls in obtaining affordable home loan financing. Bailey's nemesis, Mr. Potter who operates a rival financial institution believes that Bailey's approach is irresponsible and financially unsound. When Bailey is shown a vision of what Bedford Falls would look like had he never been born. He is shocked when he sees that the town has been transformed into Pottersville. The town has no affordable housing developments and instead the residents are relegated to becomming Mr. Potter's tenants. In real life, low interest rates have also enabled hedge funds, private equity and [pension funds in search of higher yields to borrow money and snap up single-family housing](https://www.wsj.com/articles/if-you-sell-a-house-these-days-the-buyer-might-be-a-pension-fund-11617544801). The intent behind these purchases is to either rent them out to tenants or flip them. *Welcome to Pottersville...*



<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/pottersville.png"></p>

