>[!note] 1



>[!note] 2


Attach the source to each person with capacity 1. Attach every dining hall $j$ to the sink with capacity $C_{j}$. Attach each person $i$ to each dining hall in $S_i$ with capacity 1.

Compute [[Max Flow Problem]] on $G$. Return `false` if $|f|<n$. 


>[!note] 3

Source $s$ with demand $-k$. Connect $s$ to each person $i$ with edge $e=(s,i)$. Let $c(e)=7$,  $l(e)=5$, and $d(i)=0$. Connect each person $i$ to each job $j\in L_{i}$ with edge $e=(i,j)$. Let $c(e)=1,l(e)=0$, and $d(i)=0$. Connect each job $j$ to the sink $t$ with edge $e=(j,t)$. Let $c(e)=1,l(e)=0$, and $d(t)=k$. 