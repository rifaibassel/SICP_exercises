```scheme
(define (product term a next b)
  (define (iter a result)
    (if (> a b)
        result
        (iter (next a) (* result (term a)))
    )
  )
  (iter a 1)
  )

(define (factorial n)
  (product identity 1 increment n)
  )

(define (pi-product n)
  (define (pi-term a)
    (cond ((= a 0) (/ 2.0 3.0))
          ((even? a) (/ (+ 2.0 a) (+ 3.0 a)))
          (else (/ (+ 3.0 a) (+ 2.0 a)))
      )
    )
  (* 4 (product-recursive pi-term 0 increment n))
```

```scheme
(define (product-recursive term a next b)
  (if (> a b)
      1
      (* (term a)
         (product-recursive term (next a) next b))))
```
