# Graph Embedding and Extensions: A General Framework for Dimensionality Reduction

## Graph Embedding

### Definition

The definition of **Graph Embedding** in this paper is different from original definition.

Let $G = \{X, W\}$ be undirected weighted graph with vertex set $X$ and similarity matrix $W$.

We want to find a low-dimensional representation of the Graph $G​$ which can maintain graph relation.

Hence, we define:

* $y = f(x)​$ which map vertex to $\mathbb{R}^m​$
* A diagonal matrix D. $D_{ii} = \sum_{i \neq j} W_{ij}​$
* $L = D - W$
* $B = I$ or $B = D^p - B^p$ for scalar preserving, where $W^p$ denotes penalty graph.

and a programming target:

$$
y^* = \arg\min_{y^TBy=d} \sum_{i \neq j}|y_i - y_j|^2 W_{ij} = \arg\min_{y^TBy=d} y^TLy
$$

### Dimensionality Reduction

Previous works on dimensionality reduction can be represented as graph embedding framework[Table crop from paper]:

| Algorithm | W&B Definition                                               |
| --------- | ------------------------------------------------------------ |
| PCA       | $W_{ij}=\frac{1}{N}$ , $B=I$                                 |
| LDA       | $W_{ij} = \frac{\delta_{c_i,c_j}}{n_{c_i}}$ , $B=I-\frac{1}{Nee^T}$ |
| LPP       | $W_{ij} = \exp\left\{\frac{-|x_i-x_j|^2}{t}\right\}, \text{if } i\in N_k(j) \text{ or } j\in N_k(i)$ , $B=D$ |

## Marginal Fisher Analysis

![Interclass vs Intraclass](intrainter.png)

### Steps

#### Step1: PCA

#### Step2: Intraclass compatness and interclass separability

* Intraclass: $W_{ij} = 1$ if $(i, j)​$ is nearest neighbor pair in same class
* Interclass: $W^p_{ij} = 1$ if $(i, j)$ is nearest neighbor pair in different class

#### Step3: Marginal Fisher Criterion

$w^* = \arg\min_w \frac{w^TX(D-W)X^Tw}{w^TX(D^p-W^p)X^Tw}$

#### Step4: Resolve PCA

## Result

The result is greater than previous work at face recognition.