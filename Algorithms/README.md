# Algorithms Powered By Princeton


# Lecture 1: Union-Find

>The implementation of algo is [here](https://github.com/PeterWrighten/Peter_CS/tree/main/Algorithms/week1).

Union Find could be modelized as a dynamic connectivity problem.

**Model Union Find**

- public class Union Find
- union(p, q): connect p and q
- find(p, q): find whether p-q is connected.

**Idea**

- Reflexive: p is connected to p.
- Symmetric: if p-q is connected, also q-p.
- Transmitive: if p-q, q-r, thus p-r.

- connected components.

## Quick Find

Connected node i's ```id[i]``` are all equal.

```java
 public boolean find(int p, int q){
	 return id[p] == id[q];
 }
```

|algo|init|union|find|
|:--:|--:|--:|--:|
|quick find| N  | N  | 1  |



## Quick Union

**Interpreter**

- ```id[i]``` is i's parent.
- root of i is ```id[id[...id[i]...]]```

```union(p,q) => id[root(p)] = root(q);```

## Quick Union+

**Weighten quick union**

It could avoid the worst case.

use ```sz[i]``` in union.

```O() < lgN```

**Paths compression**

use ```id[i] = id[id[i]]``` in ```root()```.

```O() < N + MlgN```<- Proved by Tjan, and I would discuss about it in my blog later.

|algo|init|union|find|
|:--:|--:|--:|--:|
|quick union(worst)| N  | N  | N  |
|quick union+ |  N | N+MlgN  | N+MlgN  |