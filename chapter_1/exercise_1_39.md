```scheme
(define (tan-cf x k)
  (cont-frac-iter (lambda (i)
                    (if (= i 1) x
                        (* (square x) -1))
                    )
                  (lambda (i)
                            (- (* 2.0 i) 1)
                      ) k)
  )
```
