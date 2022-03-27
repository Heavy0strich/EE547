# Solving LQR for a pendulum cart

Using the dynamic Equations of the pendulum cart sytem and find the state space representation of the system.

Then linearize the non-linear equation and write the equations as a first order differential Equation.

We then find the optimal input u by solving the LQR problem for the above dynamics with R = 6 and 
Q = [
    [10000.0, 0.0, 0, 0],
    [0, 1, 0, 0],
    [0, 0, 10000, 0],
    [0, 0, 0, 1]
]

We find the gain matrix by three methods:
1. Standard LQR function in Python Controls module
2. Solve the Riccati equation using dynamic programming approach
3. By using Hewer's Algorithm

and we compare the efficiency of the above methods.
