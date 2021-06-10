# Project-1: The Story Behind the Real Estate Lending Cycle
#### Contributors: Jackie Bai, Rosalyn Brown & Thomas Scott

[INSERT ROSALYN BACKGROUND VISUAL SENT BY EMAIL]

#### Primary Libraries Used: Pandas, Matplotlib, Seaborn, Plotly Express & Bokeh

#### APIs Used: Quandl & Alpaca

### Project Description 
In this project, we sought to utilize datasets from Fannie Mae, the St. Louis Fed, Yale University as well as the trading platform Alpaca to present a clear picture of the mortgage industry since the beginning of the new millenium. We wanted to see whether today's lending environment resembled that of the 2000s, given that low interest rates preceded an asset bubble that finally burst in 2008. After that crisis, as well as during the pandemic; the Federal Reserve lowered interest rates through a program known as quantitative easing to stave off deflation. We wanted to see whether or not these low interest rates would in turn lead to another housing bubble in spite of enhanced underwriting standards on the part of lenders as well as agencies such as Fannie Mae and Freddie Mac.

### Executive Summary of Findings
What we found is that [we now have a K-shape housing boom](https://www.axios.com/housing-bubble-federal-reserve-intervention-1ac8151e-d8f3-4984-af23-23414932a32b.html). As we will show, tightened underwriting standards in concert with low interest rates and have lead to soaring single-family home prices, ushering in a highly competitive housing market in which only well-heeled qualifying buyers can be competitive. In addition, we observed that *low interest rates correlate directly to soaring single-family housing prices*, which in turn *lead to degraded loan quality* as well as *stagnating returns for mortgage backed securities*. What follows is a macroeconomic analysis explaining these findings.

### Key Objectives
Evaluate the following questions:
- What is the impact of low interest rates on the housing market?
- What is the impact of low interest rates on loan quality overall?
- What correlations exist between low interest rates and other data points?
- What is the impact of low interest rates on mortgage backed securities?

### Analysis Part 1: Preparing the Data
After downloading our data in CSV format from our various sources in CSV (comma separated value) format from the year 2000 through 2020. We then used the Pandas library to aggregate our data into a consolidated dataframe. Afterward, we cleaned it by dropping any null values and displaying the new dataframe to check our work. This portion of our project can be found in the notebook called 'DataClean.ipynb' in the solution directory. In addition, we reset the index several times in our 'DataAnalysis.ipynb' notebook. We recognize that it is duplicative, but it was a lot easier for us to call the initial combined dataframe and work with a different instance each time than worrying about alterations made to said dataframe as our code flows throughout the notebook. Ultimately, it comes down to individual programmming style in our opinion.

### Analysis Part 2: Data Visualization
Our data analysis notebook incorporates three primary visualization libraries in Python. They are: Matplotlib, Seaborn and Plotly Express. The resulting visuals are shown in sequential order below and arranged by visualization library. Bear in mind that we did not use every visual generated in the 'DataAnalysis.ipynb' file for presentation purposes.

.center {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 50%;
}

#### Matplotlib Area & Line Plots
The first visualization libarary we used is Matplotlib, which allowed us to create area and line plots to display trends in our data. 

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Case-Schiller_vs_Interest_Rate_Plot.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Federal_Funds_Rate_vs_Interest_Rate_Plot.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Loan_Volume_vs_Interest_Rate_Plot.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/FICO_Score_vs_Interest_Rate_Plot.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Weighted_LTV_vs_FICO_Plot.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Weighted_Interest_Rate_vs_LTV_Plot.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Investor_vs_Cashout_Plot.png" class="center">


#### Seaborn Heatmaps
The second visual library we utilized is Seaborn, which allowed us to show the correlations between various elements of our dataset in the form of a heatmap. As you will see, all of our heatmaps by and large have the same range of 1 to -1. 

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Case-Schiller_vs_Interest_Rate_Heatmap.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Federal_Funds_Rate_vs_Interest_Rate_Heatmap.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Loan_Volume_vs_Interest_Rate_Heatmap.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/FICO_Score_vs_Interest_Rate_Heatmap.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Weighted_LTV_vs_FICO_Heatmap.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Weighted_Interest_Rate_vs_LTV_Heatmap.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Investor_vs_Cashout_Heatmap.png" class="center">

#### Secondary Axis Plots
The third visual library we implemented was Plotly Express which allowed us to show inverse correlations in stark review with secondary axis plots. As you can see, these plots have two Y-axes.  

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Debt_to_Income_Ratio_vs_FICO_Plot.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Number_of_Loans_Originated_vs_FICO_Plot.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Number_of_Loans_Originated_vs_LTV_Plot.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Case-Schiller_vs_Prapayment_Percentage_Plot.png" class="center">


### Analysis Part 3: APIs
 We implemented two APIs as part of our analysis. The first was the Quandl API to pull quartly data for the Case-Schiller Home Price Index and National Average Interest rates on a quarterly basis. We did this because increase our sample size within the time frame in question to verify the validity of our initial findings with regard to interest rates vis-a-vis single-family home prices. In the jupyter lab notebook labeled 'DataAnalysis.ipynb' we also use environmental variables for said APIs. Take note that in order to run these, you will need to make sure the variable name in your (dot)env file matches the one called in the program so that the key will be read by our program. 
 
 #### Quandl
<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Quandl_Quarterly_Case-Schiller_vs_Interest_Rate_Plot.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Quandl_Quarterly_Case-Schiller_vs_Interest_Rate_Heatmap.png" class="center">

#### Alpaca API & Montecarlo Simulations
Finally, we used the Alpaca API to pull daily stock price data for the four [largest mortgage backed security ETFs (exchange traded funds)](https://etfdb.com/etfdb-category/mortgage-backed-securities/) in order to run Montecarlo simulations. Montecarlo simulations allow us to simulate potential cummulative returns in the future based on past data. For our simulation, we composed a sample portfolio of the iShares MBS ETF (NASDAQ: MBB), the Vanguard Mortgage-Backed Securities ETF (NASDAQ: VMBS), the First Trust Low Duration Opportunities ETF (NASDAQ: LMBS), the SPDR Portfolio Mortgage Backed Bond ETF (NYSEARCA: SPMB). We then weighted each of these assets equally and simulated their cumulative returns over the next 5-10 years based on past performance during the 2010s.

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Mortgage_Backed_Securities_ETF_Montecarlo_5_Year.png" class="center">

<img src="https://raw.githubusercontent.com/ThomasJScott3/Housing-Market-Project-1/main/Images/Mortgage_Backed_Securities_ETF_Montecarlo_10_Year.png" class="center">

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
- Maintain current underwriting standards and seek out ways to optimize them to suit the current market environment.
- Continue to monitor cash out refinances and loans on investment properties.
- Seek out ways to enhance returns on mortgage backed securities in a low interest rate environment
- Evaluate ways to improve access to financing for middle-income borrowers without compromising the bank's overall portfolio.
- ELABORATE FURTHER


