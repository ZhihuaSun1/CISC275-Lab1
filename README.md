# Robinson’s Resolution Theorem Exercises

---

## Problem (a)  
\( \models (\forall v_1)[P(v_1) \lor Q(v_1)] \rightarrow [(\forall v_1)P(v_1) \lor (\exists v_1)Q(v_1)] \)

### Steps:
1. **Negate the conclusion**:  
   \[
   (\forall v_1)(P(v_1) \lor Q(v_1)) \land \lnot (\forall v_1)P(v_1) \land \lnot (\exists v_1)Q(v_1)
   \]

2. **Convert to CNF clauses**:  
   - \(\{P(v_1), Q(v_1)\}\)  
   - \(\{\lnot P(a)\}\) (Skolem constant \(a\) for \(\lnot (\forall v_1)P(v_1)\))  
   - \(\{\lnot Q(v_1)\}\) (from \(\lnot (\exists v_1)Q(v_1)\))

3. **Resolution steps**:  
   - Resolve \(\{P(v_1), Q(v_1)\}\) with \(\{\lnot Q(v_1)\}\):  
     \[
     \{P(v_1)\}
     \]  
   - Substitute \(v_1 = a\) in \(\{P(v_1)\}\):  
     \[
     \{P(a)\}
     \]  
   - Resolve \(\{P(a)\}\) with \(\{\lnot P(a)\}\):  
     \[
     \boxed{\emptyset}
     \]

---

## Problem (b)  
\( \models (\forall v_1)[P(v_1) \rightarrow Q(v_1)] \rightarrow [(\exists v_1 P(v_1) \land (\exists v_1 R(v_1)) \rightarrow (\exists v_1 Q(v_1))] \)

### Steps:
1. **Negate the conclusion**:  
   \[
   (\forall v_1)(\lnot P(v_1) \lor Q(v_1)) \land (\exists v_1 P(v_1)) \land (\exists v_1 R(v_1)) \land \lnot (\exists v_1 Q(v_1))
   \]

2. **Convert to CNF clauses**:  
   - \(\{\lnot P(v_1), Q(v_1)\}\)  
   - \(\{P(a)\}\) (Skolem constant \(a\) for \(\exists v_1 P(v_1)\))  
   - \(\{R(b)\}\) (Skolem constant \(b\) for \(\exists v_1 R(v_1)\))  
   - \(\{\lnot Q(v_1)\}\)  

3. **Resolution steps**:  
   - Resolve \(\{\lnot P(a), Q(a)\}\) with \(\{P(a)\}\):  
     \[
     \{Q(a)\}
     \]  
   - Substitute \(v_1 = a\) in \(\{\lnot Q(v_1)\}\):  
     \[
     \{\lnot Q(a)\}
     \]  
   - Resolve \(\{Q(a)\}\) with \(\{\lnot Q(a)\}\):  
     \[
     \boxed{\emptyset}
     \]

---

## Problem (c)  
\( (\forall v_1)[P(v_1) \rightarrow Q(v_1)], (\forall v_1)[Q(v_1) \rightarrow (\exists v_2)R(v_2, v_1)] \models (\forall v_1)[P(v_1) \rightarrow (\exists v_2)R(v_2, v_1)] \)

### Steps:
1. **Negate the conclusion**:  
   - \(\{P(a)\}\) (for \(\lnot (\forall v_1)[P(v_1) \rightarrow (\exists v_2)R(v_2, v_1)]\))  
   - \(\{\lnot R(v_2, a)\}\)  

2. **Convert premises to CNF clauses**:  
   - \(\{\lnot P(v_1), Q(v_1)\}\)  
   - \(\{\lnot Q(v_1), R(f(v_1), v_1)\}\) (Skolem function \(f(v_1)\) for \(\exists v_2\))  

3. **Resolution steps**:  
   - Resolve \(\{P(a)\}\) with \(\{\lnot P(v_1), Q(v_1)\}\) (\(v_1 = a\)):  
     \[
     \{Q(a)\}
     \]  
   - Resolve \(\{Q(a)\}\) with \(\{\lnot Q(v_1), R(f(v_1), v_1)\}\) (\(v_1 = a\)):  
     \[
     \{R(f(a), a)\}
     \]  
   - Substitute \(v_2 = f(a)\) in \(\{\lnot R(v_2, a)\}\):  
     \[
     \{\lnot R(f(a), a)\}
     \]  
   - Resolve \(\{R(f(a), a)\}\) with \(\{\lnot R(f(a), a)\}\):  
     \[
     \boxed{\emptyset}
     \]
