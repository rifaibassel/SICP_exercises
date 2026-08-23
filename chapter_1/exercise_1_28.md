```scheme
(define (expmod-M-R base exp m)
  (cond ((= exp 0) 1)
        ((even? exp) (square-test (expmod-M-R base (/ exp 2) m) m))
        (else (remainder (* base (expmod-M-R base (- exp 1) m)) m))))

(define (square-test num-to-square number-to-mod-by)
  (if (and (not (= num-to-square 1)) (not (= num-to-square (- number-to-mod-by 1))) (= (remainder (square num-to-square) number-to-mod-by) 1)) 0
      (remainder (square num-to-square) number-to-mod-by)
  )
  )

(define (M-R-test n)
  (define (try-it a)
    (= (expmod-M-R a (- n 1) n) 1)) 
  (try-it (+ 1 (random (- n 1)))))
```
