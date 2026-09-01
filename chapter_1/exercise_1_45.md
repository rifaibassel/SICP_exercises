```scheme
(define (pow x n)
  (define (iter i result)
    (if (= i n)
        result
        (iter (+ i 1) (* x result))
    )
   )
  (iter 0 1)
  )

(define (log2 x)
  (/ (log x) (log 2)))

(define (compute-n-roots x n)
  (fixed-point ((repeated-iter average-damp (floor (log2 n))) (lambda (y) (/ x (pow y (- n 1))))) 1.0) 
  )
```
