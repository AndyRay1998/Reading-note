[[convex optimisation]]

```toc
```


## 2.1 Affine and convex sets
### 2.1.1 Lines and line segments
![[Pasted image 20220530205619.png]]
or
![[Pasted image 20220530205941.png]]
### 2.1.2 Affine sets
- affine sets
		- if for any x1, x2 ∈ C and θ ∈ R, we have $θx_1 +(1−θ)x_2 ∈ C$![[Pasted image 20220530220233.png]]
- affine hull
		- set of all affine combinations of points in some set $C ⊆ R^n$, i.e. $aff \ C = {θ_1x_1 + · · · + θ_kx_k | x_1, . . . , x_k ∈ C, θ_1 + · · · + θ_k = 1}$

### 2.1.3 Affine dimension and relative interior
- affine dimension
		- the affine dimension of a set C is the dimension of its affine hull
- relative interior
		- $relint \ C = {x ∈ C | B(x, r) ∩ aff \  C ⊆ C \ for \ some \ r > 0}$, where B(x, r) = {y | ||y − x|| ≤ r}, the ball of radius r and center x.
		- example ![[Pasted image 20220530221714.png]]


### 2.1.4 Convex sets
- Convex set
		- set C is convex if line segment between any two points in C lies in C, i.e., if for any x1, x2 ∈ C and any θ with 0 ≤ θ ≤ 1, we have$$θx_1 + (1 − θ)x_2 ∈ C$$
- Convex hull
		- set of all convex combinations of points in C:		$$conv C = {θ_1x_1 + · · · + θ_kx_k | x_i ∈ C, θ_i ≥ 0, i = 1, . . . , k, θ_1 + · · · + θ_k = 1}$$
		- ![[Pasted image 20220530210526.png]]

### 2.1.5 Cones
- convex cone
		- A set C is a convex cone if it is convex and a cone, which means that for any $x_1, x_2 ∈ C$ and $θ_1, θ_2 ≥ 0$, we have
$$θ_1x_1 + θ_2x_2 ∈ C$$
- conic combination
		- $θ_1x_1 + · · · + θ_kx_k \ \ with \ \ θ_1, . . . , θ_k ≥ 0$
		- a set C is a convex cone if and only if it contains all conic combinations of its elements
		- ![[Pasted image 20220530211121.png]]
		- ![[Pasted image 20220530211224.png]]

## 2.2 Some important examples
### 2.2.1 Hyperplanes and halfspaces
- concept
		- A hyperplane is a set of the form
$$\{x | a^T x = b\}$$
- interpretation
		- inner product with normal vector a![[Pasted image 20220530213824.png]]
		- $\{x | a^T (x − x_0) = 0\},a^T x_0 = b$

- halfspace
		- convex but not affine
		- $\{x | a^T x ≤ b\}$ = $\{x | a^T (x − x_0) ≤ 0\}$, simple geometric interpretation![[Pasted image 20220530214451.png]]

### 2.2.2 Euclidean balls and ellipsoids
- (Euclidean) ball
		- $B(x_c, r) = \{x ||x − x_c||_2 ≤ r\} = \{x | (x − x_c)T (x − x_c) ≤ r^2\}$
		- $B(x_c, r) = \{x_c + ru \ \ | \ \ ||u||_2 ≤ 1\}$
		- convex set

- ellipsoids
		- $E = {x | (x − x_c)^T P^{−1}(x − x_c) ≤ 1}$, P is symmetric and positive definite
		- $E = \{x_c + Au \ \ | \ \ ||u||_2 ≤ 1\}$, A is symmetric and positive definite.  $A = P^{1/2}$.

### 2.2.3 Norm balls and norm cones
- norm balls
		- $\{x \ \big{|} \ ||x−x_c|| ≤ r\}$

- norm cone
		- $C = \{(x, t) \ \big{|} \  ||x|| ≤ t\} ⊆ R^{n+1}$![[
		- second-order cone / quadratic cone
			$C = \{(x, t) \ \big{|} \  ||x||_2 ≤ t\} ⊆ R^{n+1}$ = $\{ \begin{bmatrix} x  \\ t \end{bmatrix} \ \Big{|} \ \begin{bmatrix} x  \\ t \end{bmatrix}^T  \begin{bmatrix} I & 0  \\ 0&-1 \end{bmatrix} \begin{bmatrix} x  \\ t \end{bmatrix} \leq 0, t\geq 0 \}$![[Pasted image 20220531115707.png]]

### 2.2.4 Polyhedra
- the solution set of a finite number of linear equalities and inequalities:
$$P = \{x | a^T_jx ≤ b_j , j = 1, . . . ,m, c^T_jx = d_j , j = 1, . . . , p\}$$
$$P = \{x | Ax \leq b, Cx = d\}$$
- A polyhedron is thus the intersection of a finite number of halfspaces and hyperplanes![[Pasted image 20220531120058.png]]
- simplexes
		- $C = conv\{v_0, . . . , v_k\} = \{θ_0v_0 + · · · + θ_kv_k | θ \geq 0, 1^T θ = 1\}$
		- A 1-dimensional simplex is a line segment; a 2-dimensional simplex is a triangle (including its interior); and a 3-dimensional simplex is a tetrahedron


### 2.2.5 The positive semidefinite cone
- symmetric $n \times n$ matrices:
		- $S_n = \{X ∈ R^{n×n} | X = X^T \}$
- positive semidefinite matrices
		- $S^n_{+}= \{X ∈ S_n | X \geq 0\}$
- symmetric positive definite matrices
		- $S^n_{++}= \{X ∈ S_n | X > 0\}$
- The set $S^n_+$ is a convex cone: if θ1, θ2 ≥ 0 and A, B ∈ Sn
	+, then θ1A+θ2B ∈ Sn+.
- Positive semidefinite cone in $S^2$:
		- $X=\begin{bmatrix} x&y  \\ y&z  \end{bmatrix}\in S^2_+ \iff x \geq 0, z \geq 0, xz \geq y^2$![[Pasted image 20220531132038.png]]

## 2.3 Operations that preserve convexity
### 2.3.1 Intersection
- if S1 and S2 are convex, then S1 ∩ S2 is convex.
- a converse holds: every closed convex set S is a (usually infinite) intersection of halfspaces.
- In fact, a closed convex set S is the intersection of all halfspaces that contain it:

### 2.3.2 Affine functions
- if it has the form f(x) = Ax + b, where A ∈ Rm×n and b ∈ Rm. Suppose S ⊆ Rn is convex and f : Rn → Rm is an affine function. Then the image of S under f, $$f(S) = {f(x) | x ∈ S}$$
	is convex. Similarly, if f : Rk → Rn is an affine function, the inverse image of S under f, $$f^{−1}(S) = {x | f(x) ∈ S}$$, is convex
- EXAMPLE: scaling and translation ![[Pasted image 20220609205348.png]]
- EXAMPLE: sum, projection
- EXAMPLE: linear matrix inequality (LMI)
		- ![[Pasted image 20220609210926.png]]

### 2.3.3 Linear-fractional and perspective functions
- perspective function
		- P : Rn+1 → Rn, with domain domP = Rn × R++, as P(z, t) = z/t.
- Linear-fractional functions
		- ![[Pasted image 20220609212003.png]]
		- ![[Pasted image 20220609212301.png]]


## 2.4 Generalized inequalities
### 2.4.1 Proper cones and generalized inequalities
- proper cone
		- ![[Pasted image 20220609214548.png]]
- generalized inequality
		- partial ordering
		- ![[Pasted image 20220609214846.png]]
		- ![[Pasted image 20220609214854.png]]
		- When K = R+, the partial ordering is the usual ordering.

- Properties of generalized inequalities
		- ![[Pasted image 20220609215407.png]]
		- ![[Pasted image 20220609215443.png]]

### 2.4.2 Minimum and minimal elements
- not linear ordering
		- e.g. [1, 2] and [2, 1] are not comparable
		- ![[Pasted image 20220609220344.png]]
- minimum and minimal
		- ![[Pasted image 20220609220420.png]]
		- ![[Pasted image 20220609220526.png]]

## 2.5 Separating and supporting hyperplanes
### 2.5.1 Separating hyperplane theorem
- separating hyperplane theorem
		- Suppose C and D are nonempty disjoint convex sets, i.e., C ∩D = ∅. Then there exist a != 0 and b such that aT x ≤ b for all x ∈ C and aT x ≥ b for all x ∈ D.
		- ![[Pasted image 20220609221923.png]]
- The converse of the separating hyperplane theorem (i.e., existence of a separating hyperplane implies that C and D do not intersect) is not true, unless one imposes additional constraints on C or D, even beyond convexity.

### 2.5.2 Supporting hyperplanes
- supporting hyperplane theorem
		- for any nonempty convex set C, and any x0 ∈ bdC, there exists a supporting hyperplane to C at x0
 - concept
		 - Suppose C ⊆ Rn, and x0 is a point in its boundary bdC, i.e., x0 ∈ bdC = clC \ intC.![[Pasted image 20220609222724.png]]
- partial converse of the supporting hyperplane theorem
		- If a set is closed, has nonempty interior, and has a supporting hyperplane at every point in its boundary, then it is convex.

## 2.6 Dual cones and generalized inequalities
### 2.6.1 Dual cones
