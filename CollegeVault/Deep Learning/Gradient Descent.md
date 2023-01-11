- "Gradient" of a function gives direction of steepest ascent
	- $\triangledown C(x,y)$ : Which direction decrease most quickly

Gradient Descent
	- Converge into a local minimum of a [[Cost function]]

- The algorithm of building an effective gradient descent is called [[Backpropagation]].
	- Heart of neuron network

![[Screen Shot 2022-12-17 at 10.30.06 PM.png]] 
- Think the $\vec W$ as a vector with 13,002 nudge,
	- The  $- \triangledown C(\vec W)$ is the Gradient Descent which is another vector telling $\vec W$ what to adjust for each nudge in order to "go down the hill"
	- for example: 0.31: Mean if you nudge the connection there, it will affect the cost function 31 times