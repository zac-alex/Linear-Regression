Understanding Regression: A Simple Guide

Regression is a statistical technique used for modeling the relationship between a dependent variable (the one you're trying to predict) and one or more independent variables (the predictors). In simple terms, regression helps us understand how changes in the independent variables impact the dependent variable.
At its core, regression tries to fit a line (or curve) to the data points. This line is the best possible representation of the relationship between the variables.

### What is Linear Regression?

Linear regression is used when we want to predict a continuous dependent variable based on the values of one or more independent variables. The term "linear" comes from the fact that the relationship between the variables is modeled as a straight line.

The equation for simple linear regression (with one independent variable) is:

y = β₀ + β₁ * x + ε

Where:
- y is the dependent variable (what we're trying to predict),
- x is the independent variable (the predictor),
- β₀ is the intercept (where the line crosses the y-axis),
- β₁ is the slope (how much y changes when x changes),
- ε is the error term (the difference between the predicted and actual values of y).

### How Does Linear Regression Work?

Linear regression works by finding the best-fitting line that minimizes the difference between the predicted values and the actual values of the dependent variable. This difference is known as the **residuals**.

The "best-fitting" line is determined by the **least squares method**, which minimizes the sum of the squared residuals. By doing so, we ensure the model fits the data as closely as possible.

### The Goal of Linear Regression

The goal of linear regression is to find the values of β₀ and β₁ that minimize the residual sum of squares. Once we have these values, we can use the equation to predict the dependent variable for new data.

### Matrix Representation of Simple Linear Regression

For linear regression, especially when dealing with multiple predictors, it's often useful to represent the model using matrices. In **simple linear regression** (one predictor), we can represent the equation in matrix form:

Y = X β + ε

Where:
- Y is an n × 1 vector of the dependent variable values (responses),
- X is an n × 2 matrix, which includes a column of ones (for the intercept) and the independent variable x for each observation,
- β is a 2 × 1 vector of the regression coefficients [β₀, β₁],
- ε is an n × 1 vector of the error terms.

### The Normal Equation for Simple Linear Regression

To find the optimal values of β₀ and β₁, we use the **normal equation**:

β = (Xᵀ X)⁻¹ Xᵀ Y

Where:
- Xᵀ is the transpose of matrix X,
- (Xᵀ X)⁻¹ is the inverse of Xᵀ X,
- Xᵀ Y is the matrix multiplication of Xᵀ and Y.

This formula gives us the best-fitting line by solving for the coefficients that minimize the sum of squared residuals.

### Example Calculation for Simple Linear Regression

### Solving for β

Given the normal equation:

β = (Xᵀ X)⁻¹ Xᵀ Y

Where:
- Xᵀ is the transpose of matrix X,
- (Xᵀ X)⁻¹ is the inverse of Xᵀ X,
- Xᵀ Y is the matrix multiplication of Xᵀ and Y.

Let’s solve for β using the dataset:

| Study Hours (x) | Test Score (y) |
|-----------------|----------------|
| 1               | 55             |
| 2               | 60             |
| 3               | 65             |

Step 1: Construct Matrix X (including a column of ones for the intercept):

X = [1 1]
    [1 2]
    [1 3]

Step 2: Calculate Xᵀ X:

Xᵀ X = [3   6]
       [6  14]

Step 3: Calculate Xᵀ Y:

Xᵀ Y = [180]
       [420]

Step 4: Calculate the inverse of Xᵀ X:

(Xᵀ X)⁻¹ = 1 / (3 * 14 - 6 * 6) * [14  -6 ]
                                  [-6   3 ]

         = 1 / (42 - 36) * [14 -6 ]
                           [-6  3 ]

         = 1 / 6 *   [14  -6]
                     [-6   3]

         = [2.3333  -1]
           [-1     0.5]

Step 5: Now, multiply (Xᵀ X)⁻¹ by Xᵀ Y:

β = [2.3333 -1]   *   [180]   =   [ 5.3333]
    [-1    0.5]       [420]       [  5   ]

Step 6: So, the regression coefficients are:

β₀ = 5.3333 (Intercept)
β₁ = 5 (Slope)

This means the regression equation is:

y = 5.3333 + 5 * x