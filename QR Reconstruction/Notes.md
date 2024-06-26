

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
 >[!important]
 >indicators of masking and error correction level placed twice
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
>Masking is a maximum... maybe affects $$A_{1}\hat x\le \hat b_{1}$$penalty score

TODO:
1. Code to turn directional sums into block of linear system
2. remove known pixels from linear system
3. Find ICP solver and make sure it works



>[!note]
>Size 29 QR code has 7 0 bits at the end of the message for padding, could we use this to determine masking?

TODO:
Are the syndromes exactly 0 or just $0\in\text{GF}(256)$?
How big do the syndromes get?
Explain $\text{GF}(4)$


Idea:
1. Preprocess the normal number data using cutting planes, remove large sections of the solution space
2. Put this into the Galois Field solver


TODO:
1. Given encoded polynomial $E(X)$ and $k$, form a linear system representing the syndromes
2. Code that takes in a (underdetermined) linear system in $\text{GF}(256)$ (think about whether we want this in bytes or bits)
	1. Gaussian elimination -> locate pivots and free variables
	2. Then rewrite the system where only unknowns are the free variables (an able to solve back for the pivots)

>[!question]
>Can we frame the directional sums as a linear equation in $GF(256)$?

1. Add parity of directional sums to linear system
2. Logic in ILP (Big M)
	1. solution using boolean arithmetic: https://cs.stackexchange.com/questions/12102/express-boolean-logic-operations-in-zero-one-integer-linear-programming-ilp
3. Reed-Solomon on the identifier strip
	1. It seems like we can't use $\text{GF}(2)$ *because* the length of the format strip is longer than $2$
	2. why don't the format strings need to have an even number of 1s?
	3. Not RS - BCH https://en.wikiversity.org/wiki/Reed–Solomon_codes_for_coders#BCH_codes
4. Relationship between the error correction bits and $n$ and $k$ 
5. Use the encoding type bits for the mask in addition to the padding ones
6. Can we 
7. Is there a linear equation in $\text{GF}(256)$ that restricts $x_i$ to $0$ or $1$?

If the encoded data still is less than the maximum capacity, add 236 (_11101100_) and 17 (_00010001_) as bytes to the end of the string, repeating as necessary until the data has reached the maximum length.

Format information error correction:
Now we generate 10 error correction bits for the first 5 bits using the same process as the [Version Error Correction Bits](https://observablehq.com/@zavierhenry/encoding-qr-codes#versionErrorCorrectionBits) section. In this case, the message polynomial is the 5 bits described in the previous section and the generator polynomial is $x^{10}+x^8+x^5+x^4+x^2+x+1$ or $10100110111$.

Afterwards, we XOR the 15 bits with the pattern $101010000010010$ to get the final format information string.
- since the format error correction is done bitwise, it gives us 10 equations!

This is placed left to right and bottom to top


From wikiversity:
The process for checking the encoded information is similar to long division, but uses exclusive-or instead of subtraction. The format code should produce a remainder of zero when it is "divided" by the so-called generator of the code. QR format codes use the generator $10100110111$ ($x^{10}+x^{8}+x^{5}+x^{4}+x^{2}+x+1$).
- Need to figure out zeros (in $\text{GF}(256)$?) of this generator
	- this will give us the analogy of the syndromes equations in RS

Except, this isn't quite right, because we XOR after...

>[!note]
>Instead of removing $x_{i}$ from the system if it is known, we can add an equation.

TODO:
- Once we have a possible solution, can we find another solution quickly?
	- what about this? https://cs.stackexchange.com/questions/62926/finding-all-solutions-to-an-integer-linear-programming-ilp-problem
- Add the inequalities from masking-padding
- what's the situation for the other encoding types


Probing:
- ILP maximizes something subject to $Ax=b$ and $A_{2}x≤c$ and $x\in\{0,1\}$
- Linear Programming: same thing, but $0≤x_{i}≤1$. (this is in [[P]])
- $LP_{max}$ does Linear programming with a maximization condition. ie maximize $x_{i}$, to see if it can be 1


TODO:
- What's the relationship between EC level and EC bytes
	- EC level (as a percentage) is the percentage of the total number of bytes we want to recover.
	- If total bytes is 44 (version 2) and we want to recover 25% (quartile EC), then we need 22 EC codewords. 
	- We think there is room for 70 bytes in a version 3
		- how can we check this?
		- how can we check how many error correction bytes there are for each level?

>[!question]
>Can we treat the directional sums system as a system in $GF(29)$? If so, would that help us?

RAP: 695972
7:30 on April 16

TODO:
- Find rank of full system in $\text{GF}(256)$
- What approaches are like ILP in a finite field?

TODO:
- Debug the GF matrix
- Add the encoding type equations to the matrix $A$
- Solving the finite field system:
	- "Alternating Projections"
	- Things to satisfy in $\text{GF}(256)$:
		1. $A x=b$
		2. $x_{i}\in\{0,1\}$
	- Projection onto (1) - google projection onto column space
		- need to modify the formula for order: $$A(A^{T}A)^{-1}A^{T}$$
	- Projection onto (2) go from codeword to its representation in binary

Questions:
- bug
- where to project
- solution space-null space?
- knight's tour


Start with a valid QR Code
Change at least 23 codewords (changing less would let error correction project back to previous)
- choose pixels based on which directional sums are furthest from being satisfied

Fix 22 bytes to leave out of ILP. Adjust directional sums. Find a feasible solution. Fill in the rest with EC. Check the directional sums.


TODO:
- Look at 

Look at matrix A with all of the 1-constraints and directional sum upper bounds.

>[!question]
Can we only add upper bounds and then maximize or look only at vertices.
