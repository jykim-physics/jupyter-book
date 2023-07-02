# Error propagation formula

## Formulae 

Variables: $A,B$
Standard deviation: $\sigma_A, \sigma_B$
Correlation: $\rho_{AB}$
Covariance: $\sigma_{AB}=\rho_{AB}\sigma_A\sigma_B$
(Constant number: $a,b$)
In table: $A,B$ = Expectation value
| Function $f$| Variance |
| ------ | ------ |
| $aA$ | $\sigma_f^2=a^2\sigma_A^2$ |
| $aA+bB$ | $\sigma_f^2=a^2\sigma_A^2+b^2\sigma_B^2+2ab\sigma_{AB}$ |
| $aA-bB$ | $\sigma_f^2=a^2\sigma_A^2+b^2\sigma_B^2-2ab\sigma_{AB}$ |
| $AB$ | $\sigma_f^2/f^2\approx (\sigma_A/A)^2+(\sigma_B/B)^2+2\sigma_{AB}/AB$ |
| $A\over B$ | $\sigma_f^2/f^2\approx (\sigma_A/A)^2+(\sigma_B/B)^2-2\sigma_{AB}/AB$ |
| $f(A,B,C)$ | $\sigma_f^2\approx ({\partial f \over \partial A}\sigma_A)^2+({\partial f \over \partial B}\sigma_B)^2+({\partial f \over \partial C}\sigma_C)^2+\text{cross terms}$ |

### Basic examples

- $z = x + y$
    - $\delta z = \sqrt{\delta x ^2 + \delta y^2}$
- $z = x  y$
    - ${\delta z \over z} = \sqrt{(\delta x /x)^2 + (\delta y/y)^2}$
        - proof.
        $z = xy\\
        \ln z=\ln x + \ln y\\
        \delta \ln z = \sqrt{(\delta\ln x )^2 + (\delta\ln y )^2}\\
        {\delta z \over z} = \sqrt{({\delta x \over x})^2 + ({\delta y \over y})^2}$ or ${\delta z} = z\sqrt{({\delta x \over x})^2 + ({\delta y \over y})^2}$
- $z=f(x)$
    - $\delta z = |f'(x)|\delta x$
    - How about error of $\sqrt x$ when $x$ measured as $100 \pm 6$?\
    Let $f(x)=\sqrt x, f'(x)=1/(2\sqrt x)$\
    $\to \delta f = f'(x)\delta x =1/(2\sqrt{100}) \times 6=6/20=0.3$\
    Then, $\sqrt{x}=10.0 \pm 0.3$

- $f = x/(y-z), x=200\pm2,y=50\pm3,z=40\pm4$
    - Let's estimate first $\delta(y-z)=\sqrt{\delta y^2 + \delta z^2}=\sqrt{3^2 + 4^2}=5$\
    Then, $y-z=10\pm5$\
    $\delta(x/(y-z))=(200/10)\sqrt{(2/200)^2 + (5/10)^2}=20\sqrt{0.01^2 + 0.5^2}\\
    \to f = 20\pm 20\sqrt{0.01^2 + 0.5^2}$