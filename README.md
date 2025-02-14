1. Constructor: Simplex(vector<vector<double>> &A, vector<double> &b, vector<double> &c)
•	Purpose: Initializes the simplex tableau using the input coefficients of constraints (A), right-hand side values (b), and the objective function coefficients (c).
•	Parameters:
o	A: Coefficients of constraint equations.
o	b: Right-hand side values for the constraints.
o	c: Coefficients of the objective function.
•	How it Works:
o	Constructs the initial tableau.
o	Adds slack variables to transform inequalities into equations.
o	Sets up the last row for the objective function.
________________________________________
2. void printTableau()
•	Purpose: Prints the current simplex tableau along with the Zj row and Cj - Zj row to track the computation process.
•	How it Works:
o	Prints the entire tableau in a formatted way.
o	Computes the Zj row (the sum of basic variable contributions).
o	Computes Cj - Zj row to check for optimality conditions.
o	Displays both rows.
________________________________________
3. bool isOptimal()
•	Purpose: Checks whether the current tableau represents an optimal solution.
•	How it Works:
o	Iterates over the objective row (last row of the tableau).
o	If any coefficient is negative, the solution is not optimal and further iterations are required.
o	If all values are non-negative, the algorithm terminates.
________________________________________
4. void pivot(int pivotRow, int pivotCol)
•	Purpose: Performs the pivoting operation to bring a new variable into the basis.
•	Parameters:
o	pivotRow: Index of the row containing the pivot element.
o	pivotCol: Index of the column containing the pivot element.
•	How it Works:
o	Divides the pivot row by the pivot element to make the pivot element 1.
o	Updates all other rows to make the pivot column entries 0, ensuring a valid basic feasible solution.
o	Uses the row operations of the Simplex method to maintain feasibility.
________________________________________
5. void solve()
•	Purpose: Iteratively applies the Simplex algorithm to reach an optimal solution.
•	How it Works:
o	Repeatedly checks for optimality using isOptimal().
o	Identifies the pivot column (most negative value in the objective row).
o	Identifies the pivot row using the minimum ratio test (smallest positive ratio of RHS to the pivot column value).
o	If no valid pivot row exists, the problem is unbounded.
o	Performs the pivot operation.
o	Prints the updated tableau after each iteration.
o	Stops once an optimal solution is reached.
