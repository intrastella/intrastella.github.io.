---
layout: cheat_sheet
category: linear_algebra
out: 1
topic: representation
title: Matrix Representation
permalink: /linear_algebra/representation
---

_____________________________________________________________________________________________________________________________________

<br/>

#### Introduction

<br/>

Every linear map $$ f \in \mathcal L(\mathcal V, \mathcal W ) $$ between two vector spaces $$ \mathcal V$$ and  $$\mathcal W $$ has a unique matrix representation. In most fields where one uses numerical approaches to solve problems
a matrix representation is preferred to do any calculations due to practicality and opportunity of parallelizing computations. This section is a short summary of matrix representation.

<br/>

{% include res_img.html url="/images/separator.png" width="800px" %}

<br/>

#### Approach to obtain the Matrix Representation

<br/>

Let $$\mathcal V (\mathbb{F}) $$ and $$\mathcal W (\mathbb{F}) $$ be two vector spaces over a field $$\mathbb{F} $$ and let $$\mathcal B_{1} = \{b_{1}, ..., b_{n} \} $$ 
and $$\mathcal B_{2} = \{\hat{b_{1}}, ..., \hat{b_{m}} \} $$  be two basis for $$\mathcal V $$ and $$\mathcal W $$ respectively. Further let $$ f \in \mathcal L
(\mathcal V, \mathcal W ) $$ be a homomorphism.
{% include latex_high.html latex1="Then for $$ f(b_{j}) \in \mathcal W $$" content_txt="/c/there exists uniquely defined coordinates/c/" latex2="$$ \alpha_{1, j}, ..., \alpha_{n, j} \in \mathbb{F} $$ such that:" %}


<br>

$$ f(b_{j}) = (\hat{b_{1}}, ..., \hat{b_{m}})  \begin{bmatrix} \alpha_{1, j} \\ \alpha_{2, j} \\ \vdots \\ \alpha_{n, j} \end{bmatrix} $$

<br/>

This is a system of equations that can be extended so that we obtain one expression for all basis elements in $ \mathcal B_{1}$. For this denote $ A = [ \alpha_{i, j} ] \in \mathbb{F}^{m \times n} $ 
as the matrix of all coordinates from that system of equation:

<br/>

$$\begin{align} f(b_{1}, ..., b_{n}) = (f(b_{1}), ..., f(b_{n})) = (\hat{b_{1}}, ..., \hat{b_{m}}) \ A \end{align} $$

<br/>

Then we obtain for any $$ v = \sum_{i=1}^{\\n} \lambda_{i} b_{i}  \in \mathcal V $$ :

<br/>

$$\begin{align} f(v) &= f \ (\sum_{i=1}^{\\n} \lambda_{i} b_{i}) \\ 
&= (f(b_{1}), ..., f(b_{n}))  \begin{bmatrix} \lambda_{1} \\ \vdots \\ \lambda_{n} \end{bmatrix} \\
&= (\hat{b_{1}}, ..., \hat{b_{m}}) \ A \begin{bmatrix} \lambda_{1} \\ \vdots \\ \lambda_{n} \end{bmatrix} \end{align} $$

<br/>

The matrix representation of $$ f $$ is given by $$ A $$ and is denoted by $$ [f]_{B_{1}, B_{2}} $$.  The coordinates of $$ f(v) = w \in \mathcal{W} $$ is given by $$ \Biggl( [f]_{B_{1}, B_{2}} \begin{bmatrix} \lambda_{1} \\ \vdots \\ \lambda_{n} \end{bmatrix} \Biggl) $$
where $$ {\lambda_{1}, ..., \lambda_{n}} $$ are the coordinates of $$ v $$.

<br/>

{% include collapse.html  id="ex1" title="&nbsp; Example"  collapsed_content="
Let $f \in \mathcal{L}(\mathbb{R}^{3}, \mathbb{R}^{2})$ and $\mathcal{B}_1 = \left\{ \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}, \begin{pmatrix} 0 \\ 2 \\ 1 \end{pmatrix}, \begin{pmatrix} 0 \\ 0 \\ 2 \end{pmatrix} \right\} $ be a basis of $\mathbb{R}^{3}$
and $\mathcal{B}_2 = \left\{ \begin{pmatrix} 3 \\ 1 \end{pmatrix}, \begin{pmatrix} 0 \\ 2  \end{pmatrix} \right\} $ be a basis of $\mathbb{R}^{2}$. Then $f$ is defined by:
$$ f \ : \mathbb{R}^{3} \longrightarrow \mathbb{R}^{2} , \quad \begin{pmatrix} v_1 \\ v_2 \\ v_3 \end{pmatrix} \longmapsto \begin{pmatrix} v_1 + 3v_2 \\ v_1 + 2v_3 \end{pmatrix} \ $$

<br>

Find the coordinates of $f\Biggl( \begin{pmatrix} 3 \\ 6 \\ 2 \end{pmatrix} \Biggl)$ w.r.t. $\mathcal{B}_2$.

<br>

<br>

<ins>SOLUTION</ins>:

<br>

<br>

1) We need to calculate the image of the basis $\mathcal{B}_1$ under f:

<br>

<br>

$ f \Biggl(  \Biggl( \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}, \begin{pmatrix} 0 \\ 2 \\ 1 \end{pmatrix}, \begin{pmatrix} 0 \\ 0 \\ 2 \end{pmatrix} \Biggl) \Biggl) =  \Biggl(f  \Biggl( \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}\Biggl), f \Biggl( \begin{pmatrix} 0 \\ 2 \\ 1 \end{pmatrix}\Biggl), f \Biggl( \begin{pmatrix} 0 \\ 0 \\ 2 \end{pmatrix} \Biggl) \Biggl) = 
 \Biggl( \begin{pmatrix} 1 \\ 1 \end{pmatrix}, \begin{pmatrix} 6 \\ 2 \end{pmatrix}, \begin{pmatrix} 0 \\ 4 \end{pmatrix}\Biggl)$ 

<br>

<br>

<br>

2) Now we want to obtain the matrix representation $[f]_{B_1, B_2}$: 

<br>

<br>

$[f]_{B_1, B_2} =

\begin{bmatrix}
3 & 0 \\
1 & 2 
\end{bmatrix}^{-1} 

\begin{bmatrix}
1 & 6 & 0 \\
1 & 2 & 4
\end{bmatrix} = 

\begin{bmatrix}
1/3 & 0 \\
-1/6 & 1/2 
\end{bmatrix}

\begin{bmatrix}
1 & 6 & 0 \\
1 & 2 & 4
\end{bmatrix} = 

\begin{bmatrix}
1/3 & 2 & 0 \\
1/3 & 0 & 2
\end{bmatrix}
$

<br>

<br>

<br>

3) Next we need to find the coordinates of $\begin{pmatrix} 3 \\ 6 \\ 2 \end{pmatrix}$ w.r.t. $\mathcal{B}_1$:

<br>

<br>

$\Phi_{\mathcal{B}_1} \Biggl( \begin{pmatrix} 3 \\ 6 \\ 2 \end{pmatrix} \Biggl) =

\begin{bmatrix}
1 & 0 & 0 \\
0 & 2 & 0 \\
0 & 1 & 2
\end{bmatrix}^{-1} 

\begin{pmatrix} 3 \\ 6 \\ 2 \end{pmatrix} = 

\begin{bmatrix}
1 & 0 & 0 \\
0 & 1/2 & 0 \\
0 & -1/4 & 1/2
\end{bmatrix}

\begin{pmatrix} 3 \\ 6 \\ 2 \end{pmatrix} = 

\begin{bmatrix} 3 \\ 3 \\ -1/2 \end{bmatrix}

$

<br>

<br>

<br>

4) Last but not least the coordinates of $f\Biggl( \begin{pmatrix} 3 \\ 6 \\ 2 \end{pmatrix} \Biggl)$ w.r.t. $\mathcal{B}_2$:

<br>

<br>

$\Phi_{\mathcal{B}_2} \Biggl( f \Biggl( \begin{pmatrix} 3 \\ 6 \\ 2 \end{pmatrix} \Biggl) \Biggl) =

[f]_{B_1, B_2} \begin{bmatrix} 3 \\ 3 \\ -1/2 \end{bmatrix} = 

\begin{bmatrix}
1/3 & 2 & 0 \\
1/3 & 0 & 2
\end{bmatrix}  

\begin{bmatrix} 3 \\ 3 \\ -1/2 \end{bmatrix} = \begin{bmatrix} 7 \\ 0 \end{bmatrix}
$

<br>

<br>

<br>

<ins>Let's check our result</ins>:

<br>

<br>

$$ 
\begin{pmatrix} 21 \\ 7 \end{pmatrix} = 
f\Biggl( \begin{pmatrix} 3 \\ 6 \\ 2 \end{pmatrix} \Biggl) =
\Biggl( \begin{pmatrix} 3 \\ 1 \end{pmatrix}, \begin{pmatrix} 0 \\ 2  \end{pmatrix}  \Biggl)  \Phi_{\mathcal{B}_2} \Biggl( f \Biggl( \begin{pmatrix} 3 \\ 6 \\ 2 \end{pmatrix} \Biggl) \Biggl) =

\begin{bmatrix}
3 & 0 \\
1 & 2 
\end{bmatrix}

\begin{bmatrix} 7 \\ 0 \end{bmatrix} =

\begin{pmatrix} 21 \\ 7 \end{pmatrix} \qquad \qquad \qquad \square

$$


"%}

<br/>

{% include res_img.html url="/images/separator.png" width="800px" %}

<br/>

#### Commutative Diagram

<br/>

Let $$ \mathcal{V}(\mathbb{F})$$ be an n-dimensional vector space and $$ \mathcal{B}_1, \ \mathcal{B}_2 $$ are some basis of $$ \mathcal{V} $$. $$ \mathcal{W}(\mathbb{F}) $$ 
is an m-dimensional vector space with basis $$ \mathcal{\hat{B}}_1, \ \mathcal{\hat{B}}_2 $$. The following commutative diagram captures the mappings of the (1) homomorphism, (2) coordinates, (3) identity and their matrix representations:

<br/>

$$\begin{align} 
&(1) \quad f \ : \mathcal V \longrightarrow \mathcal W , \quad v \longmapsto f(v) = w\\
&(2) \quad \Phi_B \ : \mathcal V \longrightarrow \mathbb{K}^{n, 1} , \quad v = \sum_{i=1}^{\\n} \lambda_{i} b_{i} \longmapsto \Phi(v) := \begin{bmatrix} \lambda_{1} \\ \vdots \\ \lambda_{n} \end{bmatrix} \\
&(3) \quad \mathcal{I}d_{\mathcal V} \ : \mathcal V  \longrightarrow \mathcal V  , \quad \mathcal v \longmapsto \mathcal{I}d_{\mathcal V}(v)  = v
\end{align}$$

<br/>

<br/>

{% include res_gif.html url="/images/lina/commutative.png" text="The dotted arrows are the mappings from the matrix representations. <br> To obtain $$ [\mathcal{I}d_{\mathcal V}]_{B_1, B_2} $$ use the same method from before for f but consider f to be an endomorphism and then let f be the identity map." %}

<br/>

<ins> Hint</ins> : Notice that the matrix representations only map between the coordinates of vectors.

<br/>

<br/>

{% include res_img.html url="/images/separator.png" width="800px" %}

<br/>

<br/>

#### Properties 

<br/>

### Coordinate Mapping

<br/>

1. &emsp; *The coordinate mapping $$ \Phi_{\mathcal{B}} $$ is an isomorphism.* <br>
2. &emsp; $$\Phi_{\mathcal{B}_2}(f(v)) = [f]_{\mathcal{B}_1, \mathcal{B}_2} \ \Phi_{\mathcal{B}_1}(v) ; \quad \forall \ v \in \mathcal{V}$$ <br>
3. &emsp; *A coordinate transformation is defined by $$\Phi_{\mathcal{B}_2} = [\mathcal{I}d_{\mathcal{V}}]_{\mathcal{B}_1, \mathcal{B}_2} \ \circ \ \Phi_{\mathcal{B}_1}$$. This is useful if you consider $$\mathcal{B}_1$$ to be the canonical basis.*

<br/>

<br/>

### Basis Transformation

<br/>

1. &emsp; *The matrix representation of the identity mapping $$ \mathcal{I}d_{\mathcal{V}} $$ is the basis transformation from $$\mathcal{B}_1$$ to $$\mathcal{B}_2$$.* <br>
2. &emsp; *The basis transformation $$ [\mathcal{I}d_{\mathcal{V}}]_{\mathcal{B}_1, \mathcal{B}_2} $$ is an isomorphism.* <br>
3. &emsp; $$ ([\mathcal{I}d_{\mathcal{V}}]_{\mathcal{B}_1, \mathcal{B}_2})^{-1} = [\mathcal{I}d_{\mathcal{V}}]_{\mathcal{B}_2, \mathcal{B}_1} $$

<br/>

<br/>

### Matrix Representation

<br/>

1. &emsp; $$f = \Phi_{\mathcal{B}_2}^{-1} \ [f]_{\mathcal{B}_1, \mathcal{B}_2} \ \Phi_{\mathcal{B}_1} $$
2. &emsp; *For $$f \in \mathcal{L}(\mathcal{V}, \mathcal{W})$$ and $$g \in \mathcal{L}(\mathcal{W}, \mathcal{U})$$ and $$\mathcal{V}, \mathcal{W}, \mathcal{U}$$ being finite dimensional with basis $$\mathcal{B}_1, \mathcal{B}_2, \mathcal{B}_3$$, respectively, $$[g \circ f]_{\mathcal{B}_1, \mathcal{B}_3} = [g]_{\mathcal{B}_2, \mathcal{B}_3}  \  [f]_{\mathcal{B}_1, \mathcal{B}_2}$$.*
3. &emsp; *Let $$ v_1, ..., v_n \in \mathcal{V} $$ be linearly independent and $$dim(\mathcal{W}) = m \in \mathbb{N}$$. Further, let $$ f \in \mathcal{L}(\mathcal{V}, \mathcal{W}) $$. Iff $$\textbf{rank}([f]_{\mathcal{B}_1, \mathcal{B}_2}) = m$$ then $$ (v_1, ..., v_n) [f]_{\mathcal{B}_1, \mathcal{B}_2} = (w_1, ..., w_m) \in \mathcal{W} $$ are linearly independent.*

<br/>

{% include res_img.html url="/images/separator.png" width="800px" %}

<br/>

<br/>

#### Applications 

<br/>

### &emsp; **Diagonal representation**

Let $$ \mathcal{V}(\mathbb{F}) $$ be a finite dimensional vector space and $$ f $$ an endomorphism. If $$ \{\hat{v}_1, ..., \hat{v}_n \} $$ are the eigenvectors of $$ f $$ choose $$ \mathcal{B} =  \{\hat{v}_1, ..., \hat{v}_n \} $$ as the basis.
Then we get as the matrix representation of $$ f $$:

$$ [f]_{\mathcal{B}} = 

\begin{bmatrix}
\lambda_1 & \cdots & 0 \\
\vdots & \ddots & \vdots \\
0 & \cdots & \lambda_n
\end{bmatrix}

$$

where $$ f(\hat{v}_i) = \lambda_i \hat{v}_i $$.

<br>

{% include collapse.html  id="ex2" title="&nbsp; Proof"  collapsed_content="

Some text.

"%}

<br/>

<br/>

### &emsp; **Differential operator representation**

<br/>

Let $$ p = \sum_{k=0}^{n} \alpha_k t^k \in \mathbb{R}[t]_{\leq n} \ \land \ \mathcal{B} = \{ t^k \}_{k=0}^{n} $$ be the canonical basis then the derivative of p(t) is given by:

$$ D(p(t)) = D \Biggl( \sum_{k=0}^{n} \alpha_k t^k \Biggl) = \sum_{k=1}^{n} k \alpha_k t^{k - 1} = \begin{bmatrix} 1 & t & \ldots & t^n \end{bmatrix} \begin{bmatrix} \alpha_{1} \\ 2 \alpha_2 \\ \vdots \\ n \alpha_{n} \\ 0 \end{bmatrix} $$

<br> 

Therefore, the representation matrix of the operator, $$ D $$, has to fulfill the following equation:

$$ [D]_{\mathcal{B}} \begin{bmatrix} \alpha_0 \\ \alpha_1 \\ \vdots \\ \alpha_{n-1} \\ \alpha_n \end{bmatrix} =

\begin{bmatrix} \alpha_{1} \\ 2 \alpha_2 \\ \vdots \\ n \alpha_{n} \\ 0 \end{bmatrix} $$

<br>

Solving that equation we obtain the following form:

$$  [D]_{\mathcal{B}} = 

\begin{bmatrix}
    \begin{array}{c|c}
  0_{n, 1} & M \\
  \hline
  0 & 0_{1, n}
    \end{array}
\end{bmatrix} \\

$$

where $$ M = \textbf{diag}(1, ..., n) \in \mathcal{M}_{n \times n}(\mathbb{R})$$.

<br/>

{% include res_img.html url="/images/separator.png" width="800px" %}

<br/>

<br/>


