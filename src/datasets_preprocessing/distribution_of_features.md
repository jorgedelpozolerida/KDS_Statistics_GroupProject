# The Distribution of Features

There is a libary which can find and plot the most suitable distribution for the given data. Here, I am going to explain the necessary steps for that.

### 1. Import libaries:
>     import numpy as np   
>     import pandas as pd   
>     import seaborn as sns  from fitter import Fitter, get_common_distributions, get_distribution

### 2. Loading dataset

    dataset = pd.read_csv("weight_height.csv")  
    dataset.head()

### 3. Covert the data to numpy array

    height = dataset["Height"].values

### 4. Fitting distributions
 You can specifield the distributions that you want to check in following way: 

     f = Fitter(height,  
               distributions=['gamma',  
                              'lognorm',  
                              "beta",  
                              "burr",  
                              "norm"])  
    f.fit()f.summary()
Or you can test it for all the avaiable distribution (there are 106 different distribution,  so it is going to be slow.)

       f = Fitter(height,  
                   distributions=['gamma',  
                                  'lognorm',  
                                  "beta",  
                                  "burr",  
                                  "norm"])  
        f.fit()f.summary()
It can be a good idea to only test it for the most common distributions

    f = Fitter(data,  
    distributions= get_common_distributions())  
    f.fit()  
    f.summary()

**Everything is described in more detailed in this article:**
https://medium.com/the-researchers-guide/finding-the-best-distribution-that-fits-your-data-using-pythons-fitter-library-319a5a0972e9
