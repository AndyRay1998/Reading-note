[[DRL Algorithms]]


# Derivation
1. Porobability of a trajectory
	![[Pasted image 20220427222359.png]]
2. The log-derivative trick
	$\nabla_\theta P(\tau|\theta)=P(\tau|\theta)\nabla_\theta P(\tau|\theta)$
	![[Pasted image 20220427222525.png]]
3. Log-prob of a trajectory
![[Pasted image 20220427222142.png]]
4. Gradients of env functions
	The environment has no dependence on $\theta$, so gradients of $\rho_0(s_0)$, $P(s_{t+1}|s_t, a_t)$, and $R(\tau)$ are zero.
5. Grad-log-prob of a trajectory
	![[Pasted image 20220427223110.png]]
6. All together
![[Pasted image 20220427223157.png]]
7. Calculate expectation using sampling
![[Pasted image 20220427223327.png]]
8. Focus on the future (rewards after the action is taken)
![[Pasted image 20220427223928.png]]

# Baselines in PG
1. Expected grad-log-prob lemma
	Suppose that $P_{\theta}$ is a parameterized probability distribution over a random variable, $x$. Then: $E_{x \sim P_{\theta}}{\nabla_{\theta} \log P_{\theta}(x)} = 0$ 

2. Decrease variance
	The above lemma allows us to subtract any variable related to the states $s$.
	$$E_{a_t \sim \pi_{\theta}}{\nabla_{\theta} \log \pi_{\theta}(a_t|s_t) b(s_t)} = 0$$
	$$\nabla_{\theta} J(\pi_{\theta}) = E_{\tau \sim \pi_{\theta}}{\sum_{t=0}^{T} \nabla_{\theta} \log \pi_{\theta}(a_t |s_t) \left(\sum_{t'=t}^T R(s_{t'}, a_{t'}, s_{t'+1}) - b(s_t)\right)}$$

# General Form of PG
$$\nabla_{\theta} J(\pi_{\theta}) = E_{\tau \sim \pi_{\theta}}{\sum_{t=0}^{T} \nabla_{\theta} \log \pi_{\theta}(a_t |s_t) \Phi_t}$$
, where $\Phi_t$ can be any advantage function ([GAE](https://arxiv.org/abs/1506.02438)). 

# Quick fact
1. on-policy
2. discrete or continuous action space



