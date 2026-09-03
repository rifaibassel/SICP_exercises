```scheme
(define (make-point x y)
  (cons x y)
  )

(define (x-point point)
  (car point)
  )

(define (y-point point)
  (cdr point)
  )

(define (make-segment x y)
  (cons x y)
  )

(define (start-segment segment)
  (car segment)
  )

(define (end-segment segment)
  (cdr segment)
  )

(define (mid-point-segment segment)
  (make-point (average (x-point (start-segment segment)) (x-point (end-segment segment))) (average (y-point (start-segment segment)) (y-point (end-segment segment))))
  )
```
