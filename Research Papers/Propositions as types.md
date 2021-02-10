## Section 2 Gentzen
-Gentezen introduced *natural deduction* and *sequent calculus* ^1466d3
- proof rules should come in pairs
- 
### sequent calculus
- if A holds then B holds $B \subset A$
- conjuction $A \& B$
- disjunction $A  \lor B$
- false : $\curlywedge$


### natual deduction

^0ee9bd

- introduction rule : how one can prove $B \subset A$ 
- elimination rule : what can be done when $B \subset A$ is proven
-  introduction $\equiv$ defintions and elimination $\equiv$ conclusions

### Subformula principle
From what was said in [[#^0ee9bd | Natural deduction ]] in the proof of a combination formulas, only those formulas and their subformulas could show up.
- formula consistency then appears as proving false
- to find a contradiction one pust find $\curlywedge \subset A$

### why sequent calculus < natural deduction
- every rule except one allows for the subformula principle\
	- the exception, the cut rule can be dealt with by cut elimination **(?? what is this)**
- apperantly Gentzen only used sequent calculus to prove subformula for natural deduction
	- not quite sure why? or what was the goal of natural deduction?

## Section 3 Propositions as types
- Curry found that every type of function (what does he mean "type of function") $A \rightarrow B$ could be read as $B \subset A$
	- type of formula $\leftrightarrow$ proposition
	- this was also drawn to proofs
A connection was drawn between lambda calculus and natural deduction 
Allowed by extending lambda calculus to allow for pairs (? like cartesian products) and disjoint sums (? not super sure what this is, i guess just a way to represent disjoint).
Thus, typing rules could be compared to the natural deduction rules:
- introduction rules $\leftrightarrow$ define a value
- elimantion rules $\leftrightarrow$ how to use or deconstruct values of a given type (not sure what "type" means in this context)

Howard's connections:
- $A \& B \leftrightarrow A \times B$
	- a proof of $A \& B$ means a proof of $A$ and $B$
	- $A \times B$ is the value type of $A$ and $B$
- $A \lor B \leftrightarrow A + B$
	- a proof of $A \lor B$ means a proof of $A$ or $B$
	- $A+B$ either a value of $A$ or $B$ and where it is a left or right summand (? pretty sure this means just indicating what type it is)
- $B \subset A \leftrightarrow A \rightarrow B$
	- a proof of $B \subset A$ means there is a procedure from a proof of $A$ to $B$
	- a value of type $A \rightarrow B$ is a function that with a value of type $A$ gives a value of type $B$

Howads proposes that $\forall$ and $\exists$ correspond to *dependent types* (? what are these)

## 4 Intuitionistic logic
Intuitionists come with assumptions made about infinity and insist upon a *constuctionist* (??) notion of truth.
- a proof of $A \lor B$ must show which of A or B holds
- reject law of the excluded middle, that $A \lor \lnot A$ must hold, since it's unclear which holds

it is provable is equating it to being a true in classical.
Not being unprovable does not equate being provable
false is something being absurd

requiring you to give proofs, the impossibility of a proof does not conclude something to be true

## 5 Other logics
Hilbert's logic was closely related to intuitionists (Heyting's) if included the law of excluded middle.
Intuitionistic logic work with propositions as types since disjunction must be proof of either A or B (and cannot just be A and not A)

"second-order logic corresponds to type abstraction in second-order lambda calculus" - what does that mean?
- it correlates with data abstraction



The design of Java and C# draws on Girard-Reynolds (abstraction second order thingy)[[https://en.wikipedia.org/wiki/System_F]]
The design of Haksell and ML draw on Hindley-Milner (principal types) [[https://en.wikipedia.org/wiki/Hindley%E2%80%93Milner_type_system]]

Classical was connected by (i have no clue what any of these are):
- connecting Pierce's Law as a type for call/cc operator of Scheme
- double-negation translation $\leftrightarrow$ continuation-passing style tranformation 

Modal logic permits "necessarily" or "possibly" true
- what does this do? how?
- apperantly 5 different types
- "monads as a technique to explain the semantics of important features of programming languages such as state, exceptions, and input-output"
	- what the hell are monads?

Temporal logic :
- allows for "hold now" or "will hold at some point" true or false values
- useful for verification of computing systems ( like turing machines?)
- application to functional reactive prog (uhhh...)

Linear logic:
- hypothesis can be used exactly once
- allows for facts to be "overthrown"
- applicable to systems where there are changes (example?)

There is a correspondence between natural deduction and cartesian closed category.

## 6. Natural deduction
$A$ and $B$ stand for arbitrary formulas. Proofs are like trees, each node is an instance of a "proof rule". 
"Proof rule" is a set of formulas written above a line, *premises*, and a single formula below, a *conclusion*.
- when all *permises* hold the *conclusion* follows

A *connective* is a $-I$ or $-E$

Proof rules aim to either introduce or eliminate *connective*
- one introduces a formula for the connective
- one eliminates a forumula for a connective

Introduction rules **define** a connective.
Elimination rules show use how to **use** or **take advantage** of a connective.

#### Conjuction introduction rule $\& - I$:
![[Pasted image 20210126203844.png]]
- if $A$ and $B$ hold then $A \& B$ holds

#### Elimantion rule 1 $\& -E_{1}$:
![[Pasted image 20210126203948.png]]
- if $A \& B$ holds then $A$ holds

####  Elimation rule 2 $\& -E_{2}$:
![[Pasted image 20210126204036.png]]
- if $A \& B$ holds then $B$ holds


#### To show assumption:
![[Pasted image 20210126204449.png]]
- "tether" and bracket A to B
- the $x$ indicates the "name" of the assumption and in order to discharge it must be shown on the introduction rule,e.g., $\supset - I ^{x}$ 


#### Introduction rule for implication $\supset - I$:
![[Pasted image 20210126204134.png]]
- if assuming $A$, $B$ holds then $A \supset B$ and the assumption may be gotten rid of (i think it's just getting acknowledge and can hence be forgotten)

#### Elimination rule for implication $\supset - E$:
![[Pasted image 20210126224553.png]]
- if $A$ and $A \supset B$ hold, then $B$ holds
- called *modus ponens*

### Example proof
$$(B \& A) \supset (A \& B)$$
![[Pasted image 20210126225120.png]]

1. start with assumption $[B \& A]^{z}$
2.  from $[B \& A]^{z}$ by using $\& -E_{2}$ we get $A$
3. from $[B \& A]^{z}$ by using  $\& -E_{1}$ we get $B$
4. using $\& - I$ we get $A \& B$
5. discharge the assumption by using $\supset - I^{z}$  getting $(B \& A) \supset (A \& B)$


### Redux Rules
These are rules that allow you to reduce the amount of rules you have to use to get to something
#### Reduction of $\& - I, \& - E_{1}$
![[Pasted image 20210127171526.png]]

#### Reduction of $\supset - I, \supset - E$
![[Pasted image 20210127171601.png]]

## 7 Lambda calculus
$A,B$ : arbitrary types
$L,M,N$ : arbitrary terms

Product types : $A \times B$
Function types: $A \rightarrow B$

Same shpeel for *premises* and *conclusions*

When all premises hold, then the conclusion follows

#### Introduction rule $\times - I$
![[Pasted image 20210127164050.png]]
- if the M term has type A and N type B, then we may form the pair term $\langle M,N \rangle$  of product type $A \times B$

#### Elimination rule $\times - E_{1}$
![[Pasted image 20210127164102.png]]
- if term L has type $A \times B$ then we can create the term $\pi _{1} L$ of type $A$

#### Elimination rule $\times - E_{2}$
![[Pasted image 20210127164111.png]]
- if term L has type $A \times B$ then we can create the term $\pi _{2} L$ of type $B$

#### Introduction rule $\rightarrow - I$
![[Pasted image 20210127164130.png]]
- if given *variable* $x$ of type $A$ we have formed a term $N$ of type $B$, then we form the term $\lambda x . N$ of function type $A \rightarrow B$
- $x$ is "free" in $N$ and "bound" in $\lambda x . N$
- to show that $x$ can be present an arbitrary amount of times in term $N$ -> $[x:A]$ and "tether" it to $N:B$
- **Closed** - when all variables in a term are bound by a $\lambda$

#### Elimination rule $\rightarrow - E$
![[Pasted image 20210127164547.png]]
- given term L of type $A \rightarrow B$ and term $M$ of type $A$, we create *application* term $LM$ of type $B$

What was "discharging assumption" in natural deduction is now "binding variables" in lambda calculus.

### Example
![[Pasted image 20210127165024.png]]
1. from $z$ we form term $\pi_{2} z$ of $A$ using $\times - E_{2}$
2. from $z$ we form term $\pi_{1} z$ of $B$ using $\times - E_{1}$
3. we make the pair $\lange \pi_{2} z, \pi_{1} z \rangle$ using $\times - I$
4. noting how we have a free variable left we bound it with $\rightarrow - I$ getting $\lambda z . \lange \pi_{2} z, \pi_{1} z \rangle$ of type $(B \times A) \rightarrow (A \times B)$

### Redux rules
![[Pasted image 20210127170318.png]]
- this shows a valid reduction of: $\times - I$ followed by $\times - E_{1}$, to  term $M$ of type $A$
	- this means that when you see those two rules immediatly in said way, you can replace them with just $A$

![[Pasted image 20210127170520.png]]
- a reduction of $\rightarrow - I^{x}$ with $-E$, to $N[M/x]$  of $B$ - each variable $x$ in term $N$ by term $M$

### Example of Redux Rules
![[Pasted image 20210127171634.png]]

### Example of redux rules
![[Pasted image 20210127171335.png]]