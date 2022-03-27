# Solving LQR for a pendulum cart

Using the following dynamic Equations, find the state space model.
<img src="https://render.githubusercontent.com/render/math?math=\begin{align*}(LM-m\ell \cos^2(\theta))\ddot{x}+m\ell g \cos(\theta)\sin(\theta)-Lm\ell \sin(\theta)\dot{\theta}^2&=Lu_1\\(LM-m\ell \cos^2(\theta))\ddot{\theta}-Mg\sin(\theta)+\frac{Mm\ell}{L}\dot{\theta}^2\cos(\theta)\sin(\theta)&=-\cos(\theta)u_2\end{align*}where $$\begin{align*}u_1&=K_1u + K_2\dot{x}\\u_2&=K_1u - K_2\dot{x}\end{align*}$$with $K_1$ and $K_2$ defined in the code block below">

We then linearize the above non-linear equation and write the equations in terms of
\dot{x} = Ax + Bu

We then find the optimal input u by solving the LQR problem for the above dynamics with R = 6 and $$Q = \begin{bmatrix} 10000 0 0 0// 0 1 0 0// 0 0 1000 0// 0 0 0 1\end{bmatrix}$$

We find the gain matrix by three methods:
1. Standard LQR function in Python Controls module
2. Solve the Riccati equation using dynamic programming approach
3. By using Hewer's Algorithm

and we compare the efficiency of the above methods.
