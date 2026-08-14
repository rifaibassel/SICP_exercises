Input: 10 Result: 10

Input: (+ 5 3 4) Result: 12

Input: (- 9 1) Result: 8

Input: (/ 6 2) Result: 3

Input: (+ (*2 4) (- 4 6)) Result: 6

Input: (define a 3) Result: Defines a as 3

Input: (define b (+ a 1)) Result: Defines b as a + 1 (4)

Input: (+ a b (* a b)) Result: 19

Input: (= a b) Result: False

Input:

```
(cond ((= a 4) 6)
      ((= b 4) (+ 6 7 a))
      (else 25))
(+ 2 (if (> b a) b a))
(* (cond ((> a b) a)
         ((< a b) b)
         (else -1))
   (+ a 1))
```

Result: 16, 6, 16
