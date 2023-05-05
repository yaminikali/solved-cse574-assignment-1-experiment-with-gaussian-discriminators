Download Link: https://assignmentchef.com/product/solved-cse574-assignment-1-experiment-with-gaussian-discriminators
<br>
<strong>Evaluation </strong>We will evaluate your code by executing script.py file, which will internally call the problem specific functions. Also submit an assignment report (pdf file) summarizing your findings. In the problem statements below, the portions under REPORT heading need to be discussed in the assignment report.

<strong>Data Sets         </strong>Two data sets are provided:

<ol>

 <li>A 2D sample data set in the file “sample.pickle” along with the class assignment.</li>

 <li>A medical data set is provided in the file “diabetes.pickle” along with the target assignment. The input variables correspond to measurements (physical, physiological, and blood related) for a given patient and the target variable corresponds to the level of diabetic condition in the patient. It contains:

  <ul>

   <li><strong>x<sub>train </sub></strong>(242 × 64) and <strong>y<sub>train </sub></strong>(242 × 1) for training.</li>

   <li><strong>x<sub>test </sub></strong>(200 × 64) and <strong>y<sub>test </sub></strong>(200 × 1) for testing.</li>

   <li>                                                   Problem 1: Experiment with Gaussian Discriminators</li>

  </ul></li>

</ol>

Implement <strong>Linear Discriminant Analysis </strong>(LDA) and <strong>Quadratic Discriminant Analysis </strong>(QDA). Implement two functions in Python: ldaLearn and qdaLearn which take a training data set (a feature matrix and labels) and return the means and covariance matrix (or matrices). Implement two functions ldaTest and qdaTest which return the true labels for a given test data set and the accuracy using the true labels for the test data. The format of arguments and the outputs is provided in the base code.

<strong>REPORT 1. </strong>

Train both methods using the sample training data (<strong>sample train</strong>). Report the accuracy of LDA and QDA on the provided test data set (<strong>sample test</strong>). Also, plot the discriminating boundary for linear and quadratic discriminators. The code to plot the boundaries is already provided in the base code. Explain why there is a difference in the two boundaries.

Problem 2: Experiment with Linear Regression

Implement <em>ordinary least squares </em>method to estimate regression parameters by minimizing the squared loss.

(1)

In matrix-vector notation, the loss function can be written as:

<strong>Xw</strong>)<sup>&gt;</sup>(<strong>y </strong>−<strong>Xw</strong>)                                                                         (2)

where <strong>X </strong>is the input data matrix, <strong>y </strong>is the target vector, and <strong>w </strong>is the weight vector for regression.

Note that this is same as maximizing the log-likelihood in the Bayesian setting. You need to implement the function learnOLERegression. Also implement the function testOLERegression to apply the learnt weights for prediction on both training and testing data and to calculate the mean squared error (MSE):

(3)

<strong>REPORT 2. </strong>

Calculate and report the MSE for training and test data for two cases: first, without using an intercept (or bias) term, and second with using an intercept. Which one is better?

Problem 3: Experiment with Ridge Regression




Implement parameter estimation for ridge regression by minimizing the regularized squared loss as follows:

<strong>w                                                              </strong>(4)

In matrix-vector notation, the squared loss can be written as:

<strong>Xw</strong>)<sup>&gt;</sup>(<strong>y </strong>−<strong>Xw</strong>) + <strong>w                                                               </strong>(5)

You need to implement it in the function learnRidgeRegression.

<strong>REPORT 3. </strong>

Calculate and report the MSE for training and test data using ridge regression parameters using the the testOLERegression function that you implemented in Problem 2. Use data with intercept. Plot the errors on train and test data for different values of <em>λ</em>. Vary <em>λ </em>from 0 (no regularization) to 1 in steps of 0.01. Compare the relative magnitudes of weights learnt using OLE (Problem 2) and weights learnt using ridge regression. Compare the two approaches in terms of errors on train and test data. What is the optimal value for <em>λ </em>and why?

Problem 4: Using Gradient Descent for Ridge Regression Learning

As discussed in class, regression parameters can be calculated directly using analytical expressions (as in Problem 2 and 3). To avoid computation of (<strong>X</strong><sup>&gt;</sup><strong>X</strong>)<sup>−1</sup>, another option is to use gradient descent to minimize the loss function (or to maximize the log-likelihood) function. In this problem, you have to implement the gradient descent procedure for estimating the weights <strong>w</strong>.

You need to use the minimize function (from the <strong>scipy </strong>library). You need to implement a function regressionObjVal to compute the regularized squared error (See (4)) and its gradient with respect to <strong>w</strong>.

In the main script, this objective function will be used within the minimizer.

<strong>REPORT 4. </strong>

Plot the errors on train and test data obtained by using the gradient descent based learning by varying the regularization parameter <em>λ</em>. Compare with the results obtained in Problem 3.

<h2>Problem 5: Non-linear Regression (10 code + 5 report = 15 Points)</h2>

In this problem we will investigate the impact of using higher order polynomials for the input features. For this problem use the third variable as the only input variable:

xtrain = xtrain [ : , 2 ] xtest = x test [ : , 2 ]

Implement the function mapNonLinear which converts a single attribute <strong>x </strong>into a vector of <em>p </em>attributes, 1<em>,x,x</em><sup>2</sup><em>,…,x<sup>p</sup></em>.

<strong>REPORT 5. </strong>

Using the <em>λ </em>= 0 and the optimal value of <em>λ </em>found in Problem 3, train ridge regression weights using the non-linear mapping of the data. Vary <em>p </em>from 0 to 6. Note that <em>p </em>= 0 means using a horizontal line as the regression line, <em>p </em>= 1 is the same as linear ridge regression. Compute the errors on train and test data. Compare the results for both values of <em>λ</em>. What is the optimal value of <em>p </em>in terms of test error in each setting? Plot the curve for the optimal value of <em>p </em>for both values of <em>λ </em>and compare.

Problem 6: Interpreting Results

Using the results obtained for previous 4 problems, make final recommendations for anyone using regression for predicting diabetes level using the input features.

<strong>REPORT 6. </strong>