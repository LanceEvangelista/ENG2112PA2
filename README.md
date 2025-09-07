# ENG2112PA2

## Numpy in Python

## NORMALIZATION PROBLEM: Create a randomized 5 x 5 array and save the normalized output


This program makes use of the numpy library in order to generate and manipulate a 5x5
array into the desired normalized output.


First, the program generates a 5x5 random array using the code `x = np.random.random((5,5))`
This creates an array filled with numbers between the range of 0 - 1 based on the size inside the `()`


After the initial array of values is created, a separate variable stores the mean and standard deviation
of the initial array using `.mean()` and `.std()` to perform mention calculations.

``` python
#Get the Mean and standard deviation using .mean and .std
x_mean = x.mean()
x_std = x.std()
```
Once the mean and standard deviation are calculated, the normalized values per element can be calculated using the following formula:

$$
Z = \frac{X - \bar{x}}{\sigma}
$$

which represented in python is

```python
x_normalized = ((x - x_mean)/x_std)
```
In order to save the normalized values for the array in an .npy file type `.save()` is used which allows the program to save the value
of a given variable as a file using the parameters ("name.filetype", [variable])

```python
np.save('x_normalized.npy', x_normalized)
```

## Divisible by 3 Array: Create an array of the squares of the first 100 integers and then save the values divisble by three as an .npy file

First, the program creates an array of the first 100 positive integers using the `arange(start,stop,step)` syntax. in order to turn the values
within the array into squares `** 2` is used after the syntax, which applies the indicated operation onto every element within the array.

```python
intarray = np.arange(1, 101) ** 2
```

Using a loop that checks if the remainder of an element after dividing by 3 is zero, the program can determine which numbers are divisible by three.
If the condition is satisfied, the program adds that element to a new array to be exported after checking all elements.

``` python
for x in intarray:
    divisible = intarray[intarray % 3 == 0]
```
Lastly, using .save() the program saves the data as "div_by_3.npy"

```python
np.save("div_by_3.npy", divisible)
```
