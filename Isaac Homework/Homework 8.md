>[!note] 1


>[!note] 2

(a) False 

(b) 

>[!note] 3


1. Adjust graph to follow new constraints
	1. locate edge where change occurred 
	2. find path to this edge
	3. reduce all edge weights by 1 along this path 
2. Perform 1 iteration of the FF algorithm

Proof idea:

- this change either reduces the max flow in the graph by one or does not change it

this might not work if there is a "completely different" flow that is also a max flow for the graph