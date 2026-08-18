# Induction proof of Fib(n) = $\phi^n - \psi^n / \sqrt{5}$

## Base Case n = 0

Fib(0) is defined as being equal to 0
$\frac{\phi^0 - \psi^0}{\sqrt{5}}$
$\frac{1 - 1}{\sqrt{5}}$
$0$
LHS is equal to RHS
Base case is true

## Base Case n = 1

Fib(1) is defined as being equal to 1
$\frac{\phi^1 - \psi^1}{\sqrt{5}}$
$\frac{(1+\sqrt{5}) / 2 - (1-\sqrt{5}) /2} {\sqrt{5}}$
$\frac{0 + 2 \sqrt{5} / 2}{\sqrt{5}}$
$1$
LHS is equal to RHS
Base case is true

## Induction step: We assume Fib(n) = $\phi^n - \psi^n / \sqrt{5}$ and Fib(n-1) = $\phi^{n-1} - \psi^{n-1} / \sqrt{5}$

## n + 1 case

LHS: Fib(n+1) = Fib(n) + Fib(n - 1)

     Fib(n+1) = \frac{$\phi^n - \psi^n / \sqrt{5}$ + $\phi^{n-1} - \psi^{n-1}}{\sqrt{5}}$

     Fib(n+1) = $\frac{\phi^n + \phi^{n-1} - \psi^n - \psi^{n-1}} {\sqrt{5}}$

     Fib(n+1) = $\frac{\phi^{n-1} * (\phi  + 1) - \psi^{n-1} * (\psi + 1)} {\sqrt{5}}$

We remember that due to the definition of the of the golden ratio we have $\phi + 1 = \phi^2$

     Fib(n+1) = $\frac{\phi^{n-1} * \phi^2 - \psi^{n-1} * \psi^2} {\sqrt{5}}$

     Fib(n+1) = $\frac{\phi^{n+1} - \psi^{n+1}}{\sqrt{5}}$

LHS = RHS

By the principle of mathematical induction Fib(n) = $\frac{\phi^n - \psi^n}{\sqrt{5}}$ for $n >= 0$
