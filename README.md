# Sat-solver-caml  
A SAT solver written in OCaml!

## What is a SAT Problem?  
The Boolean satisfiability problem (SAT) is a classic decision problem in computer science. Given a propositional logic formula, the goal is to determine whether there exists an assignment of variables (or clauses) that makes the formula true.

In simpler terms, given a system of Boolean equations with *n* variables, the task is to find values for `V₁`, `V₂`, ..., `Vₙ` such that the entire system is satisfied. A SAT solver typically takes one or more formulas expressed in **conjunctive normal form (CNF)** as input.

## How to Run the Algorithm  
1. Start the OCaml REPL by launching `utop`.  
2. Load the file `sat.ml` with the following command:
    ```ocaml
    #use "sat.ml";;
    ```

## Example  

For the following system of constraints:

- `V₁ OR V₂ = TRUE`  
- `V₁ XOR V₃ = V₂`  
- `NOT (V₁ AND (V₂ AND V₃)) = TRUE`

You would input:
```ocaml
# solveur [
    (OR(V(1), V(2)), TRUE);
    (XOR(V(1), V(3)), V(2));
    (NOT(AND(AND(V(1), V(2)), V(3))), TRUE)
];;
```

### Expected Output:  
```ocaml
[
  [(V 2, true); (V 1, true); (V 3, false)];
  [(V 2, false); (V 1, true); (V 3, true)];
  [(V 2, true); (V 1, false); (V 3, true)]
]
```

These are all the valid assignments of variables that satisfy the given Boolean constraints.
