# Project-1: The Story Behind the Real Estate Lending Cycle
#### Contributors: Jackie Bai, Rosalyn Brown & Thomas Scott

[INSERT ROSALYN BACKGROUND VISUAL SENT BY EMAIL]

#### Primary Libraries Used: Pandas, Matplotlib, Seaborn, Plotly Express & Bokeh

#### APIs Used: Quandl & Alpaca

### Project Description 
In this project, we sought to utilize datasets from Fannie Mae (loan origination & performance data), the St. Louis Fed (case-schiller index & national average 30-year interest rates), the economic data repository Quandl (quartly interest rate & case-schiller data) as well as the trading platform Alpaca (mortgage backed security perfomance data) to present a clear picture of the mortgage industry since the beginning of the new millenium. We wanted to see whether today's lending environment resembled that of the 2000s, given that low interest rates preceded an asset bubble that finally burst in 2008. After that crisis, as well as during the pandemic; the Federal Reserve lowered interest rates through a program known as quantitative easing to stave off deflation. We wanted to see whether or not these low interest rates would in turn lead to another housing bubble in spite of enhanced underwriting standards on the part of lenders as well as agencies such as Fannie Mae and Freddie Mac.
 
### Executive Summary of Findings
What we found is that [we now have a K-shape housing boom (source: Axios)](https://www.axios.com/housing-bubble-federal-reserve-intervention-1ac8151e-d8f3-4984-af23-23414932a32b.html). As we will attempt to show, tightened underwriting standards in concert with low interest rates and have lead to soaring single-family home prices, ushering in a highly competitive housing market in which only well-heeled qualifying buyers can be competitive. In addition, we attempt to argue that *low interest rates correlate directly to soaring single-family housing prices*, which in turn *lead to degraded loan quality* as well as *stagnating returns for mortgage backed securities*. What follows is a macroeconomic analysis explaining our findings.

### Key Objectives
Evaluate the following questions:
- What is the impact of low interest rates on the housing market?
- What is the impact of low interest rates on loan quality overall?
- What correlations exist between low interest rates and other data points?
- What is the impact of low interest rates on mortgage backed securities?

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
Cash-out refinances by investors were a secondary objective of ours. Our hypothesis was that real estate speculators such as house flippers would have caused the rate of cash-out refinances to increase. In the heatmap section below, we show that there is a correlation. But as the visual above demonstrates, the practice did not cause a massive spike in of cash-out refinance volume relative to the 2000s.


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
This was actually a bit of a surprise as well. We were not expecting an inverse relationship between the occurance rate of cash out refinances and origination of loans for investor properties. Based on my research, cash out refinances are a popular tool among real estate investors to tap into the equity of their properties and finance improvements. More research is resquired in the future. Bear in mind that Federal Housing Finance Agency [has instituted a 7% cap on second homes and investment properties](https://www.housingwire.com/articles/white-house-aware-of-issues-over-investment-properties/), which may be playing a role here.


#### Secondary Axis Plots
The third visual library we implemented was Plotly Express which allowed us to show inverse correlations in stark review with secondary axis plots. As you can see, these plots have two Y-axes.  


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Debt_to_Income_Ratio_vs_FICO_Plot.png"></p>

<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Number_of_Loans_Originated_vs_FICO_Plot.png"></p>

<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Number_of_Loans_Originated_vs_LTV_Plot.png"></p>

<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Case-Schiller_vs_Prapayment_Percentage_Plot.png"></p>


### Part 3: APIs
We implemented two APIs as part of our analysis. They were Quandl for macroeconomic data and Alpaca for stock price data. In the jupyter lab notebook labeled 'DataAnalysis.ipynb,' we also used environmental variables for said APIs. Take note that in order to run our code, you will need to make sure the variable name in your (dot)env file matches the local variable called in our program so that the API key will be read. 
 
 #### Plots with the Quandl API
The first was the Quandl API to pull quartly data for the Case-Schiller Home Price Index and National Average Interest rates on a quarterly basis. We did this because increase our sample size within our 20-year time frame. This allowed us to verify the validity of our initial findings vis-a-vis single-family home prices and interest rates. 
 
 
<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Quandl_Quarterly_Case-Schiller_vs_Interest_Rate_Plot.png"></p>

<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Quandl_Quarterly_Case-Schiller_vs_Interest_Rate_Heatmap.png"></p>

#### Alpaca API & Montecarlo Simulations
Finally, we used the Alpaca API to pull daily stock price data for the four [largest mortgage backed security ETFs (exchange traded funds)](https://etfdb.com/etfdb-category/mortgage-backed-securities/) in order to run Montecarlo simulations. Montecarlo simulations allow us to simulate potential cummulative returns in the future based on past performance data. For our simulation, we composed a sample portfolio of the iShares MBS ETF (NASDAQ: MBB), the Vanguard Mortgage-Backed Securities ETF (NASDAQ: VMBS), the First Trust Low Duration Opportunities ETF (NASDAQ: LMBS) and the SPDR Portfolio Mortgage Backed Bond ETF (NYSEARCA: SPMB). We then weighted each of these assets equally and simulated their cumulative returns over the next 5-10 years based on past performance during the 2010s.


<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Mortgage_Backed_Securities_ETF_Montecarlo_5_Year.png"></p>

<p align="center"><img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Mortgage_Backed_Securities_ETF_Montecarlo_10_Year.png"></p>

### Conclusions:
- What is the impact of low interest rates on the housing market? 
ANSWER HERE

- What is the impact of low interest rates on loan quality overall?
ANSWER HERE

- What correlations exist between low interest rates and other data points?
ANSWER HERE

- What is the impact of low interest rates on mortgage backed securities?
ANSWER HERE

### Recommendations:
- Enhance current underwriting standards by decreasing loan to value limits.
- Adjust debt to income limits in anticipation of a housing market correction.
- Limit relationship with real estate investors to mitigate adverse exposure to speculation based losses.
- Limit origination of cash out refinances in anticipation of correction which could leave borrowers underwater.
- ELABORATE FURTHER


