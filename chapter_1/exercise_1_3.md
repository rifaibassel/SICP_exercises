```
(define
  (twoLargerSquareSums x y z)
  (cond ((and (< x z) (< x y)) (+ (* y y) (* z z)))
        ((and (< y x) (< y z)) (+ (* x x) (* z z)))
        ((and (< z x) (< z y)) (+ (* x x) (* y y)))
  ))
```
