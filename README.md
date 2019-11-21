# Food-Preparation-Time-Prediction

This original datasets provided by the SkipTheDishes include files train_orders_data_with_targets.csv (training data which has actual food preparation times), menu_items_details_complete.csv (which conatains details about menu items), and train_orders_data_with_targets.csv (for which we want to predict food preparation times).

The All_Test_Train_Clean.ipynb notebook produces cleaned datasets test_clean.csv, train_clean.csv, and menu_clean.csv. We firstly got rid of all the NaN values in test and train data. For fields that are like "item_", the NaN values are changed to "None" and for the fields that are like "quantity_", the NaN values are changed to 0.0. 

Manual imputations were done for the category and category_type for menu_items. 

New fields are added to both test and train dataset, based on quantities ordered for each item/category/category_type. These fields are named like "quant_". 

The train_clean.csv is then used to create our model which is then used to predict food preparation times for test data. The deep learning model has 4 layers of neural networks with ReLU as the activation function used to predit these times. "final_predictions.csv" contains the predictions corresponding to every order of the test data. 

"Poster.pdf" contains the poster that was presented at the 2019 Nexus Data Science Competition held at University of Manitoba, Winnipeg, Manitoba, Canada. 
------------------------------------------------------------------------------------------------------------------------------------------
The data science team at SkipTheDishes later provided "test_orders_target.csv" file which contains the actual food preparation time for the orders of test data. The comparisons of our "test_orders_target.csv" and "final_predictions.csv" is in the file "prediction_vs_actual_comparison.ipynb", in which we generate KDE plot ("prediction_vs_actual.png") and get the values of R^2 and RMSE. It turns out R^2 = 0.9599909551423244, and RMSE = 2.2393729909651934.  
