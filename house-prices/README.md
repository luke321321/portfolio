# House Price Prediction

In this project we predict English and Welsh house prices in 2015 from historical data (1995-2014) using only the length of the lease, type of property (flat, terrace etc) and if the house is in London.  The dataset consists of approximately 24 million records in CSV format.  We use a simple Tensorflow model to fit a least squares regression (with elastic net regularisation).  We obtain a mean error of £640 on the test (2015) dataset after using the 2014 house prices as a validation dataset to fit the hyperparameters.  We used Gaussian process optimisation to choose the hyperparameters.

We preprocess and clean the data in [preprocess.ipynb](https://nbviewer.jupyter.org/github/luke321321/portfolio/blob/master/house-prices/pre-process.ipynb).  We fit and use evaluate the model in [model.ipynb](https://nbviewer.jupyter.org/github/luke321321/portfolio/blob/master/house-prices/model.ipynb).

Link to dataset: `FULL Price Paid Data-Single file 1995-2015` (CSV) from https://data.gov.uk/dataset/4c9b7641-cf73-4fd9-869a-4bfeed6d440e/hm-land-registry-price-paid-data.  Information about the dataset: https://www.gov.uk/guidance/about-the-price-paid-data