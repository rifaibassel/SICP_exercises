For an example of a small number we choose the number 0.0001 (1 * 10^-3).

We know its square root to be 0.01, but running our procedure with 0.0001 returns 0.03230844833048122.

This value passes our test but it is not close to the true number we would need to improve our at least once so we can get a number close to the true value.

For an example of a large number we choose the number 1000000000000000.

We know its square root to be 31522776.60168379.

What we find is that we hit an infinite loop where our guess is not passing the test but our improvement function is not changing the guess instead its keeping it the same.

So the problem for small numbers is that our test function returns true prematurely while the problem for large numbers is that we never reach a point where the test function returns true.

We can reimplement the good-enough? function to test if the change between the previous guesses is very small, this tells us that our improvements are negligible and we wont get stuck in an infinite loop.

It also tells us that we do not have any more improvements to implement as this is the most we can do.

```scheme
(define (square x)
  (* x x)
  )

(define (good-enough? prev-guess guess)
  (define delta (abs(- guess prev-guess)))
  (< (* (/ delta prev-guess) 100) 1)
  )

(define (average x y)
  (/ (+ x y) 2)
  )

(define (improve guess x)
  (average guess (/ x guess))
  )

(define (sqrt-iter prev-guess guess x)
  (if (good-enough? prev-guess guess)
      guess
      (sqrt-iter guess (improve guess x) x))
  )

(define (sqrt x) (sqrt-iter 10000 1.0 x))


(sqrt 0.0001)
```
