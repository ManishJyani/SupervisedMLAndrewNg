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


lab4 : Started scikit-learn library ,got function for normalizing the data , intiating model (SGD : need to learn more ) and train , all with single line of command

