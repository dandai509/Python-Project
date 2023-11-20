# Python Project- New Zealand GDP Forecasting
## Business Problem 
As a data scientist who works for Global Consulting Group, I was approached by a client who wants to know if NZ’s economy will continue growing next year. Therefore he can safely invest his business in the country. My goal is to build up a Machine learning model to predict future GDP.  In this project, time series model and linear regression model are used and compared, and result and recommendations are delivered to our clients based on the analysis findings.
## Data Preparation 
Data was initially selected from the World Bank from 1972-2021, after data mining and cleaning. Null values are eliminated. Below is the data we use for EDA visualization.
![1](https://github.com/dandai509/Python-Project/assets/106848444/d1381326-c2db-4b7f-8aa4-01c1eaa5af12)
![2](https://github.com/dandai509/Python-Project/assets/106848444/cd21db8e-4893-4200-9d66-93360ca2611d)
## Data Analysis 
Overall, NZ had a stable growth of GDP from the 1970s, it doubled from 5 billion in 2000 to 10 Billion in 2003, and doubled again from 2003-2013. Only negative growth in 2008 due to financial crisis and 2020 due to Covid 19.
![Picture4](https://github.com/dandai509/Python-Project/assets/106848444/7e61af56-dec1-43af-83f9-39ed542c5ac2)
![Picture5](https://github.com/dandai509/Python-Project/assets/106848444/dd7c9ae4-a749-4deb-ad7c-643750764ebb)

New Zealand’s GDP growth heavily relies on the service sector, the agriculture and Manufacturing sector has a steady but insignificant growth over the 50 years. The factors that affect GDP growth the most. Manufacture, service, and Agriculture consumption have the highest correlation with Total GDP. And Inflation and Unemployment have a negative correlation with GDP.
![Picture6](https://github.com/dandai509/Python-Project/assets/106848444/efacb26b-ff64-44e3-bbc2-f6fe24c22d66)
![Picture7](https://github.com/dandai509/Python-Project/assets/106848444/f5e68af4-df93-49a6-828c-2ee0cd29183d)
## Machine Learning Modell
### ARIMA Model
Because the nature of the data is historical, we chose ARIMA(Autoregressive Integrated Moving Average) model to forecast the future GDP of NZ. The limitations are that data needs to be Stationary and non-seasonal. We use ADF test to test the null hypothesis to determine if the data is stationary. Results are below.
![Picture8](https://github.com/dandai509/Python-Project/assets/106848444/e22e3ec6-df13-41d1-a82e-af960bf3f0d9)
![Picture8-1](https://github.com/dandai509/Python-Project/assets/106848444/e5f0818b-e694-4b0a-9f62-6f676e73cb64)

Original data is non-stationary, we applied Log Transfer and First Order difference to the data, and it became stationary.
![Picture9](https://github.com/dandai509/Python-Project/assets/106848444/5ff451cc-7319-4fe7-81d4-fa3f95ba7d26)
![Picture9-1](https://github.com/dandai509/Python-Project/assets/106848444/f34fea78-db88-44c4-971f-7b81cbdec0ac)

We also used ARIMAL model tuning using parameters p,q,d, and used Autocorrelation and Partial Autocorrelation chart to find out the value of p,q,d. ( details see coding)
![Picture10](https://github.com/dandai509/Python-Project/assets/106848444/a02d7255-9a8b-4c9c-b002-1e04271a2b47)
![Picture11](https://github.com/dandai509/Python-Project/assets/106848444/abb738a0-8f0d-457b-b93f-a9e02762ccfa)
Finally, I used time series train-test-split cross-validation, default 5 splits was used. The forecasting is shown in the below chart. 

![Picture12](https://github.com/dandai509/Python-Project/assets/106848444/4c20e6a8-b358-47c1-a191-4fb18090ea0b)
### Regression Model
I then used linear regression model, all variables were used except year, all features were selected, data normalised, train and test the database on a 30% split, The result is shown below with an RMSE Value 77%.
![Picture13](https://github.com/dandai509/Python-Project/assets/106848444/da718829-cc8b-4b5e-b488-1b54abf0fa8c)
## Summary
NZ' GDP is expected to keep on growing above 5% in next couple of years, variety of factors that affects the growth of GDP including Services, consumption, agriculture sector. Both ARIMA and Linear regression models can be used to predict GDP growth. Linear regression model has outperformed ARIMA model with a Smaller RMSE value. Invest in the service sector as it is highly correlated to GDP, you would expect a similar return of at least 5%.






