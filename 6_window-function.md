### Window function

#### a window function or analytic function is a function which uses values from one or multiple rows to return a value for each row. 

#### Window functions have an OVER clause; any function without an OVER clause is not a window function, but rather an aggregate or single-row function.

### Types of Window functions :
#### Analytical
#### Aggregate


#### Aggregate functions : An aggregate function computes the aggregate values of a particular row and returns the value. For example : sum() returns sum of a row. This returns a single result.

#### They are : sum, avg, min, max etc. This is same as we studied in python and in school.

#### Analytical functions : An analytic function computes values over a group of rows and returns a single result for each row. This is different from an aggregate function, which returns a single result for an entire group of rows.

#### They are : Cumulative distribution, row number, dense rank, rank, ntile, lag, lead, firstvalue, last value etc. We will see each one with a example and we will get more understanding.


