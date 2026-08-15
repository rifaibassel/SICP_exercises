We will get an infinite loop.

This is because even though cond only evaluates a clause if the previous clause(s) were false we are wrapping it in a procedure.

Wrapping it in a procedure leads to applicative-order evaluation, and one of the arguments is the function square-iter.

This leads to a call to the function again and the infinite loop.
