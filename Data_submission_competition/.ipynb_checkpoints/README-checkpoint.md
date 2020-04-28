# SA GAWLER CHALLENGE - FROM DATA CLEANING TO MACHINE LEARNING
# *Bridging the Gap between Geologists and Data Scientists!* 

-- By INCERTO DATA (Russell Menezes, Ahmad Saleem)

Our submission revolved around trying to clean and setup the state wide geochemical data supplied by the South Australian geological survey - with particular attention to handling the various populations present within the geochemical dataset - and then using this base geochemical dataset in conjunction with gridded geophysical data (not images) to create a training dataset that could be used for a machine learning model. 

The process that we have highlighted is not meant to be prescriptive but our attempt at understanding how best to handle the spatial variability present within the geochemical and geophysical datasets.

Please note that we have only focussed on the gold assay data available in the geochemical dataset. But the process could be repeated for other elements as well.

#### 1. Handling Different Sample Populations

Statewide geochemical datasets are usually a collection of decades worth of various samples collected by various entities (including the geological survey but also numerous mining and exploration companies) combined into one dataset irrespective of what the different samples are or when they were collected. The intention behind creating this single dataset is to make it easy for the end user to work with. But it creates the unintended problem of combining various populations into the one dataset. The end user must decide how to handle the various populations within the dataset. 

There are several reasons for the various populations in these geochemical datasets. The two most common culprits are:
- Different samples types present 
- Different analysis methods being included. This leads to different elements present for each sample (i.e. not all elements are available for each sample) and can also lead to differences in absolute elemental values reported for each element.

Before deciding to use this dataset, it is worth understanding what effect these different populations have and how best to minimise that. 

#### 2. Integrating Geochemical Data with Geophysical Grids (Not RGB Images)

Once the geochemical dataset was normalised to the various populations within it, we attempted to correlate it to the available geophysical (magnetics and gravity) datasets available. Instead of using the interpreted images, we used the available gridded data. The intention was to create a training dataset that combines geochemical and the geophysical data with anomalous gold values as the predictor. 

#### 3. What is the X and y? Regression or Classification? Formulating the Machine Learning Problem

At the end, we open it up for discussion on how best to approach this in creating a machine learning model - i.e. whether it is best to create a classification model or a regression model. 

Our belief was that setting up the test as a classification problem is likely to deliver better results as it is hard to imagine it being possible to predict gold assay values based on geophysical data. Whereas it is more conceivable to have geophysical responses related to anomalous gold features highlighted through the classification test. 

We created the dataset to test both but we left it there for this submission as we ran out of time to fully test and report our models.

![xyz](Notebooks/map.png)