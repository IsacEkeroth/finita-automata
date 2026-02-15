Drawing on the sources, here are the proofs and definitions requested.

### **Proof of $|\Sigma^m| = |\Sigma|^m$**

We prove that for every finite alphabet $\Sigma$, $\forall m \in \mathbb{N}, |\Sigma^m| = |\Sigma|^m$ using **mathematical induction** on $m$.

- **Base Case ($m=0$):**
  By definition, $\Sigma^0 = \{\epsilon\}$. The set $\{\epsilon\}$ contains exactly one element, the empty string, so $|\Sigma^0| = 1$. Mathematically, $|\Sigma|^0 = 1$ for any non-zero size of $\Sigma$. Thus, the property holds for $m=0$.
- **Inductive Step:**
  Assume the **inductive hypothesis (IH)**: $|\Sigma^n| = |\Sigma|^n$ for some $n \in \mathbb{N}$. We must show that $|\Sigma^{n+1}| = |\Sigma|^{n+1}$.
  By definition, $\Sigma^{n+1} = \Sigma \Sigma^n$.
  Using the provided equality $|\Sigma \Sigma^n| = |\Sigma| |\Sigma^n|$, we substitute the IH:
  $|\Sigma^{n+1}| = |\Sigma| \cdot |\Sigma|^n$
  $|\Sigma^{n+1}| = |\Sigma|^{1+n} = |\Sigma|^{n+1}$

By the principle of induction, the statement holds for all $m \in \mathbb{N}$.

---

### **Counterexample for $|MN| = |M||N|$**

The equality $|MN| = |M||N|$ **does not hold** for all languages $M$ and $N$.
The concatenation of languages is defined as $MN = \{uv \mid u \in M, v \in N\}$.
Consider the following counterexample:
Let $M = \{\epsilon, a\}$ and $N = \{a, aa\}$.

- $|M| = 2$ and $|N| = 2$. Therefore, $|M||N| = 4$.
- $MN = \{\epsilon a, \epsilon aa, aa, aaa\} = \{a, aa, aa, aaa\}$.
- Since sets do not contain duplicate elements, $MN = \{a, aa, aaa\}$.
- $|MN| = 3$.
  Because $3 \neq 4$, the proposition $|MN| = |M||N|$ is not generally valid.

---

### **Recursive Functions and Induction on $S$**

#### **1. Definition of $\#a$ and $\#b$**

Using **recursion** on the structure of strings in $\Sigma^*$, we define the functions as follows:

- $\#a(\epsilon) = 0$
- $\#a(aw) = 1 + \#a(w)$
- $\#a(bw) = \#a(w)$
- $\#b(\epsilon) = 0$
- $\#b(aw) = \#b(w)$
- $\#b(bw) = 1 + \#b(w)$

#### **2. Lemma: $\#a(uv) = \#a(u) + \#a(v)$**

We prove this by induction on the structure of $u$:

- **Base Case ($u = \epsilon$):** $\#a(\epsilon v) = \#a(v)$ and $\#a(\epsilon) + \#a(v) = 0 + \#a(v) = \#a(v)$.
- **Inductive Step:** Assume $\#a(wv) = \#a(w) + \#a(v)$ for a string $w$.
  _ If the next character is $a$: $\#a((aw)v) = \#a(a(wv)) = 1 + \#a(wv) = 1 + \#a(w) + \#a(v) = \#a(aw) + \#a(v)$.
  _ If the next character is $b$: $\#a((bw)v) = \#a(b(wv)) = \#a(wv) = \#a(w) + \#a(v) = \#a(bw) + \#a(v)$.
  The lemma holds for all $u, v \in \Sigma^*$. A similar proof applies to $\#b$.

#### **3. Proof of $\forall w \in S, \#a(w) = 2\#b(w)$**

We use **structural induction** based on the inductive definition of $S$.

- **Case $\epsilon \in S$:** $\#a(\epsilon) = 0$ and $2\#b(\epsilon) = 2(0) = 0$. The property holds.
- **Case $auavb \in S$:** Assume $u, v \in S$ and the IH: $\#a(u) = 2\#b(u)$ and $\#a(v) = 2\#b(v)$.
  - $\#a(auavb) = 1 + \#a(u) + 1 + \#a(v) + \#a(b) = 2 + \#a(u) + \#a(v)$ [Lemma].
  - $2\#b(auavb) = 2(\#b(a) + \#b(u) + \#b(a) + \#b(v) + \#b(b)) = 2(0 + \#b(u) + 0 + \#b(v) + 1) = 2\#b(u) + 2\#b(v) + 2$.
  - By IH, $2 + 2\#b(u) + 2\#b(v) = 2\#b(u) + 2\#b(v) + 2$. Holds.
- **Case $buavaw \in S$:** Assume $u, v, w \in S$ and the IH for each.
  - $\#a(buavaw) = \#a(u) + 1 + \#a(v) + 1 + \#a(w) = \#a(u) + \#a(v) + \#a(w) + 2$.
  - $2\#b(buavaw) = 2(1 + \#b(u) + 0 + \#b(v) + 0 + \#b(w)) = 2\#b(u) + 2\#b(v) + 2\#b(w) + 2$.
  - By IH, the property holds.

---

### **Recursive Functions $f, g, h$**

#### **1. Computations**

To compute the values, we apply the recursive definitions and string length $|w|$:

- **Step 1 ($n=1$):**
  - $g(0) = |\epsilon| + g(\epsilon) - h(\epsilon) = 0 + 1 - 0 = 1$
  - $h(0) = |\epsilon| + g(\epsilon) = 0 + 1 = 1$
  - $f(0) = h(\epsilon) + 2g(\epsilon) = 0 + 2(1) = 2$
- **Step 2 ($n=2$):**
  - **$g(00)$** $= |0| + g(0) - h(0) = 1 + 1 - 1 = **1**$
  - **$h(00)$** $= |0| + g(0) = 1 + 1 = **2**$
  - **$f(00)$** $= h(0) + 2g(0) = 1 + 2(1) = **3**$
- **Step 3 ($n=3$):**
  - **$g(000)$** $= |00| + g(00) - h(00) = 2 + 1 - 2 = **1**$
  - **$h(000)$** $= |00| + g(00) = 2 + 1 = **3**$
  - **$f(000)$** $= h(00) + 2g(00) = 2 + 2(1) = **4**$
- **Step 4 ($n=4$):**
  - **$g(0000)$** $= |000| + g(000) - h(000) = 3 + 1 - 3 = **1**$
  - **$h(0000)$** $= |000| + g(000) = 3 + 1 = **4**$
  - **$f(0000)$** $= h(000) + 2g(000) = 3 + 2(1) = **5**$

#### **2. Proof of $f(0^n) = 1 + n$**

First, we prove the **Lemma**: $\forall n \in \mathbb{N}, g(0^n) = 1 \wedge h(0^n) = n$ by induction.

- **Base Case ($n=0$):** $g(0^0) = g(\epsilon) = 1$ and $h(0^0) = h(\epsilon) = 0$. Holds.
- **Inductive Step:** Assume $g(0^k) = 1$ and $h(0^k) = k$.
  _ $g(0^{k+1}) = |0^k| + g(0^k) - h(0^k) = k + 1 - k = 1$.
  _ $h(0^{k+1}) = |0^k| + g(0^k) = k + 1$.
  The lemma is proven for all $n$.

Now we prove the **Main Statement**:
For $n=0$: $f(0^0) = f(\epsilon) = 1$, and $1+0=1$.
For $n = k+1$ (where $n \geq 1$):

- $f(0^{k+1}) = h(0^k) + 2g(0^k)$.
- Using the lemma, $h(0^k) = k$ and $g(0^k) = 1$.
- $f(0^{k+1}) = k + 2(1) = k + 2 = (k+1) + 1 = n + 1$.
  Thus, $\forall n \in \mathbb{N}, f(0^n) = 1 + n$.
