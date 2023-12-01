Input:
- Undirected [[Graph]] $G=(V,E)$

Output:
- A [[Subset]] $S\subseteq V$ such that 
	1. For all $e\in E$ at least one endpoint of $e$ belongs to $S$
	2. $|S|$ is minimized

Claim: $S$ is an [[Independent Set]] [[iff]] $V-S$ is a vertex cover. 
Follows from the definitions:
$S$ is an [[Independent Set]] [[iff]] for all $(u,v)\in E$, $u\notin S$ or $v\notin S$. [[iff]] $u\in V-S$ or $v\in V-S$ [[iff]] $V-S$ is a vertex cover

Therefore, the minimum vertex cover is the same as the maximum [[Independent Set]]. So, [[Vertex Cover Problem]] $=_{p}$ [[Independent Set Problem]].

Claim: [[Vertex Cover Problem]] $≤_{p}$ [[Set Cover]]
$U=E$
$S=\{S_{j}=\{\{i,j\}\in E:i\in V\}:j\in V\}$. 