# Solutions to 3. Homework

1. Yes
  * A two layer network can **theoretically** learn any smooth function y(x)
2. B)

* y(x) = h(x+d) - h(x-d)
* h(x) = 1 if x >= 0 else 0
* for x < -d: g(x) = 0 - 0 = 0
* for -d <= x < d: g(x) = 1 - 0 = 1
* for x >= d: g(x) = 1 - 1 = 0
* So in the interval [-d, d], h(x) = 1, else it's zero
* we need 3 neurons
  * one fires when x > -d (-d bias)
  * one fires when x < d = -x > -d (-d bias, -1 weight)
  * one fires when both of the others fire (2 bias)
  * so 2 in hidden, one in output
* in order to accomplish this with sigmoid, we need to scale up the values (bigger weights) 
to get close to a step-wise activation function

d > x > -d

~ 



3. C)
  1. layer weights = 100 * 30 = 3000
  1. layer weights = 30 * 10 = 300
  1. layer weights = 10 * 2 = 20
  1. layer weights = 2 * 10 = 20
  1. layer weights = 10 * 30 = 300
  1. layer weights = 30 * 100 = 3000
  1. biases weights = 30 + 10 + 2 + 10 + 30 + 100 = 182
  * weights = 6822
  * 6822 * 4 = 27 288  bytes (32 bits = 4 bytes)
  * question seems to check if we will forget the biases
4. B)
5. B) (but should be C))
  * let's look at 1D case for x_2
  * C_1
    * f(x) = x^2/2
    * f'(x) = x
    * f''(x) = 1 
    * takes 1000 iterations for newton => same amount for gradient descent
	as the inverse heassian matrix won't do anything in this case
  * C_2
    * f(x) =x^2/2 * 10^{-3}
    * f'(x) = x * 10^{-3}
    * f''(x) = 10^{-3}
  * so hessian = [[1, 0], [0, 10^{-3}]]
  * inverse hessian = [[1, 0], [0, 1000]]
  * that means 2. dimension needs 10^3 more steps in gradient descend
  * so it will take 10^3 (steps for C_1) * 10^3 = 10^6 steps for gradient descent, where as newton will still need 10^3
6. B)
7. C)
8. C)
  * but assuming question actually means to theta^+ instead of theta^*
9. C)
  * 9 hidden layers, number of neurons must be choosen (9 hyperparams from here)
  * 4 hyperparams for adam
    * beta1 and beta2 for 1 and 2 moment running means
    * learning rate
    * epsilon for numerical stability
  * the choice of a non-linear activation function is also a hyperparam
  * Total: 14
