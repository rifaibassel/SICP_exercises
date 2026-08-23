```scheme
(define (expmod base exp m)
  (cond ((= exp 0) 1)
        ((even? exp)
         (remainder 
          (square (expmod base (/ exp 2) m))
          m))
        (else
         (remainder 
          (* base (expmod base (- exp 1) m))
          m))))

(define (test-congruence n a)
  (cond ((= a 0) #t)
        ((not (= (remainder a n) (expmod a n n))) #f)
        (else (test-congruence n (- a 1))))
  )

(test-congruence 561 561)
(test-congruence 1105 1105)
(test-congruence 1729 1729)
(test-congruence 2465 2465)
(test-congruence 2821 2821)
(test-congruence 6601 6601)
(newline)
(prime? 561)
(prime? 1105)
(prime? 1729)
(prime? 2465)
(prime? 2821)
(prime? 6601)
```

The output is

```
#t
#t
#t
#t
#t
#t

#f
#f
#f
#f
#f
#f
```

As we can see while the numbers pass the fermat test they are not primes thus we conclude that if a number is prime it passes the test but if it passes the test that does not mean that it is prime.
