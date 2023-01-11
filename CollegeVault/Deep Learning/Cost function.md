- Square of the difference between the expected output and the real output
![[Screen Shot 2022-12-17 at 10.51.15 AM.png]]
- The sum of all the cost functions is small if the program
- How bad the computer feel

- **Neural network function**
	- Input: 784 numbers (pixels)
	- Output: 10 numbers
	- Parameters: 13,002 weights/biases
- **Cost function**
	- Input: 13,002 weights/biases
	- Output: 1 number
	- Parameters: Many, many training examples
$$C(w_1, w_2,\dots, w_{13,002})$$
or
$$C(w)$$
- Minimalize it
	- $$\frac {dC}{dw}(w) = 0$$
	- Start in  any input and find the slope to get it 
	 ![[Screen Shot 2022-12-17 at 11.00.37 AM.png]]

- In this neuron network, the cost functions take 13,002 nudges as input and change them everytime there is new data.