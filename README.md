The data which was given to me was to predict early birth weight of children during mother's pregnancy on basis of some maternal factors.<br>
For building a model to predict early birth weight I have gone through several process. They are:<br>

At first import all necessary libraries.<br>
Then import and read the data. Understand some necessary things like info decription for the data<br>
The dataset have 666 row with 75 columns. The data set's main objective is to find out birth wieght of babies early from different factors of mother during pregnency.<br>
In the data set there have childwt. which is our target column or dependent column and all other columns are independent column. The independent columns are like mothers physical stuation, environmental fector, habit, desease and many more. <br>On basis of mothers that type of condition we will predict the child's birth weight.<br>

<h1><b>data cleaning</b></h1><br>
then I have cleaned the data. drop the columns where there have null valuemore then 80% and fill the other null value with most frequent value.<br>
Binarized the childwt column<br>
There in the data logit column indicate <br>
0= child weight less than 2.5kg and<br>
1= child weight greater than 2.5kg <br>

With binariztion I have make child weight categorical. where I have defined<br>
0= child weight 0-2.4(weight less then 2.5 kg) and<br>
1= child weight 2.5-above(weight greater then 2.5 kg) <br>
As, both column are same we can drop one. I have drop logit.<br>

<h1><b> EDA(Exploratory data analysis)</b></h1><br>
Then try to described every categorical and continious value column and make analysis ondata on basis of different criteria.<br>
Then defined the childwt as the dependent variable and the others column as the independent variables.<br>

<h1><b>Feature Engineering</b></h1><br>
<b>Feature scaling</b>
Scale data with minmax scaler.<br>
Applied PCA(principal componant analysis for) explaining data variance ratio.<br>
<b>Feature Selection</b><br>
Showed corelation for data where we can see correlation of childwt with other columns. And also showed correlation of only dependents columns. plotted the correlattion plot. Find out columns which have correlation more then 0.5<br>
I also see most important feature by the feature importance.<br>
Aplied backward elimination process from wrapper method to find the best features. then see the multicoliniarity with vif.<br>
on basis of these feature selection techniques I have droped some feature which are least important.<br>
Then I have scaled the data with standard scaler from sklearn library.<br>
I have applied there holdout cross validation process.<br>
Split the data set into train and test(70:30)<br>

<h1><b>modeling</b></h1><br>
<b>logistic regression</b>
Accuracy:98.0%<br>
R Square score:88.34%<br>
Mean_squared_error:2.0%<br>

<b>Support vector mechine</b>
Accuracy:96.5%<br>
R Square score:79.60%<br>
Mean_squared_error:3.50%<br>

<b>K neighbours classifier</b>
accuracy:87.0%<br>
R Square score:24.24%<br>
mean_squared_error:13.0%<br>

<b>Gaussian Naive Bayes%</b>
accuracy:96.5%<br>
R Square score:79.60%<br>
mean_squared_error:3.50%<br>

For each model I have also calculated confusion matrix and plotted it. And make a classification report for each model.<br>
Then get AUC value for each model and plotted them into ROC curve<br>

The AUROC value we get:<br>
Logistic regression: AUROC = 0.971<br>
Support vector mechine: AUROC = 0.937<br>
K-Neighbours: AUROC = 0.721<br>
Gaussian Naive Bayes: AUROC = 0.945<br>

I have also make a logistic regression model with K-fold cross validation method and got score 97%


<b>So, according to the model accuracy and others criteria we can tell the logistic regression model with holdout cross validation method perform better than any other models.</b>
