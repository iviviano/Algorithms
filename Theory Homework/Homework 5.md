>[!1]

$A=\{w|w\in\{\texttt{a},\texttt{b}\}^{*}\text{ has more }\texttt{a}\text{'s than }\texttt{b}\text{'s}\}$

$$\begin{align*}
S&\rightarrow \texttt{a}S\ |\ S \texttt{a}\ |\ \texttt{b}S \texttt{a}\ |\ \texttt{a}S \texttt{b}\ |\ \texttt{a}
\end{align*}$$

>[!2]

$B=\{w\#x|w,x\in\{\texttt{a,b}\}^{*}\text{ and }w^{\mathcal{R}}\text{ is a substring of }x\}$

$$\begin{align*}
S&\rightarrow UV\\
U&\rightarrow \#V\ |\ \texttt{a}U \texttt{a}\ |\ \texttt{b}U \texttt{b}\\
V&\rightarrow \texttt{a}V\ |\ \texttt{b}V\ |\ \varepsilon
\end{align*}$$
>[!3]

$C=\{\texttt{a}^{m}\texttt{b}^{n}\texttt{c}^{k}|m,n>0\text{ and }k=m+n\}$. 

$$\begin{align*}
S&\rightarrow \texttt{a}S
\end{align*}$$