# <u><center>Implementing Deutsch-Jozsa Algorithm</u></center>

The Deutsch–Jozsa algorithm is a deterministic quantum algorithm proposed by David Deutsch and Richard Jozsa in 1992 with improvements by Richard Cleve, Artur Ekert, Chiara Macchiavello, and Michele Mosca in 1998. Although of little current practical use, it is one of the first examples of a quantum algorithm that is exponentially faster than any possible deterministic classical algorithm.

The Deutsch-Jozsa algorithm, first introduced was the first example of a quantum algorithm that performs better than the best classical algorithm. It showed that there can be advantages to using a quantum computer as a computational tool for a specific problem.


### Deutsch-Jozsa problem

Given a hiden boolean function $f$ which takes as input a string of bits and returns either $0$ or $1$:

$$
f(x0, x1, x2, ...)
$$

It is guaranteed that the function to either be balanced or constant. A constant function returns all $0$'s or all $1$'s for any input, while a balanced function returns $0$'s for exactly half of all inputs and $1$'s for the other half.

The problem is to determine whether the given function is balanced or constant.

### The classical solution

In the best case, two queries can determine if the hidden boolean function, $f(x)$, is balanced: e.g. if we get both $f(0,0,0,...)→0$ and $f(1,0,0,...)→1$, then we know the function is balanced as we have obtained the two different outputs.

In the worst case, if we continue to see the same output for each input we try, we will have to check exactly half of all possible inputs plus one in order to be certain that $f(x)$ is constant. Since the total number of possible inputs is $2^n$, this implies that we need $2^{n−1}+1$ trial inputs to be certain that $f(x)$ is constant in the worst case.

### The quantum solution

Using a quantum computer, we can solve this problem with 100% confidence after only one call to the function f(x), provided we have the function f  implemented as a quantum oracle, which maps the state
$\ket{x}\ket{y}$ to $\ket{x}$ $\ket{y⊕ f(x)}$
where   is addition modulo . Below is the generic circuit for the Deutsch-Jozsa algorithm.
