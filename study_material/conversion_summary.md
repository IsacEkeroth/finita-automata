### **1. Finite Automata and Regular Expression Conversions**

#### **NFA (or $\epsilon$-NFA) to DFA: The Subset Construction**

This algorithm converts nondeterminism into determinism by tracking the **set of all possible states** the NFA could be in simultaneously.

- **Process:** Create a DFA where each state corresponds to a subset of the NFA's states.
- **Start State:** The DFA start state is the **$\epsilon$-closure** of the NFA's start state.
- **Transitions:** For a set of states $S$ and input $a$, the new transition is the $\epsilon$-closure of all states reachable from any $s \in S$ on input $a$.
- **Accepting States:** Any DFA state (subset) that contains **at least one** NFA accepting state is an accepting state.
- **Optimization:** To avoid an exponential blowup of up to $2^n$ states, construct only the **accessible states** starting from the start state.

#### **Finite Automata to Regular Expression**

There are two primary methods for this conversion:

1.  **State Elimination:** This visual method involves removing non-start and non-accepting states one by one. When a state is removed, the edges passing through it are replaced by **regular expressions** that represent those paths.
2.  **Arden’s Lemma:** This algebraic method converts the automaton into a system of equations. It relies on the rule that an equation $X = AX \cup B$ has the least solution **$X = A^*B$**. By solving these equations for the start state, you derive the final regular expression.

#### **Regular Expression to $\epsilon$-NFA**

This is a **recursive algorithm** that builds the automaton based on the structure of the expression:

- **Basic cases:** Create simple structures for $\emptyset$, $\varepsilon$, and single symbols.
- **Alternation ($e_1 + e_2$):** Create a new start state with $\epsilon$-transitions to the NFAs of $e_1$ and $e_2$, and link their accepting states to a new final state.
- **Sequencing ($e_1 e_2$):** Connect the accepting state of the $e_1$ NFA to the start state of the $e_2$ NFA with an $\epsilon$-transition.
- **Kleene Star ($e^*$):** Add $\epsilon$-transitions to allow bypassing the NFA (for $\varepsilon$) and looping back from the end to the start.

---

### **2. DFA Optimization and Testing**

#### **DFA Minimization**

This process produces the smallest possible DFA for a given language through two steps:

1.  **Remove non-accessible states:** Delete any states that cannot be reached from the start symbol.
2.  **Merge equivalent states:** Identify and combine states that behave identically for all possible future inputs.

#### **State Equivalence: The Matrix Method**

To find equivalent states, use a **table-filling algorithm**:

- Mark all pairs $(p, q)$ as **distinguishable** if one is an accepting state and the other is not.
- Iteratively mark pairs $(p, q)$ as distinguishable if, for some input $a$, the states $(\delta(p, a), \delta(q, a))$ are already marked as distinguishable.
- Any pairs remaining unmarked at the end are **equivalent**.

#### **Equality of Languages**

To test if two DFAs $A_1$ and $A_2$ define the same language, combine them into one automaton (keeping their states distinct) and check if their respective **start states are equivalent** using the matrix method.

---

### **3. Context-Free Grammar (CFG) Transformations**

#### **CFG to Chomsky Normal Form (CNF)**

To convert a grammar into CNF (where productions are only $A \to BC$ or $A \to a$), apply these transformations in order:

1.  **Bin (Binarization):** Replace long productions ($| \alpha | \ge 3$) with a chain of productions using new nonterminals so that each production body has at most two symbols.
2.  **Del ($\varepsilon$-removal):** Identify **nullable** nonterminals (those where $A \Rightarrow^* \varepsilon$). Remove $A \to \varepsilon$ and, for every production containing a nullable nonterminal, add new versions of that production with the nullable symbol both present and absent.
3.  **Unit (Unit production removal):** Identify **unit pairs** $(A, B)$ where $A \Rightarrow^* B$. For every non-unit production $B \to \alpha$, add a new production $A \to \alpha$.
4.  **Term (Terminal removal):** For any production $A \to \alpha$ where $|\alpha| \ge 2$, replace every terminal $a$ with a new nonterminal $X_a$ and add the production $X_a \to a$.

---

### **4. Decision Algorithms for CFGs**

#### **Testing Emptiness: Generating Symbols**

A CFG language is non-empty if the start symbol $S$ is **generating**.

- **Algorithm:** Initialize a set with all terminals. Iteratively add nonterminals $A$ if there is a production $A \to \alpha$ where every symbol in $\alpha$ is already in the set.

#### **Membership: The CYK Algorithm**

For a nonempty string $w$ and a CFG in **Chomsky Normal Form**, membership is decided using dynamic programming:

- Construct a table where $T_{i,j}$ stores all nonterminals that can derive the substring of $w$ from index $i$ to $j$.
- The string is a member if the **start symbol $S$** is in $T_{1,|w|}$.

#### **Testing if $\varepsilon \in L(G)$**

A grammar generates the empty string if the start symbol is **nullable**. This is checked using a step function similar to the generating symbols algorithm, identifying which nonterminals can derive $\varepsilon$ through a chain of productions.
