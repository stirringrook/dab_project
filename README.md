# Market Basket Analysis Project
The code for this work is presented in two separate files

## 1. clean_up.ipynb
Contains steps on preprocessing the data, renaming data fields, deciding on which data to use.

Also, some explanatory dashboards are constructed in that file - overviewing the dataset composition, distribution of sales data by days of the week and hours of the day
## 2. clusterization.ipynb
This section of code begins with ___creating new features___ explaining the sales data, grouping them by clients. Then, it proceeds to perform ___outlier filtering___, keeping only clients that do not belong to the top and bottom 10th percentile by metrics like average bill paid or amount of orders made. This approach has shown significant impact on the further analysis, as some extreme-behaviour buyers made impact on the clusterization, even though there are more than 100,000 clients overall.

Then, project proceeds with ___encoding___ the top-level of hierarchical division of the items with One-Hot-Encoding, and then ___scaling___ the previously generated features.

Then, multiple ___clusterization___ algorithms are tested to find the best ___number of clusters___, and the best algorithm to use further.

___K-Means Algorithm with 6 clusters___ then is chosen as the best performing one, with DBSCAN and EM Algorithm(Gaussian-Mixture) not being able to deliver enough reduction in uncertainty.

Then, the cosmetics begin, with providing ___profiling___ analysis, showing distributions of metrics across customers from different clusters, their composition, profitability for the company and usual categories of items they purchase.

Finally, ___Market Basket Analysis___ is carried out, using both _Apriori_ and _FP-Growth_ algorithms to find the best antecedent-consequence pairs(rules). It turns out, two of the 6 clusters do not have rules that are statistically significant, but there is nothing that can be done about that - after all, this project is a research of the given data, and in this case, the whole analysis process proved to produce insignificant results.

## Data [folder](https://drive.google.com/drive/folders/19iHyue_sr9cbP6v9IqJBG-FX_e1FI2IC?usp=sharing)
Initial dataset can be found in the _data.csv_ file.

After carrying out the _clean_up.ipynb_, a _data_clean.csv_ file is produced
