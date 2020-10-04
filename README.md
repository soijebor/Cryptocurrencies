# Cryptocurrencies

## ***Project Overview***

  * Describe the differences between supervised and unsupervised learning, including real-world examples of each.
  * Preprocess data for unsupervised learning.
  * Cluster data using the K-means algorithm.
  * Determine the best amount of centroids for K-means using the elbow curve.
  * Use PCA to limit features and speed up the model.
  
## ***Resources***

  * Data Source: iris.csv, shopping_data.csv, crypto_data.csv
  * Software: Python 3.7.6, Anaconda 4.8.4, Jupyter Notebook 6.0.3
  
## ***Challenge Overview***

A senior manager for the Advisory Services Team at Accountability Accounting, one of your most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrencies investment portfolio for its customers. The company, however, is lost in the immense universe of cryptocurrencies and asks me to present a report of what cryptocurrencies are on the trading market and how cryptocurrencies could be grouped toward creating a classification for developing this new investment product.

  * Prepare the data for dimensions reduction with PCA and clustering using K-means.
  * Reduce data dimensions using PCA algorithms from sklearn.
  * Predict clusters using cryptocurrencies data using the K-means algorithm form sklearn.
  * Create some plots and data tables to present your results.
 
## ***Challenge Summary***

1.) ***Data Preprocessing***

 I started by loading the data into a panda Dataframe, then i followed the following data preprocessing tasks:

   * Remove all cryptocurrencies that aren’t trading.
   * Remove all cryptocurrencies that don’t have an algorithm defined.
   * Remove the IsTrading column.
   * Remove all cryptocurrencies with at least one null value.
   * Remove all cryptocurrencies without coins mined.
   * Store the names of all cryptocurrencies on a DataFramed named coins_name, and use the crypto_df.index as the index for this new DataFrame.
   * Remove the CoinName column.
   * Create dummies variables for all of the text features, and store the resulting data on a DataFrame named X.
   * Use the StandardScaler from sklearn to standardize all of the data from the X DataFrame. 

2.) ***Reducing Data Dimensions Using PCA***

Reduced the dimensions of the X DataFrame down to three principal components using the PCA algorithm from sklearn. Then, I created a DataFrame named “pcs_df” that includes the following columns: PC 1, PC 2, and PC 3. I used the crypto_df.index as the index for this new DataFrame.

3.) ***Clustering Cryptocurrencies Using K-means***
 
Using the KMeans algorithm from sklearn to cluster the cryptocurrencies using the PCA data. I completed the following tasks:
   
   * Create an elbow curve to find the best value for K, and use the pcs_df DataFrame.

   ![](https://github.com/soijebor/Cryptocurrencies/blob/master/Charts/elbow_curve.png)
   From the chart we can tell the best value for K is 4

   * After I defined the best value for K, I used the pcs_df dataframe to run the K-means algorithm to predict the K clusters for the cryptocurrencies’ data as shown below

   ![]()

   * Then I created a new DataFrame named “clustered_df,” that includes the following columns: Algorithm,ProofType, TotalCoinsMined, TotalCoinSupply, PC 1, PC 2, PC 3, CoinName, and Class.

 4.) ***Visualizing Results***
 
   * Created a 3D scatter plot using Plotly Express to plot the clusters using the clustered_df DataFrame. And included the following parameters on the plot: hover_name="CoinName" and hover_data=["Algorithm"] to show this additional info on each data point.
   
   ![](https://github.com/soijebor/Cryptocurrencies/blob/master/Charts/newplot.png)
   
   * Used hvplot.table to create a data table with all the current tradable cryptocurrencies, which has the following columns: CoinName, Algorithm, ProofType, TotalCoinSupply, TotalCoinsMined, and Class.
    
   ![](https://github.com/soijebor/Cryptocurrencies/blob/master/Charts/clustered_df_table.png)
    
   * Created a scatter plot using hvplot.scatter to present the clustered data about cryptocurrencies having x="TotalCoinsMined" and y="TotalCoinSupply" to contrast the number of available coins versus the total number of mined coins and used the hover_cols=["CoinName"] parameter to include the cryptocurrency name on each data point.
   
   ![](https://github.com/soijebor/Cryptocurrencies/blob/master/Charts/scatter_clustered.png)
   
   For a clearer view of the y-axis i increased the height to 3000 which gives it a reasonable view
   
   ![]()
