```scheme
(define (smooth f dx)
  (lambda (x)
    (/ (+ (f x) (f (- x dx)) (f (+ x dx))) 3)
    )
  )

 (define (n-smooth f n)
   ((repeated-iter (lambda (g) (smooth g 0.001)) n) f)
   ) 
```
