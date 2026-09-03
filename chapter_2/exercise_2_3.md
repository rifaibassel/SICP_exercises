```scheme
;First representation
(define (make-rect bot-left-corner upp-right-corner)
  (cons bot-left-corner upp-right-corner)
  )

(define (get-rect-bot-left-corner rect)
  (car rect)
  )

(define (get-rect-top-right-corner rect)
  (cdr rect)
  )

(define (get-rect-length rect)
  (- (y-point (get-rect-top-right-corner rect)) (y-point (get-rect-bot-left-corner rect)))
  )

(define (get-rect-width rect)
  (- (x-point (get-rect-top-right-corner rect)) (x-point (get-rect-bot-left-corner rect)))
  )

(define (get-rect-area rect)
  (* (get-rect-length rect) (get-rect-width rect))
  )

(define (get-rect-perim rect)
  (* 2 (+ (get-rect-length rect) (get-rect-width rect)))
  )

;Second representation 
(define (make-rect length-segment width-segment)
  (cons length-segment width-segment)
  )

(define (get-rect-length rect)
  (- (y-point (end-segment rect)) (y-point (start-segment rect)))
  )

(define (get-rect-width rect)
  (- (x-point (end-segment rect)) (x-point (start-segment rect)))
  )

(define (get-rect-area rect)
  (* (get-rect-length rect) (get-rect-width rect))
  )

(define (get-rect-perim rect)
  (* 2 (+ (get-rect-length rect) (get-rect-width rect)))
  )
```
