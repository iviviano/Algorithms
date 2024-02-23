

[[Finite Field]]s: example $\mathbb{Z}_2$. 

We will use integers mod 2 for binary signal




[[Read-Solomon]] for [[QR Code]]s
- [[Finite Field]]
- code type, parameters
- [[Lagrange Interpolation]]
- prepare an example

[[QR Code]] structure:
- squares in the corners - help with determining orientation
- certain pixels known zero or one
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
	- question: what is the relationship between error correction level and 