```scheme
(define (Make-rat n d)
  (let ((g (gcd n d)))
    (cond ((and (< n 0) (< d 0)) (cons (/ (* -1 n) g) (/ (* -1 d) g)))
          ((and (> n 0) (> d 0)) (cons (/  n g) (/  d g)))
          ((< n 0) (cons (/ n g) (/ d g)))
          ((< d 0) (cons (/ (* -1 n) g) (/ (* -1 d) g)))
          )
  )
  )
```
