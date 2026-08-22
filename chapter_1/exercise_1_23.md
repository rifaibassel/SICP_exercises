```scheme
(define (smallest-divisor n)
  (find-divisor n 2))

(define (next n)
  (if (= n 2) 3
      (+ n 2)
      )
  )

(define (find-divisor n test-divisor)
  (cond ((> (square test-divisor) n) 
         n)
        ((divides? test-divisor n) 
         test-divisor)
        (else (find-divisor 
               n 
               (next test-divisor)))))
```

```
Results after implementing the next function

1009 *** 1
1013 *** 1
1019 *** 1

10007 *** 2
10009 *** 3
10037 *** 3

100003 *** 7
100019 *** 8
100043 *** 6

1000003 *** 22
1000033 *** 20
1000037 *** 20
```

```
Results before implementing the next function 

1009 *** 1
1013 *** 0
1019 *** 1

10007 *** 2
10009 *** 4
10037 *** 3

100003 *** 8
100019 *** 8
100043 *** 9

1000003 *** 26
1000033 *** 26
1000037 *** 28
```

We notice that the amount of time needed is less than before implementing the next function, but it is not half the amount.
The new averages are:

  1. 1
  2. 2.6
  3. 7
  4. 20.67

The ratios are

  1. 1.66
  2. 0.86
  3. 0.84
  4. 0.77

We observe that the ratio is not what we expected this is due to introducing extra operations in place of the original one operation of just adding one, where now we call a function and execute a comparison.
