```scheme
(define (timed-prime-test n)
  (start-prime-test n (runtime)))

(define (start-prime-test n start-time)
  (if (fast-prime? n 1)
      (report-prime n (- (runtime) 
                       start-time))
      #f))
```

```
Output
1009 *** 1
1013 *** 1
1019 *** 1

10007 *** 1
10009 *** 1
10037 *** 1

100003 *** 1
100019 *** 2
100043 *** 1

1000003 *** 1
1000033 *** 2
1000037 *** 2
```

The new averages are:

  1. 1
  2. 1
  3. 1.33
  4. 1.66

We have 1 / 1 = 1
We have 1.33 / 1 = 1.33
We have 1.66 / 1.33 = 1.2481203007518795
We also ave 1.66 / 1 = 1.66

We expect the ratio to be about ($\log{1000000}/\log{1000}$) = 2

The computer clock is unable to detect how fast the fast-prime? algorithm actually runs and thus measures in addition to it multiple other things that the interpreter runs
