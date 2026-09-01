```scheme
(define (iter-improve good-enough? improve-guess)
  (lambda (guess)
    (define (try guess)
      (let ((next (improve-guess guess)))
        (if (good-enough? guess next)
            next
            (try next))))
  (try guess)))

(define (sqrt-iter-improve x)
  ((iter-improve (lambda (guess next) (< (abs (- (square guess) x)) tolerance)) (lambda (guess) (average guess (/ x guess)))) 1.0)
  )

(define (fixed-point-iter f first-guess)
  ((iter-improve (lambda (x y) (< (abs (- x y)) tolerance)) (lambda (guess) (f guess))) first-guess)
  )
```
