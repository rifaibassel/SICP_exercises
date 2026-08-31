```scheme
(define (cont-frac n d k)
  (define (helper i)
    (if (= i k)
        (/ (n k) (d k))
        (/ (n i) (+ (d i) (helper (+ i 1))))
    )
    )
  (helper 1)
  )
```

k = 11 is the smallest value to get an approximation that is accurate to 4 decimal places

```scheme
(define (cont-frac-iter n d k)
    (define (iter i result)
      (if (= i 0)
          result
          (iter (- i 1) (/ (n i) (+ result (d i))))
          )
      )
    (iter k 0)
  )
```
