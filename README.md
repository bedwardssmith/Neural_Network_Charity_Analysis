<h1>Alphabet Soup</h1>
<h2>Overview of the Analysis</h2>
<p>Alphabet Soup, a not-for-profit, provides donations to other organizations which provide lifesaving technologies and organized reforestation around the world.  Using past data, Alphabet Soup is looking to design a neural network model to predict which donations will provide the greatest impact.</p>
<h2>Results</h2>
<p>In all models the data was first split into training and testing datasets using the train_test_split method.  Once the data had been split StandardScaler was then used to noramlize numerical variables to ensure that the neural network did not focus on outliers allowing for proper weights to each input.</p>
<h3>First Model</h3>
<h4>Data Preprocessing</h4>
<ul>
<li>The initial model removed both the “Name” and “EIN” from the data leaving, the “Status”, “Ask Amount”, “Application Type”, “Income Amount” and “Special Considerations” as the variables.  The target being “Is Successful”. </li>
</ul>
<h4>Compiling, Training and Evaluating the Model</h4>
<ul>
<li>In the first model two hidden layers were used with 80 and 30 neurons, respectively.   The rule of thumb for calculating the amount of neurons in the hidden layer is two to three times the number of inputs.  In our case there were 43 inputs, therefore, 80 neurons is appropriate for the first hidden layer.  The 30 neurons chosen for the second hidden layer is appropriate as it is less than half the size of the first hidden layer.<//li>
<li>Relu was used as the activation for the first and second layers whereas sigmoid was used for the output layer. The optimizer used was adam.</li>
<li>Having scaled the data and subsequently trained the data the accuracy was only 72.73%, meaning that the model predicted correctly 72.73% of the time.</li>
</ul>
<img src="https://github.com/bedwardssmith/Neural_Network_Charity_Analysis/blob/main/Images/Original.png">
<h3>Second Model</h3>
<p>As the accuracy in the first model was less than 75% a subsequently model was created.</p>
<h4>Data Preprocessing</h4>
<ul>
<li>In this model no changes were made to the variables or target from the original model.</li>
</ul>
<h4>Compiling, Training, and Evaluating the Model</h4>
<ul>
<li>This model also included two hidden layers, however, the neurons on the second layer were increased to 40 from the original 30.  Additionally, the activation for the first and second layer were changed to sigmoid.  Note that the epochs was also increased to 100.  Increasing epochs increases the amount of information provided to each neuron and therefore may result in an increased accuracy score, however, the risk of overfitting must also be taken into consideration when increasing the epochs.</li>
<li>The above changes resulted in an accuracy of 72.58% a slight decrease from the previous model.</li>
</ul>
<img src="https://github.com/bedwardssmith/Neural_Network_Charity_Analysis/blob/main/Images/Optimization_1.png">
<h3>Third Model</h3>
<p>As the accuracy in the first model and second model were less than 75% a third model was created.</p>
<h4>Data Preprocessing</h4>
<ul>
<li>In this model no changes were made to the variables or target from the original model.</li>
</ul>
<h4>Compiling, Training, and Evaluating the Model</h4>
<ul>
<li>This model included three hidden layers, with the neurons being 80, 40 and 20 respectively. Adding additional layers allows the nerual network to identify nonlinear characteristics without the need for additional input data. Additionally, the activation for all layers were changed to sigmoid.  Epochs were 100 as in the previous model.</li>
<li>The above changes resulted in an accuracy of 72.81% a slight increase from the previous models.</li>
<img src="https://github.com/bedwardssmith/Neural_Network_Charity_Analysis/blob/main/Images/Optimization_2.png">
</ul>
<h3>Fourth Model</h3>
<p>As the accuracy in the previous models were less than 75% a fourth model was created.</p>
<h4>Data Preprocessing</h4>
<ul>
<li>In this model “Status” was removed from the variables with no change to the target.  "Status" was removed as I did not feel it provided any meaningful information in predicting the target.</li>
</ul>
<h4>Compiling, Training, and Evaluating the Model</h4>
<ul>
<li>This model included three hidden layers, with the neurons being 90, 70 and 30 respectively; increased from previous models.  Additionally, the activation for all layers were changed to sigmoid with the exception of layer 1 for which relu was used.  Epochs were decreased to 70. </li>
<li>The above changes resulted in an accuracy of 72.64%s.</li>
</ul>
<img src="https://github.com/bedwardssmith/Neural_Network_Charity_Analysis/blob/main/Images/Optimization_3.png">
<h3>Fifth Model</h3>
<p>As the accuracy in the previous models were less than 75% a fourth model was created.</p>
<h4>Data Preprocessing</h4>
<ul>
<li>In this model “Status” was removed, however, “Name” was added to the list of variables with no change to the target.  I added "Name" as adding additional layers, changing neurons, changing the activation type and adding epochs had very little impact on the accuracy of the model. </li>
</ul>
<h4>Compiling, Training, and Evaluating the Model</h4>
<ul>
<li>In this model hidden layers were reduced to two with neurons being 90 and 40 respectively.  Additionally, activation was changed to sigmoid for all layers including the output layer as it is this activation that had provided the highest accuracy score in the previous models.  Epochs remained at 70. </li>
<li>The above changes resulted in an accuracy of 79.16% an increase from the previous models and greater than the thresshold of 75%.</li>
</ul>
<img src="https://github.com/bedwardssmith/Neural_Network_Charity_Analysis/blob/main/Images/Optimization_4.png">
<h2>Summary</h2>
<p>By changing the optimization to Sigmoid and by including the “Name” as a variable I was able to develop a model with an accuracy above 75%.  Based on all of the models created it is obvious that the inclusion of “Name” as a variable had a greater impact on accuracy than the number of layers, number of neurons or activation type used.  Although an accuracy of 79% was achieved using this deep learning model, RandomForets, a supervised machine learning model, likely could have achieved comparable accuracy using less code and less time.  The reason for the comparable accuracy is that RandomForest models trains weak learners on a subset of the input data. The model then predicts the classification based on a consensus of the weak learners.  By using a sufficient number of estimators and tree depth RandomForest models are generally able to perform similiar to most deep learning models.</p>

