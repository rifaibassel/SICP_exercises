```scheme
(define (+ a b)
  (if (= a 0) 
      b 
      (inc (+ (dec a) b))))

```

```scheme
(+ 4 5)
(inc (+ 3 5))
(inc (inc (+ 2 5)))
(inc (inc (inc (+ 1 5))))
(inc (inc (inc (inc (+ 0 5)))))
(inc (inc (inc (inc 5))))
(inc (inc (inc 6)))
(inc (inc 7))
(inc 8)
9
```

This process is clearly recursive, as it execution illustration shrinks and grows and to know where we are in the execution state we cant just depend on a fixed number of state variables

```scheme
(define (+ a b)
  (if (= a 0) 
      b 
      (+ (dec a) (inc b))))
```

```scheme
(+ 4 5)
(+ 3 6)
(+ 2 7)
(+ 1 8)
(+ 0 9)
9
```

This process is clearly iterative, as its execution illustration does not grow, and to know in which state of the process we are in we just have to know a and b.
