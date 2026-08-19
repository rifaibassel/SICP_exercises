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

(define (fast-multt a b)
  (cond ((or (= b 0) (= a 0)) 0)
        ((even? b) (double (fast-multt a (halve b))))
        (else (+ a (fast-multt a (- b 1))))
  )
  )
```
