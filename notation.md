Här följer en sammanställning av den notation som förekommer i källorna, uppdelad efter ämnesområde:

### **Logik och kvantifikatorer**
*   **$⊤$ och $⊥$**: Sanningsvärden för **sant** respektive **falskt**.
*   **$∧$**: Logiskt **och** (konjunktion).
*   **$∨$**: Logiskt **eller** (disjunktion).
*   **$¬$**: Logisk **negation** (inte).
*   **$⇒$**: Logisk **implikation** (om... så...).
*   **$⇔$**: Logisk **ekvivalens** (om och endast om).
*   **$∀$**: Universell kvantifikator (**för alla**).
*   **$∃$**: Existentiell kvantifikator (**det existerar**).
*   **$P(n)$**: Ett **predikat**, vilket kan ses som en funktion till propositioner.

### **Mängdlära**
*   **$ℕ$**: Mängden av **naturliga tal** $\{0, 1, 2, \dots\}$.
*   **$ℝ$**: Mängden av **reella tal**.
*   **$\in$ och $\notin$**: Betecknar **medlemskap** respektive icke-medlemskap i en mängd.
*   **$\{ \dots \}$**: Notation för att definiera mängder genom att lista element eller via **mängdbyggare** (t.ex. $\{ n \in ℕ \mid n > 2 \}$).
*   **$\subseteq$ och $\nsubseteq$**: Betecknar **delmängdsrelationen** respektive att en mängd inte är en delmängd.
*   **$\emptyset$**: Den **tomma mängden**.
*   **$\cup$**: **Union** (mängden av element som finns i antingen $A$ eller $B$).
*   **$\cap$**: **Snitt** (mängden av element som finns i både $A$ och $B$).
*   **$\setminus$ (eller $-$)**: **Mängddifferens** (element som finns i $A$ men inte i $B$).
*   **$\bar{A}$**: **Komplementet** till $A$ (allt i universumet $U$ som inte finns i $A$).
*   **$\times$**: **Cartesisk produkt**, mängden av alla ordnade par $(x, y)$.
*   **$\wp(S)$ eller $2^S$**: **Potensmängden**, mängden av alla delmängder till $S$.
*   **$Fin(S)$**: Mängden av alla **ändliga delmängder** till $S$.
*   **$⋃_{B \in P} B$**: Unionen av alla mängder som ingår i en samling $P$.

### **Relationer och funktioner**
*   **$R \subseteq A \times B$**: En **binär relation** mellan mängderna $A$ och $B$.
*   **$xRy$**: Notation för att $x$ står i relation till $y$.
*   **$A \to B$**: Mängden av alla **totala funktioner** från $A$ till $B$.
*   **$A \rightharpoonup B$**: Mängden av **partiella funktioner** från $A$ till $B$.
*   **$id$**: **Identitetsfunktionen**, där $id(x) = x$.
*   **$f \circ g$**: **Sammansättning** av funktioner ($f(g(x))$).
*   **$[x]_R$**: **Ekvivalensklassen** för elementet $x$ under relationen $R$.
*   **$A/R$**: **Kvotmängden**, mängden av alla ekvivalensklasser av $A$ under relationen $R$.

### **Strängar, alfabet och språk**
*   **$\Sigma$**: Ett **alfabet**, en ändlig och icke-tom mängd tecken.
*   **$\Sigma^*$**: Mängden av alla **ändliga strängar** över alfabetet $\Sigma$.
*   **$\varepsilon$**: Den **tomma strängen**.
*   **$aw$**: En sträng som börjar med tecknet $a$ följt av strängen $w$.
*   **$|w|$**: **Längden** på strängen $w$.
*   **$\Sigma^+$**: Mängden av alla **icke-tomma strängar** över $\Sigma$.
*   **$\Sigma^n$**: Mängden av strängar med **längden $n$**.
*   **$w^n$**: Strängen $w$ **konkateneryad med sig själv $n$ gånger**.
*   **$L, M, N$**: Beteckningar för **språk** (delmängder av $\Sigma^*$).
*   **$LM$**: **Konkatenering av språk** $\{ uv \mid u \in L, v \in M \}$.
*   **$L^*$**: **Kleenestjärnan**, unionen av språket upphöjt till alla naturliga tal $n$.

### **Finita automater (DFA och NFA)**
*   **$(Q, \Sigma, \delta, q_0, F)$**: En **5-tupel** som definierar en finit automat, där $Q$ är tillstånd, $\Sigma$ alfabet, $\delta$ övergångsfunktion, $q_0$ starttillstånd och $F$ accepterande tillstånd.
*   **$\delta$**: **Övergångsfunktion** för ett enskilt tecken.
*   **$\hat{\delta}$ (eller $\hat{\gamma}$)**: Den utvidgade övergångsfunktionen som hanterar hela **strängar**.
*   **$L(A)$**: Det **språk** som accepteras av automaten $A$.
*   **$A_1 \otimes A_2$**: **Produktkonstruktion** av två DFA:er, vilket motsvarar snittet av deras språk.
*   **$A_1 \oplus A_2$**: **Summa/unions-konstruktion** för DFA:er.
*   **$Acc(q)$**: Mängden av tillstånd som är **nåbara** från tillståndet $q$.

### **Induktion och datatyper**
*   **$suc(n)$**: **Successor-funktionen** (efterföljaren) för naturliga tal.
*   **$nil$ och $cons(x, xs)$**: Grundläggande konstruktorer för **induktivt definierade listor**.
*   **$[ ]$ och $x : xs$**: Alternativ notation för tom lista respektive $cons$.
*   **$Expr ∷= \dots$**: Notation som används för att definiera syntax i **kontextfria grammatiker**.
