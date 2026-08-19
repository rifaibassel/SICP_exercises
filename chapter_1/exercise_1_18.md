```scheme
(define (even? n)
  (= (remainder n 2) 0)
  )

(define (* a b)
  (if (= b 0) 0
      (+ a (* a (- b 1)))))

(define (double a)
  (* a 2))

(define (square a)
  (* a a)
  )

(define (halve a)
  (if (even? a) (/ a 2))
  )

(define (fast-mult a b c)
  (cond ((= c 0) a)
        ((= b 0) a)
        ((even? c) (fast-mult a (double b) (halve c)))
        (else (fast-mult (+ b a) b (- c 1))))
  )

(define (mult a b)
  (fast-mult 0 a b)
  )
```
