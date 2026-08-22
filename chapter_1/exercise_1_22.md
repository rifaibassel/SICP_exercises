```scheme
(define (timed-prime-test n)

  (start-prime-test n (runtime)))
(define (start-prime-test n start-time)
  (if (prime? n)
      (report-prime n (- (runtime) 
                       start-time))
      #f))
(define (report-prime n elapsed-time)
  (newline)
  (display n)
  (display " *** ")
  (display elapsed-time)
  #t)

 (define (search-for-primes start count)
   (cond ((= count 0) (newline))
         ((even? start)(search-for-primes (+ start 1) count))
         ((timed-prime-test start) (search-for-primes (+ start 2) (- count 1)))
         (else (search-for-primes (+ start 2) count))
         )
  )

(search-for-primes 1000 3)
(search-for-primes 10000 3)
(search-for-primes 100000 3)
(search-for-primes 1000000 3)
```

```
Output
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

The average of each call is

  1. 0.66
  2. 3
  3. 8.3
  4. 26.6

We have 3 / 0.66 = 5
We have 8.3 / 3 = 2.766666666666667
We have 26.6 / 8.3 = 3.2048192771084336

We see that the difference is getting closer to $\sqrt{10}$ as n grows which is consistent with our predictions
