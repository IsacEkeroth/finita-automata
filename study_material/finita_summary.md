### **1. Mathematical Foundations & Logic**

- **Propositions:** Statements that are either true ($⊤$) or false ($⊥$).
- **Logical Connectives:** And ($∧$), Or ($∨$), Not ($¬$), Implies ($⇒$), If and only if ($⇔$).
- **Truth Tables:** Used to define connectives and check the validity of propositions.
- **Tautology (Validity):** A proposition satisfied for all truth value assignments.
- **Logical Equivalence:** Two propositions $p$ and $q$ are equivalent if $p ⇔ q$ is valid.
- **Predicates:** Functions that return propositions (e.g., $P(n)$).
- **Quantifiers:** Universal (**For all** $∀$) and Existential (**There exists** $∃$).
- **Set Operations:** Membership ($∈, ∉$), Equality ($A=B$), Subsets ($⊆, ⊈$), Empty set ($∅$), Union ($∪$), Intersection ($∩$), Set difference ($\setminus$), Complement ($\bar{A}$), Cartesian product ($A \times B$), Power set ($\wp(S)$ or $2^S$), and Finite subsets ($Fin(S)$).
- **Russell's Paradox:** A contradiction in unrestricted naive set theory involving the set of all sets that do not contain themselves.
- **Binary Relations:** Subsets of $A \times B$. Properties include **Total**, **Functional**, **Reflexive**, **Symmetric**, **Transitive**, and **Antisymmetric**.
- **Functions:** Total functions ($A → B$), Partial functions ($A ⇀ B$), Domain, Codomain, Image, Identity ($id$), and Composition ($f \circ g$).
- **Function Properties:** **Injective** (unique outputs), **Surjective** (reaches every element in codomain), and **Bijective** (both injective and surjective).
- **Pigeonhole Principle:** If $m$ pigeons are in $n$ holes and $m > n$, at least one hole has $>1$ pigeon.
- **Equivalence Relations:** Reflexive, symmetric, and transitive relations.
- **Equivalence Classes:** $[x]_R = \{ y \in A \mid xRy \}$. They **partition** the set.
- **Quotient Set:** $A/R$, the set of all equivalence classes.

### **2. Induction and Recursion**

- **Mathematical Induction:** Proving $P(0)$ and $∀n. P(n) ⇒ P(n+1)$.
- **Complete (Strong) Induction:** Proving $P(n)$ assuming $P(i)$ holds for all $i < n$.
- **Mutual Induction:** Proving properties for multiple functions defined in terms of each other.
- **Structural Induction:** Induction based on the structure of **inductively defined sets** (like $ℕ$, Lists, or Trees).
- **Inductively Defined Sets:** Sets defined by constructors (e.g., $zero \in ℕ$, $suc(n) \in ℕ$).
- **Recursive Functions:** Functions defined by cases on the structure of their input (e.g., _length_, _append_).
- **Primitive Recursion:** Recursive calls allowed only on recursive arguments.

### **3. Regular Languages and Automata**

- **Alphabet ($\Sigma$):** A finite, non-empty set of symbols.
- **String (Word):** A finite list of symbols from an alphabet. **Empty string** is $\varepsilon$.
- **Language:** A set of strings over an alphabet.
- **String/Language Operations:** **Concatenation** ($uv$ or $LM$), **Exponentiation** ($w^n, \Sigma^n, L^n$), **Kleene Star** ($L^*$), and **Kleene Plus** ($L^+$).
- **DFA (Deterministic Finite Automaton):** Defined by $(Q, \Sigma, \delta, q_0, F)$.
- **NFA (Nondeterministic Finite Automaton):** Allows multiple transitions for the same input; transition function $\delta \in Q \times \Sigma → \wp(Q)$.
- **$\varepsilon$-NFA:** Includes **$\varepsilon$-transitions** that the automaton can take "spontaneously".
- **$\varepsilon$-closure:** The set of states reachable via only $\varepsilon$-transitions.
- **Subset Construction:** Algorithm to convert an NFA (or $\varepsilon$-NFA) into a DFA.
- **Exponential Blowup:** A DFA corresponding to an $n$-state NFA may require up to $2^n$ states.
- **Regular Expressions (RE):** **Syntax** (empty $\emptyset$, nil $\varepsilon$, symbols $a$, sequence $e_1e_2$, alternation $e_1+e_2$, star $e^*$) and **Semantics** ($L(e)$).
- **Arden’s Lemma:** The equation $X = AX \cup B$ has the least solution $X = A^*B$.
- **Regular Expression Algebra:** Laws like commutativity of $+$, distributivity, and specific rules like the **Shifting Rule** [$e_1(e_2e_1)^* = (e_1e_2)^*e_1$] and **Denesting Rule** [$(e_1+e_2)^* = (e_1^*e_2)^*e_1^*$].
- **Pumping Lemma for Regular Languages:** Used to prove a language is **not regular**.
- **Closure Properties (Regular):** Closed under union, intersection, complement, concatenation, star, substitution, homomorphism, and inverse homomorphism.
- **DFA Minimization:** Process of merging **equivalent states** and removing **inaccessible states**.
- **Distinguishable States:** States $p, r$ are distinguishable if there exists a word $w$ such that only one of $\hat{\delta}(p, w)$ or $\hat{\delta}(r, w)$ is an accepting state.

### **4. Context-Free Languages (CFLs)**

- **CFG (Context-Free Grammar):** Defined by $(N, \Sigma, P, S)$, where $N$ are **nonterminals**, $\Sigma$ are **terminals**, $P$ are **productions**, and $S$ is the **start symbol**.
- **Derivations:** Sequence of steps ($\Rightarrow$) replacing nonterminals with production bodies. Includes **Leftmost derivations** ($\Rightarrow_{lm}$) and **Rightmost derivations** ($\Rightarrow_{rm}$).
- **Parse Trees:** Visual representation of a derivation; its **yield** is the resulting string.
- **Recursive Inference:** Inductive method to determine if a string is in the language of a grammar.
- **Ambiguity:** A grammar is **ambiguous** if a string has $>1$ parse tree or leftmost derivation.
- **Inherently Ambiguous:** A language for which no unambiguous grammar exists.
- **Grammar Transformations:**
  - **Bin:** Restricts production bodies to length $\le 2$.
  - **Del:** Removes **nullable** nonterminals and $\varepsilon$-productions.
  - **Unit:** Removes unit productions ($A \to B$) using **unit pairs**.
  - **Term:** Ensures terminals only appear in productions of the form $A \to a$.
- **Chomsky Normal Form (CNF):** Productions only of the form $A → BC$ or $A → a$.
- **Pumping Lemma for CFLs:** Used to prove a language is **not context-free**.
- **PDA (Pushdown Automaton):** Finite automaton plus a **stack**. Languages are accepted by **final state** $L(P)$ or **empty stack** $N(P)$.
- **CYK Algorithm:** Dynamic programming algorithm to check if a string $w$ belongs to $L(G)$ for a grammar in CNF.
- **Closure Properties (CFL):** Closed under union, concatenation, star, substitution, homomorphism, and inverse homomorphism. **Not** closed under intersection or complement.
- **Generating Symbols:** Symbols $X$ such that $X \Rightarrow^* w$ for some terminal string $w$.

### **5. Computability and Complexity**

- **Turing Machines (TM):** Finite state machine with an infinite tape and a read/write head. A model of computation.
- **Church-Turing Thesis:** Every "effectively calculable" function is computable by a Turing machine.
- **Recursive Languages:** Languages accepted by TMs that always **halt**.
- **Recursively Enumerable Languages:** Languages accepted by TMs (may loop on strings not in the language).
- **Undecidable Problems:** Problems that cannot be solved by any TM, such as checking if a CFG is ambiguous or if two CFGs are equivalent.
- **The Language Hierarchy:** Finite $\subsetneq$ Regular $\subsetneq$ Context-free $\subsetneq$ Recursive $\subsetneq$ Recursively Enumerable $\subsetneq$ All languages.

### **6. Levels of complexity**

| Language Type              | Machine Required            | Capabilities                                        | Example Language                                    |
| :------------------------- | :-------------------------- | :-------------------------------------------------- | :-------------------------------------------------- |
| **Regular**                | DFA / NFA                   | Recognizes patterns and simple repetitions.         | $L = \{a^n b^m\}$ (Any number of $a$'s then $b$'s)  |
| **Context-Free**           | Pushdown Automata (1 stack) | Handles nested structures and matching pairs.       | $L = \{a^n b^n\}$ (Equal number of $a$'s and $b$'s) |
| **Context-Sensitive**      | Linearly Bounded Automaton  | Matches three or more sets; handles string copying. | $L = \{a^n b^n c^n\}$ (Triple matching)             |
| **Recursively Enumerable** | **Turing Machine**          | Anything physically computable (General logic).     | $L = \{ \text{Any valid computer algorithm} \}$     |

### **7. RE rules**

- **Identity of Union:** $e + \emptyset = \emptyset + e = e$
- **Associativity of Union:** $e_1 + (e_2 + e_3) = (e_1 + e_2) + e_3$
- **Commutativity of Union:** $e_1 + e_2 = e_2 + e_1$
- **Identity of Concatenation:** $e\epsilon = \epsilon e = e$
- **Associativity of Concatenation:** $e_1(e_2 e_3) = (e_1 e_2)e_3$
- **Annihilator (Null Element):** $e\emptyset = \emptyset e = \emptyset$
- **Left Distributivity:** $e_1(e_2 + e_3) = e_1 e_2 + e_1 e_3$
- **Right Distributivity:** $(e_1 + e_2)e_3 = e_1 e_3 + e_2 e_3$
- **Idempotency:** $e + e = e$
- **Kleene Star Definition:** $e^* = \epsilon + ee^*$
- **Empty Set Star:** $\emptyset^* = \epsilon$
- **Redundancy Law:** $e^* e^* = (e^*)^* = e^*$
- **Positive Closure Definition:** $e^+ = ee^* = e^*e$
- **Epsilon Addition:** $(\epsilon + e)^* = e^*$
- **Shifting Rule:** $e_1(e_2 e_1)^* = (e_1 e_2)^* e_1$
- **Denesting Rule:** $(e_1 + e_2)^* = (e_1^* e_2)^* e_1^* = e_1^*(e_2 e_1^*)^*$
