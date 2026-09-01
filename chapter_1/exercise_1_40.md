```scheme
(define (cubic a b c)
  (lambda (x)
    (+ (cube x) (* a (square x)) (* b x) c)
    )
  )

(newton-method (cubic 2 3 4) 1.0)
```
