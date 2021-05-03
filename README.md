<h1>Alphabet Soup</h1>
<h2>Overview of the Analysis</h2>
<p>Alphabet Soup, a not-for-profit, provides donations to other not-for-profits based on requests.  Using past data, Alphabet Soup is looking to design a neural network model to predict which donations will result in successful results; greatest impact .</p>
<h2>Results</h2>
<h3>First Model</h3>
<h4>Data Preprocessing</h4>
<ul>
<li>The initial model removed both the “Name” and “EIN” from the data leaving, the “Status”, “Ask Amount”, “Application Type”, “Income Amount” and “Special Considerations” as the variables.  The target in this case is “Is Successful”. </li>
</ul>
<h4>Compiling, Training and Evaluating the Model</h4>
<ul>
<li>In the first model two hidden layers were used with 80 and 30 nodes, respectively.   The rule of thumb for calculating the amount of neurons in the hidden layer is two to three times the number of inputs.  In our case there were 43 inputs, therefore, 80 neurons, is appropriate for the first hidden layer.  The 30 neurons chosen for the second hidden layer is appropriate as it is less than half the size of the first hidden layer.<//li>
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
<li>This model also included two hidden layers, however, the nodes on the second layer were increased to 40 from the original 30.  Additionally, the activation for layer the first and second layer were changed to sigmoid.  Note that the epochs was also increased to 100</li>
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
<li>This model included three hidden layers, with the nodes being 80, 40 and 20 respectively.  Additionally, the activation for layer for all layers were changed to sigmoid.  Epochs were 100 as in the previous model.</li>
<li>The above changes resulted in an accuracy of 72.81% a slight increase from the previous models.</li>
<img src="https://github.com/bedwardssmith/Neural_Network_Charity_Analysis/blob/main/Images/Optimization_2.png">
</ul>
<h3>Fourth Model</h3>
<p>As the accuracy in the previous were less than 75% a fourth model was created.</p>
<h4>Data Preprocessing</h4>
<ul>
<li>In this model “Status” was removed from the variables with no change to the target. </li>
</ul>
<h4>Compiling, Training, and Evaluating the Model</h4>
<ul>
<li>This model included three hidden layers, with the nodes being 90, 70 and 30 respectively; increased from previous models.  Additionally, the activation for layer for all layers were changed to sigmoid with the exception of layer 1 for which relu was used.  Epochs were decreased to 70. </li>
<li>The above changes resulted in an accuracy of 72.64% a slight increase from the previous models.</li>
</ul>
<img src="https://github.com/bedwardssmith/Neural_Network_Charity_Analysis/blob/main/Images/Optimization_3.png">
<h3>Fifth Model</h3>
<p>As the accuracy in the previous models were less than 75% a fourth model was created.</p>
<h4>Data Preprocessing</h4>
<ul>
<li>In this model “Status” was removed, however, “Name” was added to the list of variables with no change to the target. </li>
</ul>
<h4>Compiling, Training, and Evaluating the Model</h4>
<ul>
<li>In this model hidden layers were reduced to two with nodes being 90 and 40 respectively.  Additionally, activation was changed to sigmoid for all layers including the output layer as it is this activation that had provided the highest accuracy score in the previous models.  Epochs remained at 70. </li>
<li>The above changes resulted in an accuracy of 79.16% a slight increase from the previous models.</li>
</ul>
<img src="https://github.com/bedwardssmith/Neural_Network_Charity_Analysis/blob/main/Images/Optimization_4.png">
<h2>Summary</h2>
<p>By changing the optimization to Sigmoid and by including the “Name” as a variable I was able to develop a model with an accuracy above 75%.  Based on all of the models created it is obvious that the inclusion of “Name” as a variable had a greater impact on accuracy than the number of layers, number of nodes or activation type used.  Although an accuracy of 79% was achieved using this model it is likely that using a supervised learning model such as RandomForest would have resulted in accuracy scores similar to the first four models used.  The advantage to using a supervised model such as RandomForest is the ease of coding and the length of time to run making it preferable over deep learning models in many cases.</p>

