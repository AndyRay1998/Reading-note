[[Convex Optimisation/convex optimisation]]

```toc
```

## 1.1 Mathematical optimization
- general optimization problem
![[Pasted image 20220530193320.png]]
A vector x⋆ is called optimal, or a solution of the problem.

- linear program
	if both objective and constraint functions are linear.
	![[Pasted image 20220530193439.png]]
- convex optimization
![[Pasted image 20220530193537.png]]
	, in which $\alpha+\beta=1,\alpha \geq 0,\beta\geq 0$.
	From (1.2) and (1.3), linear programming is a special case of convex optimization.

- solving optimization problems
	(1.1) is usually difficult to solve;
	involve compromise.

## 1.2 Least-squares and linear programming
-  Least-squares problem formulation
![[Pasted image 20220530194118.png]]

- solving least squares problems
		- analytical solution ![[Pasted image 20220530200236.png]];
		- have accurate and reliable algorithms;
		- $O(n^2k)$;
		- special cases: sparse.
- using least squares
	weighted least squares;
	![[Pasted image 20220530200815.png]]
	regularization;
	![[Pasted image 20220530200808.png]]
	
- linear programming problem formulation
![[Pasted image 20220530200903.png]]
- solving linear programming
		- no analytical solutions;
		- effective methods exist;
		- $O(n^2m)$.

- Using linear programming
	Chebyshev approximation problem (i.e. infinity norm):
	![[Pasted image 20220530201247.png]]
	Transform to linear programming:
	![[Pasted image 20220530201358.png]]
	
## 1.3 Convex optimization
- problem formulation
![[Pasted image 20220530194247.png]]

- Solving convex optimization problems
		- no analytical solutions;
		- effective methods exist;
		- $O(max(n^3, n^2m, F))$, where F is the cost of evaluating the first and second derivatives of the objective and constraint functions.

- using convex optimization
		- not easy to recognize
		- many tricks to transform problems into convex form
		- surprisingly many problems can be solved with convex optimization

- example of lamp illumination
![[Pasted image 20220530195145.png]]
![[Pasted image 20220530195411.png]]
![[Pasted image 20220530195712.png]]
!!! notice how function h(~) transforms the problem to convex.


## 1.4 Nonlinear optimization
- local optimization
		- find a solution among feasible points near it
		- fast and can solve large-scale problems
		- require initial guess
		- provide no info about distance to global optimum
		- sensitive to algorithm parameter values

- global optimization
		- find global optimum
		- worst-case complexity grows exponentially

- Role of convex optimization in nonconvex problems
		- Initialization for local optimization
		- Convex heuristics for nonconvex optimization
		- Bounds for global optimization
