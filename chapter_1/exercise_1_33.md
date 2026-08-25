```scheme
(define (filtered-accumulate combiner null-value term a next b filter?)
  (define (iter a result)
    (if (> a b)
        result
        (iter (next a) (combiner result (if (filter? a)
                           (term a)
                           null-value
  )
              )
        )
    )
)

(define (square-prime-sum a b)
  (filtered-accumulate + 0 square a increment b prime?)
)

(define (relatively-prime-product n)
  (define (rpp-filter? a)
    (relatively-prime? a n)
    )
  (filtered-accumulate * 1 identity 1 increment n rpp-filter?)
  )  ```
