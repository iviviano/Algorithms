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
>- $R^{k}=$ [[Language Concatenation]]ion of $R$ $k$ times

>[!example] Examples
>- $\Sigma\Sigma=\{w:|w=2\}$
>- $(\Sigma \Sigma)^{*}=\{w:|w|\text{ is even}\}$
>- $\texttt{a}^{*}(\texttt{baa}^{*})^{*}=\{w:\text{ every }\texttt{b} \text{ in }w \text{ is followed by at least one }\texttt{a}\}$
>- $(\texttt{a}|\varepsilon)b^{*}= \texttt{ab}^{*}|\texttt{b}^{*}$
>- $$L((\texttt{a}|\texttt{bb})(\varepsilon|\texttt{a}))=\{\texttt{a},\texttt{bb},\texttt{aa},\texttt{bba}\}$$
>- $$L((\texttt{a}|\varepsilon)(a|\varepsilon))=\{\texttt{aa},\texttt{b},\varepsilon\}$$
$$(\texttt{a}|\texttt{b})^*(\texttt{ba})^{2}(\texttt{a|b})^{*}=\{w:\texttt{baba}\text{ is a substring of }w\}$$
$$(\texttt{a|b|baba})^{*}$$
>- $$(\Sigma a \Sigma^{*})|(\Sigma^{*}b \Sigma^{2})=\{w:\text{the second symbol of }w \text{ is }\texttt{a} \text{ or the third to last symbol of }w \text{ is }\texttt{b}\}$$
>- a regular expression $R^*$ contains one string if $R=\varepsilon$ or $R=\emptyset$. Otherwise $R^{*}$ is infinite. 
>- $R|\emptyset=R$
>- $R\circ \epsilon=R$
>- $(R_{1}|R_2)R_3=R_1R_3|R_2R_3$
>- $(R_1^*)^*=R_1^*$
>- $(R_1|R_2)^*=(R_1^*R_2^*)^*$
