# Cryptocurrencies
 Module 18

## Project Overview

You and Martha have done your research. You understand what unsupervised learning is used for, how to process data, how to cluster, how to reduce your dimensions, and how to reduce the principal components using PCA. It’s time to put all these skills to use by creating an analysis for your clients who are preparing to get into the cryptocurrency market.

Martha is a senior manager for the Advisory Services Team at Accountability Accounting, one of your most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked you to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data Martha will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what Martha is looking for, she has decided to use unsupervised learning. To group the cryptocurrencies, Martha decided on a clustering algorithm. She’ll use data visualizations to share her findings with the board.

### Technologies Used: 
* Jupyter Notebook
* CryptoCompare comparison data (crypto_data.csv)
* Pandas Library
* Scikit-learn Library
* Plotly and Plotly-Express Libraries
* hvPlot Library

## Deliverable 1: Preprocessing the Data for PCA
To preprocess the data, I first loaded the crypto_data.csv dataset using the following code: 

<img width="637" alt="Screen Shot 2022-05-17 at 10 41 51 AM" src="https://user-images.githubusercontent.com/96043107/168852454-0a73311d-7e39-4a78-9f8e-ff235d87f771.png">

Next, I kept all cryptocurrencies being traded and have a working algorithm. I also removed the "IsTrading" column, and any rows that have at least one null value. Next, I kept rows where coins are mined, and created a new DataFrame that holds just the cryptocurrencies names, and deropped the 'CoinName' column from the crypto_df dataframe since it won't be used in the clustering algorithm. The following image is the resulting crypto_df dataframe, with 532 rows and 4 columns. 

<img width="813" alt="Screen Shot 2022-05-17 at 10 45 21 AM" src="https://user-images.githubusercontent.com/96043107/168853278-dde9fd39-02e7-46e3-a386-ddca598a5a5a.png">

I finally used the get_dummies() function to create variables for text features and standardized the data with the StandardScaler() function. 

## Deliverable 2: Recuding Data Dimensions Using PCA
Using PCA to reduce dimension to the three principal components was completed with the following code: 

<img width="650" alt="Screen Shot 2022-05-17 at 10 47 25 AM" src="https://user-images.githubusercontent.com/96043107/168853770-16e86be9-10ce-42a7-b445-5081b50156a8.png">

I then created a DataFrame with the three principal components, using the following code: 

<img width="655" alt="Screen Shot 2022-05-17 at 10 48 13 AM" src="https://user-images.githubusercontent.com/96043107/168853927-bb35a8ec-7c99-4e32-a412-c3f3763cb6fc.png">

## Deliverable 3: Clustering Cryptocurrencies Using K-means
Finding the best value for <k> using the elbow curve entails the following code structure: 

<img width="647" alt="Screen Shot 2022-05-17 at 10 49 02 AM" src="https://user-images.githubusercontent.com/96043107/168854072-421c4235-9bef-44a0-b2f4-f575ef257b83.png">
 
I then initalized the k-means model, fit the model, and predicted clusters with the following code: 
 
 <img width="650" alt="Screen Shot 2022-05-17 at 10 50 09 AM" src="https://user-images.githubusercontent.com/96043107/168854296-e39af350-82cb-45ef-a1dc-c80687b03c5a.png">

A new DataFrame was created that combined predicted clusters and crpytocurrencies, concentrating the crypto_df and pc_df DataFrames onto the same columns. Also, a new column, "CoinName" is added to the clustered_df DataFRame that contains cryptocurrency names. Next, another new column, "Class" is added to the clustered_df Dataframe that contains the predictions. The new clustered_df DataFrame appears as the following: 
 
 <img width="979" alt="Screen Shot 2022-05-17 at 10 53 22 AM" src="https://user-images.githubusercontent.com/96043107/168854963-2ab2889c-d80d-4f97-9f01-24bf269922d9.png">


## Deliverable 4: Visualizing Cryptocurrencies Results

3D-Scatter with Clusters-
The PCA and cluster data is used to plot clusters with three features with the following code: 
 
 <img width="646" alt="Screen Shot 2022-05-17 at 10 55 37 AM" src="https://user-images.githubusercontent.com/96043107/168855422-fcb555d6-9218-4c69-984d-e457502bff68.png">

The result of the code produced the following 3D-Scatter image: 
 
 <img width="536" alt="Screen Shot 2022-05-17 at 10 56 42 AM" src="https://user-images.githubusercontent.com/96043107/168855681-5b60ef70-2507-49d7-a1c3-1c51ee90fc16.png">

Lastly, a new table was created for tradable cryptocurrencies using the hvplot function. This table resulted in 532 tradable cryptocurrency items. Next, I scaled the data to create the scatter plot for tradable cryptocurrencies. Lastly, a new DataFrame was created with the scaled data and clustered_df DataFrame index. The previous "CoinName" and "Class" columns were added from the clustered_df DataFrame to the new plot_df DataFrame. The new plot_df dataframe looks like the following: 
 
 <img width="391" alt="Screen Shot 2022-05-17 at 11 00 14 AM" src="https://user-images.githubusercontent.com/96043107/168856439-70b31b12-4467-4b09-b7f0-45493651a2a3.png">

Finally, a scatter hvplot is created where x="TotalCoinsMined" and y="TotalCoinSupply". 
 
 <img width="1005" alt="Screen Shot 2022-05-17 at 11 01 19 AM" src="https://user-images.githubusercontent.com/96043107/168856642-aaa3c8ad-42f0-4d89-b8ca-6d293ede8b2d.png">


 
