

[[Finite Field]]s: example $\mathbb{Z}_2$. 

We will use integers mod 2 for binary signal




[[Read-Solomon]] for [[QR Code]]s
- [[Finite Field]]
- code type, parameters
- [[Lagrange Interpolation]]
- prepare an example

Start with 29 x 29 QR Code (Need prime dimensions)

[[QR Code]] structure:
- squares in the corners - help with determining orientation
- certain pixels known zero or one (may depend on [[QR Code]] type, different types of same size, but probably only at larger sizes)
- indicators of 
	- level of [[Read-Solomon]] error correction
	- length of message
	- type of message
	- alphabet
- Masking
	- inverts certain regions, so that it is easier to scan
	- question: if I read some of the code works and had strong enough error correction, would I be able to figure out the masking?
	- eight kinds of maskings
- reading order and location of redundancy 
	- question: what is the relationship between error correction level and message length

![[1056px-QR_Code_Unmasked.svg.png]]

Directional Sums: For p x p array, 
- $p+1$ possible directions:
	- slope 0, $\infty$
- of original image




 TODO:
 - Find existing Python QR Code generation [[https://github.com/nayuki/QR-Code-generator/tree/master/python]]
 - Write framework that can read in a an N x N binary image
 - Data generation- directional sums
 - data reduction based on fixed structure
	 - subtract 1 from every directional sum going through a certain pixel... 







Integer Linear Programming:
maximize $$c_{1}x_{1}+c_{2}x_{2}+\cdots +c_{3}x_{n}$$where $$\hat x=\begin{bmatrix}x_{1}\\\vdots \\x_{n}\end{bmatrix}$$subject to $$\begin{align*}
A_{1} \hat x&\le \hat b_{1}\\
A_{2}\hat x&= \hat b_{2}\\
x_{i}&\in\{0,1\}
\end{align*}$$
Our case:
directional sums is the $$A_{2}\hat x=\hat b_{2}$$


>[!question]
>Masking is a maximum... maybe affects ...