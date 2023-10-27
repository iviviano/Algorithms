---
mathLink: segmented least squares problem
---
Given points $$P=\{(x_{1},y_{1}),\ldots,(x_{n},y_{n})\}$$least squares finds "line of best fit". Minimize $$\sum(ax_{i}+b-y_{i})^{2}$$for fit line $y=ax+b$.

>[!def]
>*Segmented least squares* uses multiple linear fits to approximate different regions of the data set. This is done by [[Partition]]ing $P$ and then computing the least squares for each partition.

Best fit errors: $$\sum_{i\in P_{k}}(y_{i}-(a_{k}x_{i}+b_{k}))^{2}$$So, the goal is to minimize $$C=\sum C_{j}=\sum_{j=1}^{k}\sum_{i\in P_{j}}(y_{i}-(a_{j}x_{i}+b_{j}))^2$$but this allows overfitting, we could just have $n$ lines.

