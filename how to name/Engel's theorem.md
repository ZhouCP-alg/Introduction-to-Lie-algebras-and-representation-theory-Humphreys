# Engel's theorem

Engel定理的证明实际上可以算是有一定套路性的, 主要的思路实际上在高代中也比较常见: 降维+归纳.

## 1.定理表述
> **Theorem 1**
Let $V$ be a nonzero finite-dimensional vector space, and let $L$ be a subalgebra of $\mathfrak{gl}(V)$. If every element of $L$ is nilpotent, then there exists a nonzero vector $v\in V$ such that $L.v=0$.

即linear Lie algebra $L$中每个元素幂零时, 线性空间$V$上存在一个非零向量使得对于$L$中任一变换这个向量都是它的关于$0$特征值的特征向量.

## 2.证明思路
当L的维数为 $0$ 或 $1$ 时, 这个结论是显然的. 于是利用归纳法, 只要我们能从 $L$ 中分离出一个维数更低的子代数 $K$, 那么就可以尝试利用归纳法. 但是这还不够, 因为子代数确实可以利用归纳法, 但 $L$ 无法仅仅通过子代数得到结论, 所以我们最好是能得到 $L=K\oplus I$, 其中$K$和$I$都是理想; 更进一步如果能得到$I$的维数为1, 即 $I=Fz$ for some $z\in L$, 那么也就不需要对维数进行讨论.

考虑 $K$ 是 $L$ 的一个真子代数, 为了满足上述的条件, 不妨设 $K$ 是一个极大的真子代数. 于是对于任意的 $x \in K$ 容易知道 $x$ 也是幂零的, 而且 $K$ 在 $ad_x$ 下也是 stable 的, 这样一来在线性空间$L/K$上有由 $ad_x$ 诱导的线性变换, 这里不带歧义的也记为$ad_x$. 那么这些线性变换同样构成一个关于$\mathfrak{gl}(L/K)$的 Lie 子代数, 并且它的维数显然小于 $L$ 的维数. 于是由归纳假设存在一个 $y+K \in L/K$ 满足 $ad(K).(y+K)=0$. 又因为 $K$ 是一个理想, 所以 $[yK] \subseteq K$, 即$y \in N_L(K)$, 但是$y\notin K$, 所以$K \subsetneq N_L(K)$. 但是又同时注意到 $K$ 是极大的, 故只能是 $N_L(K)=L$, 即 $K$ 是 $L$ 的一个理想.

此时我们终于从 $L$ 中分离出一个理想, $L/K$ 也不在仅仅是子空间而是一个 quotient Lie algebra. 但是如果这个 quotient 不是特别好, 我们还需要对维数进行比较复杂的讨论, 也许"极大"这个条件可以让 $K$ 的 codimension 为 1? 如果 $\operatorname{dim} L/K > 1$, 根据同构定理知 $L/K$ 中的理想与 $L$ 中包含 $K$ 的理想一一对应, 又维数大于 1, 所以存在一个严格包含 $K$ 但却是 $L$ 的真理想, 与极大矛盾, 故只能有 $\operatorname{dim} L/K=1$. 

其实到这里整个证明也就接近尾声了, 因为接下来只要对 $K$ 再使用归纳假设, 将满足 $K.v=0$ 的向量打包再验证 $L=K \oplus Fx$ 中的 $Fx$ stabilizes 它就行了. 令 $W=\{ v \in V \mid K.v=0 \}\neq 0$, 注意到对于 $x\in L, y\in K, w\in W$, 有 $[xy] \in K$ 并且
$$
y.(x.w)=yx.w=xy.w-[xy].w=x.(y.w)-[xy].w=0.
$$
由于 $x$ 也是幂零的, 所以存在 $v \in W$ s.t. $x.v=0$ and $K.v=0$, 也即 $L.v=0$.

## 3.进一步讨论
- 由 Theorem 1 可以推出 Engel's theorem, 定理的表述如下
> **Engel's Theorem**
If all elements of $L$ are ad-nilpotent, then $L$ is nilpotent.

- 证明依旧是采用归纳法, 此时不再讨论. 除此之外, 通过归纳法也可以证明 $L$ 中的元素可以同时严格上三角化 (这里不严谨的不区分 $L$ 与 $ad(L)$), 证明也比较简单, 书上是使用 flag 来叙述, 很容易看出 $x.V_{i} \subseteq V_{i-1}$. 这其实可以和后面的 Lie's theorem 做个简单的对比: Lie 定理可以看成对此处条件的"弱化", Lie 定理只要求 $L$ 是可解的并且得到的结论也不是零化某个向量, 而是存在一个公共的特征向量. 那么可预见的, 它的证明大概率也是使用归纳法并且应当有 $x.V_{i} \subseteq V_{i-1}$.












