# Time-Series-Data-Analysis
Exploratory Data Analysis on Financial data
Exploratory Data Analysis is a group of techniques used by data scientist to investigate, analyze and visualize the data set by summarizing main features of a dataset.  EDA encompasses a larger venue that is primarily used to grasp what data can disclose beyond the hypothesis testing and gives us a better understanding of data, its variables and the relationship between them. EDA is an approach to data analysis help to determine which statistical techniques should include for data analysis. EDA is not identical to statistical graphics although the EDA consists of all statistical fitness tests. Most EDA techniques are graphical in nature with a few statistical techniques. The reason for the heavy reliance on graphics is to produce interpretable, visually appealing insights for the audience of interest.

In this paper we have presented some graphical tools in python that could be useful for drawing conclusions and provide input to dashboard and model selection approach.

We have provided with a dataset of Level 1 Stock Prices for Coca-Cola the given data file was in text file format. Initially dataset contained 14 columns and 864,733 Rows which we further reduced to 10 columns, 63390 rows and added 3 more.

Feature to dataset which are as follows:
	
  DATE_TIME and EST: This feature is for specifying the timeline for the period in which stocks happened. It was not EST hence we converted original column of DATE_TIME to EST column by using pandas. The data type for the EST column is ‘datetime’

	BID and BID Size: It is price that buyers are willing to pay for an asset and Bid size represents the quantity of the willingness to purchase at a specified bid price. for level 1 quotes data the bid size is the number of shares that the investors are willing to purchase at the best available bid price.

	OFR and OFRSIZ:  It is price that sellers are want for their asset. The offer or ask size is the amount that a market maker is offering to sell. OFRSIZ is the quantity shares that market makers are willing to sell at best price. The higher the ask size, the more people want to sell. Level 1 quotations data will only show the OFR size for the best available OFR price.

	PRICE and SIZE: The price or closing price is the raw price of the last transacted before the market officially closes for normal trading. It is often uses as a reference point by investors to compare a stock's performance.

	Exchanges (EX): An exchange is a marketplace where sellers pay the market to have a platform to sell their assets. Buyers come to such marketplace to buy from those sellers. Such marketplaces provide benefit for both buyers and sellers. In our data we have 15 unique exchanges they are ‘NYS' 'ADF' 'BAT' 'DEX' 'MMX' 'PSE' 'IEX' 'THM' 'DEA' 'BOS' 'ASE' 'BTY' 'XPH' 'CIN' 'MPE' 'MID'. Out of these 15 we randomly picked ADF Exchange for further analysis.

	Return: It is a financial term for the money made or lost on an investment over some time. Meaning when you put money in the stocks you expect to get back more that is a positive return also known as profit while if you get less than what you have put in the market then it is a negative return that is a loss for investors.

Importing the relevant libraries:
	Used Pandas library for data manipulations
	Numpy for array manipulations
	Scipy for computing statistics fit tests 
	Matplotlib for creating not just visually appealing but informative graphs  

Hurst Exponent:
The Hurst exponent is use to measure of long-term memory of a time series. the Hurst coefficient gages the relative tendency that is randomness of the time series. Meaning it gives us an idea of whether the time series is a random walk or some trend. A value H in the range 0.5–1 indicates a time series with long-term positive autocorrelation, meaning high values in the series will most probably follow by another high values.
When our data was plotted estimated to be H= 0.53 – a Hurst exponent close to 0.5 is indicative of a ‘Brownian time series’

Visualizing Daily Stock Returns
	Use the plot method to create a line plot to show the daily percentage change of the adjusted close price. From the line plot, we can see the daily returns are volatile and the values oscillate between positive and negative zones
	The histogram shows that the daily returns are mostly distributed around -5% to 5%. 
	In measuring investment risk, we expect our daily returns are following the positive skew pattern or positive value that is 0 .36. This is because more than half of the daily returns are above mean in a positive skew distribution. 
	Zero skewness indicates the normal distribution of the probability a function.
	Then we calculated the variance of returns. The higher variance indicates the higher volatility of the stock price and hence the risk is higher.

Kurtosis 
Skewness is a measure for asymmetry of a symmetry. It shows weather the data looks the same to right and left of a center point of histogram. Whereas Kurtosis is used in further investigation about the data distribution. It is technique that gages whether the data are heavy-tailed or light-tailed relative to a normal distribution. 
In terms of investment, a high kurtosis for the financial return distribution means that the investor might experience instant and extreme results that is positive or negative returns. This can be more extreme than the usual three standard deviations from the mean of the normal distribution and the phenomenon is called as kurtosis risk. The resulting kurtosis value is high for our data which means an investor might experience a high kurtosis risk.

Calculation for Kurtosis
Kurt(X)=E[((X - μ)/σ)^4  ] =14.9  (excess)

                                                           Kurt(X)-3=11.9  (real)   

