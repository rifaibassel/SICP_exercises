Here we define a procedure a-plus-abs-b that takes in two arguments a and b.

This procedure applies an operator based on a conditional if, where if b is greater than zero the plus operator is applied and if not the minus operator is applied.

The resulting procedure is applied on two inputs a and b

The evaluation would be:

1. First evaluate a and b
2. Evaluate the predicate if b is greater than 0
3. Evaluate the resulting operator
4. Apply the operator to the evaluated values of a and b

Example of a = 3 and b = 4

```scheme
((if (> b 0) + -) a b)
((if (> 4 0) + -) 3 4)
((if (#t) + -) 3 4)
((+) 3 4)
(7)
```
