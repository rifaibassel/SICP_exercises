```scheme
(define (square x)
  (* x x)
  )

(define (good-enough? prev-guess guess)
  (define delta (abs(- guess prev-guess)))
  (< (* (/ delta prev-guess) 100) 1)
  )

(define (improve-cbrt guess x)
  (/ (+(/ x (square guess)) (* 2 guess)) 3)
  )

(define (cbrt-iter prev-guess guess x)
  (if (good-enough? prev-guess guess)
      guess
      (cbrt-iter guess (improve-cbrt guess x) x))
  )

(define (cbrt x) (cbrt-iter 10000 1.0 x))
```
