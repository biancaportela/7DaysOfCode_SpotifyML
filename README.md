# 7DaysOfCode_SpotifyML

- ⚡ This GitHub repository contains code and resources for [Alura's Challenge](https://7daysofcode.io/matricula/machine-learning), a project that analyzes Spotify data and predicts song popularity using Python and Machine Learning. 


- 🔭 The challenge during 7DaysOfCode is to improve my skills in data manipulation, visualization, and analysis using Machine Learning. The main goal is to analyze Spotify data and apply Machine Learning techniques to predict the popularity of songs. To achieve this, I will go through different stages of a Machine Learning project, including data collection, exploratory analysis, and model validation.

- [Dataset](https://www.kaggle.com/datasets/maharshipandya/-spotify-tracks-dataset?utm_source=ActiveCampaign&utm_medium=email&utm_content=%237DaysOfCode+-+Machine+Learning+1%2F7%3A+Coleta+de+dados+e+An%C3%A1lise+Explorat%C3%B3ria&utm_campaign=%5BAlura+%237Days+Of+Code%5D%28Js+e+DOM+-+3%C2%AA+Ed+%29+1%2F7)
- [Data Dictionary](https://github.com/biancaportela/7DaysOfCode_SpotifyML/blob/main/data/data_dictionary.md)

- [Final project](https://github.com/biancaportela/7DaysOfCode_SpotifyML/blob/main/projeto_final.ipynb)

## Summary

The topic I am exploring is Hit Song Science (HSS), which is a research field that focuses on predicting the success of songs before they are released in the market. HSS is a sub-area of Music Information Retrieval (MIR), which involves gathering information from songs [(ARAUJO, CRISTO AND GIUST, 2020)](https://seer.ufrgs.br/rita/article/view/RITA_VOL27_NR4_108). Pachet and Roy mentioned in their paper [“Hit Song is Not Yet a Science”](https://ismir2008.ismir.net/papers/ISMIR2008_133.pdf) that the idea behind HSS is that cultural items, such as songs, have specific technical features that make them preferred by a majority of people. These features can be extracted using algorithms to automate the prediction process for new songs.

The problem I am trying to solve is to predict the popularity of songs and artists. I want to develop data-driven models that can accurately forecast the success of songs and artists on music streaming platforms like Spotify. By leveraging data and insights, I aim to help musicians and record labels make informed decisions about which songs and artists to promote, invest in, and potentially collaborate with. This can help them optimize their marketing strategies, allocate resources effectively, and increase their chances of success in a highly competitive music industry. I analyzed a Spotify database of over 100,000 songs and conducted a basic EDA to identify trends. I observed that the top 25% of the distribution had small scores - 50 out of 100 - indicating that the dataset was skewed towards less popular songs. I also identified hidden duplicates and dropped them to increase the number of observations to over 80,000.

| | count	    | mean	    |     std	  |  min	 |  25%	      |   50%	    |   75%	  |   max   |
|-----------|-----------|-----------|-----------|--------|------------|-----------|---------|---------|
popularity	| 113549.0	| 33.324433	| 22.283855 |	0.0000 |	17.000000 |	35.000000 |	50.0000 |	100.00000

<p float='center'>
  <img src='https://github.com/biancaportela/7DaysOfCode_SpotifyML/blob/main/pictures/mean_popularity.png?raw=true'>
</p>
  
The modeling process involved testing several baseline models, including Dummy Classifiers and Logistic Regression. To address the issue of imbalance in the dataset and further improve the model's performance, resampling techniques were applied and SMOTE was found to be the most effective. The performance of different models, including Logistic Regression, KNN, Decision Tree, Random Forest, and XGBoost, were compared and Random Forest was selected as the best performer. The model was further optimized through hyperparameter tuning using Random Search and Grid Search.

<p float='center'>
  <img src='https://github.com/biancaportela/7DaysOfCode_SpotifyML/blob/main/pictures/smote_metrics.png?raw=true'>
</p>

To evaluate the models, a cross-validation method with 5 folds was employed, and the model was finally trained on a test set to assess its ability to generalize. The precision score was found to be ~0.11 and the F1-Score was ~0.13, which were low but expected given the complexity of the factors that influence the popularity of a song, many of which are related to behavioral and emotional factors that could not be fully explored in this dataset. Similar discussions are found in other research papers on Hit Song Science, such as the previously cited "Hit Song Science is Not Yet a Science".

|           | Random Forest Prediction |
|-----------|--------------------------|
| Accuracy  |   0.9406619121907733     |
| Precision |   0.11456859971711457    |
| Recall    |   0.15576923076923077    |
| F1-Score  |  0.13202933985330073     |

These steps are recommended for further improvement in the project:

   - Conducting a more detailed feature selection process: This involves considering categorical features such as genre and artists, which may have a significant influence on the popularity of a song. Performing frequency encoding on these columns can help capture their information, and further analysis such as feature importance or correlation analysis can aid in selecting the most relevant features for the model.

   - Reducing dimensionality of the data through PCA analysis: Principal Component Analysis (PCA) is a dimensionality reduction technique that can help capture the most important information from a large number of features. By reducing the dimensionality of the data, the model may benefit from a more focused and relevant set of features, which could improve its performance.
   
By incorporating these steps into the project, it may be possible to improve the precision and performance of the model, and gain deeper insights into the factors that influence the popularity of songs.

You can find the detailed analysis and code [here](https://github.com/biancaportela/7DaysOfCode_SpotifyML/blob/main/projeto_final.ipynb)

### 7 days of code through the days

|       | Main Goal   | Status | Completed day | 
|-------|--------------|--------|----------------|
| Day One | Data Collection and EDA   | ✔️    | 12-04-2023       | 
| Day Two  | Pre-processing  | ✔️    | 13-04-2023         | 
| Day Three  | Splitting the data | ✔️      | 14-04-2023         | 
| Day Four   | Machine Learning Models     |  ✔️     | 15-04-2023        |
| Day Five   | Evaluation  | ✔️      | 16-04-2023          | 
| Day Six   | Resampling  | ✔️      | 19-04-2023          | 
| Day Seven   | Prediction | ✔️      | 19-04-2023         |
