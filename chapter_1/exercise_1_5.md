In the applicative order interpreter we will reach an infinite loop as applicative order first evaluates the arguments, and when evaluating the procedure p we find that it returns itself, so it will keep returning itself.

In the normal order interpreter we will get a result of 0, this is because the normal order evaluation evaluates the procedures to primitive procedures and then evaluates the arguments as they are needed.

Since we are given that the special form if evaluates the predicate first, then it has no need to evaluate the parameter y and only needs to evaluate x which returns true for the predicate and the procedure returns 0 instantly without looking at y.
