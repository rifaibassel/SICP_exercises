```scheme
(define (repeated f n)
  (define (helper i)
    (if (= i n)
        f
        (compose f (helper (+ i 1)))
        )
    )
  (helper 1)
  )

(define (repeated-iter f n)
  (define (iter i result)
    (if (= i 1)
        result
        (iter (- i 1) (compose f result))
        )
    )
  (iter n f)
  )
```
