[[applied nonlinear control - slotine]]
```toc
```

## 3.1 Nonlinear Systems and Equilibrium Points
- nonlinear system 
		- $x = f(x, u, t)$
		- special case: linear system $\dot{x} = A(t)x$
		- autonomous system: $f$ does not explicitly depend on time
		- linear time-invariant (LTI) systems
		- linear time-varying (LTV) systems
		- autonomous systems have relatively simpler properties and their analysis is much easier
- may lead to a non-autonomous closed-loop system if a controller dependent on time t
is chosen. e.g. adaptive controller.

- EQUILIBRIUM POINTS
		- A state $x^*$ is an equilibrium state (or equilibrium point) of the system if once $x(t)$ is equal to $x$ , it remains equal to $x$ for all future time. Mathematically, this means that the constant vector x* satisfies $$0 = f(x^*)$$
		- Equilibrium points can be found by solving the nonlinear algebraic equations
		- $\dot{x} = Ax$ has a single equilibrium point (the origin 0) if A is nonsingular. If A is singular, it has an infinity of equilibrium points, which are contained in the null-space of the matrix A, i.e., the subspace defined by Ax = 0.

## 3.2 Concepts of Stability
- stability and instability
		- The equilibrium state x = 0 is said to be stable if, for any R>0, there exists r>0, such that if $||x(0)|| < r$, then $||x(f)|| <R$ for all t>0 . Otherwise, the equilibrium point is unstable.
		- $\forall R>0,\exists r>0, || x(0) ||<r => \forall t > 0 , || x(f) || < R$
		- ![[Pasted image 20220609191410.png]]

- asymptotically stable
		- if it is stable, and if in addition there exists some r > 0 such that || x(0) || < r implies that x{t) —> 0 as t —> $\inf$.
		- An equilibrium point which is Lyapunov stable but not asymptotically stable is called $\textbf{marginally stable}$
		- domain of attraction
		- convergence does not imply stability

- exponentially stable
		- if there exist two strictly positive numbers $a$ and $\lambda$ such that $\forall f>0, ||x(t)|| < a||x(0)||e^{\lambda t}$ in some ball $B_r$ around the origin.

- GLOBAL STABILITY
		- If asymptotic (or exponential) stability holds for any initial states, the equilibrium point is said to be asymptotically (or exponentially) stable in the large. It is also called globally asymptotically (or exponentially) stable.

## 3.3 Linearization and Local Stability
- linearisation
		- Lyapunov's linearization method is concerned with the local stability of a nonlinear system
		- ![[Pasted image 20220609193315.png]]
		- ![[Pasted image 20220609193412.png]]

- Lyapunov's linearization method
		- if the linearized system is strictly stable (i.e, if all eigenvalues of A are strictly in the left-half complex plane), then the equilibrium point is asymptotically stable (for the actual nonlinear system).
		- If the linearized system is unstable (i.e, if at least one eigenvalue of A is strictly in the right-half complex plane), then the equilibrium point is unstable (for the nonlinear system).
		- If the linearized system is marginally stable (i.e, all eigenvalues of A are in the left-half complex plane, but at least one of them is on the /co axis), then one cannot conclude anything from the linear approximation (the equilibrium point may be stable, asymptotically stable, or unstable for the nonlinear system)

## 3.4 Lyapunov's Direct Method
### 3.4.1 Positive Definite Functions and Lyapunov Functions
- positive definite functions
		- A scalar continuous function $V(x)$ is said to be locally positive definite if $V(0) = 0$ and, in a ball $B_R$$$x \neq 0 => V(x) > 0$$
		- The above definition implies that the function V has a unique minimum at the origin 0.
- Lyapunov function
		- If, in a ball $B_R$, the function $V(x)$ is positive definite and has continuous partial derivatives, and if its time derivative along any state trajectory of system is negative semi-definite, i.e., $$V(x) < 0$$
### 3.4.2 Equilibrium Point Theorems
- LYAPUNOV THEOREM FOR LOCAL STABILITY
			- If, in a ball $B_{R0}$ , there exists a scalar function V(x) with continuous first partial derivatives such that
				• V(x) is positive definite (locally in BR )
				• V(x) is negative semi-definite (locally in BR )
				then the equilibrium point 0 is stable. If, actually, the derivative V(x) is locally negative definite in $B_{R0}$ , then the stability is asymptotic

- LYAPUNOV THEOREM FOR GLOBAL STABILITY
		- ![[Pasted image 20220609202711.png]]
		- sufficiency theorems.

### 3.4.3 Invariant Set Theorems
- invariant set
		- A set G is an invariant set for a dynamic system if every system trajectory which starts from a point in G remains in G for all future time
- This theorem is to extend equilibrium to limited cycles, when $\dot{V}$ is only negative semi-definite.
- LOCAL INVARIANT SET THEOREM![[Pasted image 20220616180046.png]]
- ![[Pasted image 20220616180611.png]]
- 全局不变集定理![[Pasted image 20220616180851.png]]


## 3.5 基于李雅普诺夫直接方法的系统分析
### 3.5.1 线性时不变系统
- 对称，反对称，正定矩阵
- 反对称矩阵的二次函数为零![[Pasted image 20220616183503.png]] ![[Pasted image 20220616183553.png]]
- 正定矩阵![[Pasted image 20220616183647.png]]
		- 几何解释：x与Mx之间夹角小于90° ![[Pasted image 20220616183734.png]]
		- 充要条件：主子式全为正 或 特征值全为正数
- ![[Pasted image 20220616184245.png]]
- 一个有用的办法：给定Q正定，返回去找P正定![[Pasted image 20220616184409.png]] ![[Pasted image 20220616184523.png]]

### 3.5.2 Krasovskii方法
- 寻找一般非线性系统李函数 例子书p56![[Pasted image 20220616184719.png]]
- 推广定理![[Pasted image 20220616185118.png]]


### 3.5.3 待定梯度法
- 假设梯度满足旋度条件![[Pasted image 20220616185343.png]]
- 步骤![[Pasted image 20220616185358.png]]

### 3.5.4 物理概念产生（受控系统）
- 机械臂模型例子![[Pasted image 20220616191304.png]] ![[Pasted image 20220616191422.png]] ![[Pasted image 20220616191442.png]]


### 3.5.5 性能分析
- 指数收敛引理 ![[Pasted image 20220616192155.png]] ![[Pasted image 20220616192204.png]]
- 线性系统收敛率估计![[Pasted image 20220616192807.png]]
- 非线性系统收敛率估计![[Pasted image 20220616193237.png]]

## 3.6 基于李雅普诺夫直接方法的控制设计
略