---
title: "Discrete Mathematics: Logic and Proofs"
date: 2021-09-05T21:41:32+07:00
draft: true
categories: ['Discrete Math']
tags: [math, knowledge-note]
author: false
summary: "A brief summary of logic and proof"
---

## 1. Propositions

- A **proposition** is a declarative sentence (that is, a sentence that declares a fact) that is *either true or false, but not both*.  

    Examples:  
    - *Toronto is the capital of Canada*  
    -> This is a proposition (and it's false)
    - *1 + 1 = 2*  
    -> This is a proposition (and it's true)
    - *What is the capital of the US?*  
    -> This is not a proposition because it is not declarative
    - *x + 1 = 2*  
    -> This is not a proposition because it is either true or false

- The **truth value** of a proposition $p$: T when $p$ is true, and F when $p$ is false.

- An **atomic proposition** is a proposition that cannot be expressed in terms of simpler propositions.  

    Example: *"David Beckham is an English footballer"* is a proposition, but it's not atomic, since it can be broken down into two simpler atomic propositions: *"David Beckham is English"* and *"David Beckham is a footballer"*

- Let $p$ be a proposition, the **negation** of $p$, denoted by $\neg{p}$ or $\overline{p}$ is the statement *"It is not the case that $p$"*

    Example: The negation of *"I have a Macbook"* is *"It's not the case that I have a Macbook"* or in simpler language *"I do not have a Macbook"*

    The **truth table** of $\neg{p}$:
    | $p$      | $\neg{p}$ |
    | :----:  | :----:  |
    | T     | F     |
    | F   | T      |

- Let $p$ and $q$ be propositions
    - The **conjunction** of $p$ and $q$, denoted by $p \land q$, is the proposition *“$p$ and $q$”*
    - The **disjunction (inclusive or)** of $p$ and $q$, denoted by $p \lor q$, is the proposition *“$p$ or $q$”*. It is true when at least one of $p$ and $q$ is true.
    - The **exlcusive or** of $p$ and $q$, denoted by $p \oplus q$, is the proposition that is true when exactly one of $p$ and $q$ is true.
    - The **conditional statement** $p \rightarrow q$ is the proposition *"if $p$, then $q$."*.
    - The **converse** of $p \rightarrow q$ is $q \rightarrow p$
    - The **inverse** of $p \rightarrow q$ is $\neg{p} \rightarrow \neg{q}$
    - The **contrapositive** of $p \rightarrow q$ is $\neg{q} \rightarrow \neg{p}$
    - The **biconditional statement** $p \leftrightarrow q$ is the proposition “$p$ if and only if $q$”

    The **truth table**:
    | $p$ | $q$ | $p \land q$ | $p \lor q$ | $p \oplus q$ | $p \rightarrow q$ | $q \rightarrow p$ | $\neg{p} \rightarrow \neg{q}$ | $\neg{q} \rightarrow \neg{p}$ | $p \leftrightarrow q$ |
    |:---:|:---:|:-----------:|:----------:|:------------:|:-----------------:|:-----------------:|:-----------------------------:|:-----------------------------:|:---------------------:|
    |  T  |  T  | T           |      T     |       F      |         T         |         T         |               T               |               T               |           T           |
    |  T  |  F  | F           |      T     |       T      |         F         |         T         |               T               |               F               |           F           |
    |  F  |  T  | F           |      T     |       T      |         T         |         F         |               F               |               T               |           F           |
    |  F  |  F  | F           |      F     |       F      |         T         |         T         |               T               |               T               |           T           |

    Comments:  
        - The conditional statement $p \rightarrow q$ and it's contrapositive $\neg{q} \rightarrow \neg{p}$ is **equivalent** because they always have the same truth values  
        - The converse $q \rightarrow p$ and inverse $\neg{p} \rightarrow \neg{q}$ of a conditional statement $p \rightarrow q$ is also **equivalent**

----

## 2. Applications of propositional logic
----

## 3. Propositional equivalences

### Tautology and Contradiction

- **Tautology** is a compound proposition that is always **true**, no matter what the truth values of the propositional variables that occur in it  
    E.g: $p \land \neg{p}$
- **Contradiction** is a compound proposition that is always **false**, no matter what the truth values of the propositional variables that occur in it  
    E.g: $p \lor \neg{p}$
- **Contingency** is a compound proposition that is neither a tautology or a contradiction


### Logical Equivalences

- **De Morgan's Laws**:
$$ \neg{(p \land q)} \equiv \neg{p} \lor \neg{q} $$
$$ \neg{(p \lor q)} \equiv \neg{p} \land \neg{q} $$
