---
mathLink: regular expression
---
>[!def]
>We say that $R$ is a *regular expression* for some [[Alphabet]] $\Sigma$,
>1. $a$ for some $a\in \Sigma$
>2. $\epsilon$
>3. $\emptyset$
>4. $(R_{1}\cup R_{2})$ where $R_{1},R_{2}$ are regular expressions
>5. $(R_{1}\circ R_{2})$ where $R_{1},R_{2}$ are regular expressions, or
>6. $(R_{1}^{*}),$ where $R_{1}$ is a regular expression

>[!note]
>If parentheses are omitted, precedence order is [[Star]], then [[Language Concatenation]]ion, then [[Language Union]]. Some shorthands:
>- $R^{+}=RR^{*}$
>- $R^{k}$