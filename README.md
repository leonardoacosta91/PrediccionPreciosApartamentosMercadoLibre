# Price Apartment Prediction in Montevideo, Uruguay
Project carried out by Leonardo Acosta and Federico Crespo, in the framework of a research about the price of apartments in Montevideo, Uruguay. The project consists of an ETL pipeline which is responsible for scraping the MercadoLibre page in Uruguay, performs transformations to clean the data, determine the highest correlation variables, and fits Machine Learning models to achieve the most accurate results in the prediction.

It is divided into:
## Packages and definition of functions for graphs. 
-	Import of the necessary packages for the correct execution of the code.
-	Definition of functions for graphs for a correct visualization of the data.

### Extraction
Automated extractions are made from the Mercado Libre - Montevideo - Uruguay page but also supports the possibility of adding new pages to perform scraping in the following pages using Selenium. In this project we used the first 10 pages of apartments in the city of Montevideo, Uruguay.

### EDA and Data Transformation
The process consists of different transformations, because it is a real dataset, extracted from the internet, there was a lot to clean and transform. 
First, an EDA was elaborated to determine which columns were available, the characteristics of the data, which transformations had to be performed and which columns or data had to be discarded. 

Then we proceeded to transform the data:
-	Separate currency from price - Some apartments were in USD, others in Uruguayan pesos.
-	Determine outliers - There were exorbitant or very low prices, so we chose to keep those in the range of intermediate quartiles, from 255 to 75% of the data.
-	Determine the location of the apartments, to know where the apartments were distributed.
-	Condition - No different values were found within the data, so we proceeded to eliminate the column.
-	Area - The existence of outliers within the column was determined. We proceeded to normalize the data, eliminating outliers. The correlation between price and area was plotted, and indeed, the correlation is positive.
-	A formal count of bathrooms, bedrooms and garages of the apartments was made.
-	We explored the age of the apartments.

### Correlation
A correlation matrix was elaborated having price as the main axis. From the correlation graph, it was determined that the main components that determine the price of an apartment rental in Montevideo are:  
1- Bathrooms.  
2- Bedrooms.  
3- Total surface area.  
4- Parking spaces.  
5- Common expenses.  

Then, the locations begin to appear, being Pocitos and Punta Carretas the most expensive locations.

### Machine Learning
Since the objective of the work was to determine future prices, we used Machine Learning models of regression character, with the target variable known, i.e. a type of supervised learning. We used different Machine Learning models to be able to determine more accurately and test the model in a more efficient way. 

### Conclusions

For the final part of the project, the dataset is evaluated with different Machine Learning models, the Ridge model being the one that gives a better score in the evaluation of the prediction against the test data set.

The results obtained were:  
![image](https://user-images.githubusercontent.com/30410928/123285286-48dc6480-d4e3-11eb-9e70-748dc5d8b8fc.png)


## Prerequisites 📋
It is necessary to have python 3.7 or later.  
The dependencies and necessary modules are specified in requirements.txt 

## Setup 🔧
Create a virtual environment and run the following command to install everything needed.
```
pip install -r requirements.txt
```

## Deployment 📦
Open:
```
PrediccionVentaApartamentos.ipynb
```

## Authors  ✒️
- Leonardo Acosta - Complete project - [Leonardo Acosta](https://github.com/leonardoacosta91)
- Federico Crespo - Complete project - [Federico Crespo](https://github.com/federicocrespo10)

