# Multiple linear regression with Python, numpy, matplotlib, plot in 3d
<br/>
Background info / Notes:
<br/>
Equation:<br/>
Multiple regression: Y = b0 + b1*X1 + b2*X2 + ... +bnXn<br/>
compare to Simple regression: Y = b0 + b1*X<br/>
<br/>
In English: <br/>
Y is the predicted value of the dependent variable<br/>
X1 through Xn are n distinct independent variables<br/>
b0 is the value of Y when all of the independent variables (X1 through Xn) are equal to zero<br/>
b1 through bn are the slope of the relationship between the dependent variable and the independed variable that is holding constant of all other independent variables.<br/>
<br/>
Think of it as a system of equations:<br/>
Y1 = (b + mX1) + e1<br/>
Y2 = (b + mX2) + e2<br/>
...<br/>
Yn = (b + mXn) + en<br/>
We can then set up a matrix equation with the following matrices:<br/>
<br/>
&nbsp; &nbsp; &nbsp; &nbsp;|Y1|<br/>
Y = |......|<br/>
&nbsp; &nbsp; &nbsp; &nbsp;|Yn|<br/>
<br/>
&nbsp; &nbsp; &nbsp; &nbsp;|1 X1|<br/>
X = |... ...|<br/>
&nbsp; &nbsp; &nbsp; &nbsp;|1 Xn|<br/>
<br/>
&nbsp; &nbsp; &nbsp; &nbsp;|b|<br/>
A = |m|<br/>
<br/>
&nbsp; &nbsp; &nbsp; &nbsp;|e1|<br/>
E = |......|<br/>
&nbsp; &nbsp; &nbsp; &nbsp;|en|<br/>
<br/>
Which gives us the matrix equation: Y = XA + E<br/>
We just need to solve for A<br/>
<br/>
Use Linear Algebra to solve<br/>
Equation: <br/>
A = (X^T * X)^-1 * (X^T * Y) <br/>
<br/>
Two helpful links that explain how we get this equation:<br/>
https://www.youtube.com/watch?v=Qa_FI92_qo8<br/>
https://www.youtube.com/watch?v=qdOG7YMolmA<br/>
<br/>
Convert the equation to code:<br/>
Using the np.linalg.solve function we will not need to invert the first term<br/>
a = np.linalg.solve(np.dot(X.T, X), np.dot(X.T, Y))<br/>
<br/>
<p>
<img src="MultiLinearBPgraph1.png" alt="image">
<br/>
<img src="MultiLinearBPGraph2.gif" alt="image">
<br/>
<img src="MultiLinearBPgraph3.png" alt="image">
</p>
