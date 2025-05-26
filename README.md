# SupervisedMLAndrewNg
**Week 01** 
It is all about introduction of linear regression and gives the fundamental idea. Let's start with some simple idea
y= wx + b
Need to predict y , which according to this model depends upto x with some weight and bias (b), need to find out w, and b, but how 
Let's constuct a cost function :
J(w,b) = 0.5*(mean of (sum of square error )) [ Here error is between prediction and actual : we are doing sum of each observation ]
Our obejective is to minimise cost function (can not make it zero beacuse there always gonna be a differnce unless we have perfect linear data itself)

Now 2 major problem :
1. How we are going to guess new weights and bias , if we do randomly guesses ,it will take forever .
2. How would we get know where to stop, I mean how would I be sure , this cost function is minimum.

Answer is Gradient decent, for the given problem (only one feature (x) is there ) we can simple see , it's quadratic so 
w_new = w_old - (learning rate) * (dJ/dw) (-ve sign to direct w_new toward the minima of cost function)
b_new= b_old - (learning rate)* (dJ/db) 

when we will be heading toward the minima of cost function ,derivative will be zero and w , b and cost function will converge to the single value , though it might be possible that derivative is not perfectly zero , in that case we might neet to have some tolerance for convergence.

THAT IS ALL FOR THE FIRST WEEK. (for linear problem : no of weights = no of features we are considering in the model, bias - single value)

**Week 02**
In this new part is multiple feature introduced in the problem and how to operation with verterization to make compution fast with help of numpy as in week 01 we were iterating through each loop , so matrix multiplication is critical .
Second part is to be careful between number of obeservation (m) and number of features (n) , otherwise confusion between (m,n) can lead to wrong matrix opeation .
while traing we take X_train as captical cuz X is matrix (2D ,having features as columns and number of obeserations as row) but y_train in small latter as it is 1D vectors where size is equal to number of oberserations.

So when I build gradient decent for the house pricing problem , I found that solution was highly sensitive to the learning rate , (in most of the cases solution might not converge ), so better to normize the data  , z score normalization (where mean is 0 and std devition is  1) i.e (x-mean)/sigma

lab3: tried feature scaling and polynomial regression , so first thing ,you just scale up the input features try there differnt combination and then calculate their weights and bias just the same way with gradient decent , so there is nothing new. 
But to get the best fit , just explore the input like doing squre, polynomial or putting in some function and then calculating the weights or bias.
But there is another way to put this:
whatever you do with feature if that operation is providing you linear relation with the output , that is the best operation for getting the fit. It's obious and facinating at the same time. it becomes classic linear regression problem.

lab5: Started scikit-learn library ,got function for normalizing the data , intiating model (SGD : need to learn more ) and train , all with single line of command

**Week 03**
Logistic Regression:
Used for classification , current course talks about binary classfication ,linear regression is bad choice for classification , if any data is outlier ,that might lead to very wrong prediction . In classification problem we need result between 0 and 1 (probability) but linear regression can give output any number , though we can decide some thersold "th" f(x)>th , positive result and vica versa ,but if any outlier is there then this method is poor (refer lab 1 of week 03)

Lab 2: So here linearor any  regression don't tell the final result , as we need something 0 and 1 , so that becomes the input for sigmoid function called z, and which vary from 0 to 1 and at z=0 ,sigmoid is 0.5. means 50% of yes, 50% of no

Lab 3: We talked about decesion boundary ,what does it mean , in classification outcome we decide some boundary ,if probability is more that we say true or less then that we say false . Commanly boundary is 50% , 0.5. p>0.5 : True , p<0.5 False. sigmoid to be 0.5, z = 0, f(w,b)=0 and this will give us curve 
that is called decesion boundary, for linear f(w,b) this is line otherwise could be anything circle  , elipse or circle etc. and for f(w,b)<0 : False domain, and f(w,b)>0 : True domain .


