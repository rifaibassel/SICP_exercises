```scheme
(define (approx-e k)
  (+ (cont-frac-iter (lambda (i) 1.0)
                  (lambda (i)
                    (cond ((= (remainder i 3) 2) (/ (* (+ i 1) 2) 3))
                          (else 1)))
                  k) 2)
  )
```
