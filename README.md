# Project 1: Hotel Recommender

That project is a simple recommender based on data from hotels. Created for Recommender Systems Class conducted by [@PiotrZiolo]( https://github.com/PiotrZiolo )

## Requirements:

1. Create (and activate) a new environment with Python 3.8 with conda.

    * Linux or Mac:
        ```console
        conda create --name recommender python=3.8
        source activate recommender
        ```
    * Windows:
    
        ```console
        conda create --name recommender python=3.8 
        activate recommender
        ```

2. Install jupyter notebook
    
    ```console
    pip install notebook 
    ```
    
3. Install all needed packages

    ```console
    pip install numpy pandas matplotlib seaborn ipython sklearn hyperopt
    ```

4. Start Jupyter Notebook
    * project\_1\_data_preparation.ipynb contains the process of preprocessing data
    * project\_1\_recommender\_and\_evaluation contains recommender

## Algorithms used:
* To create user features I used one-hot encoding from all values that appeared in every column.
* To create item features I used pandas.get_dummies() which did basically the same as the method I used to create user features.
* To get negative interactions I took random all item_ids and random sample from user_ids with size of item_ids list. Then i iterated over item_ids and checked if there is a row in dataframe with that item_id and user_id.
* I've decided to use LinearRegressionCBUIRecommender, because it worked for me the best and got tuned relatively quick. It even beat Amazon recommender.
## Validation results:
|           Recommender           | HR@1     |   HR@3   | HR@5     | HR@10   | NGCG@1 | NGCG@3   | NGCG@5   | NGCG@10  |
|:-------------------------------:|----------|:--------:|----------|---------|----------|----------|----------|----------|
| LinearRegressionCBUIRecommender | 0.049219 |	0.130007 |	0.174134 |	0.233198 |	0.049219 |	0.094502 |	0.113016 |	0.131827
