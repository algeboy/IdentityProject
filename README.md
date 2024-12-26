# The Identity Project

**A proposal for a focussed long term project entailing isomorphism applications research at scale.**

[ToC]

---
## What is Identity

**Definition.** Identity is the study of what makes data equal.  

Identity comes in many forms but here is one you likely use all the time.
> **Identify** the animal in this picutre?
> <center>
> <img src="squirrel.jpeg" width="200" />
> </center>


Your task is to know if the animal you see is equivalent to some reference animal perhaps giving it a name.  Of course there are many squirrels and you will likely not have met this one.  The study of identity says that context clarifies the appropriate level of distinction for comparing data.  In this case we might mean something akin to "species".  To identify the animal is to find how the sample given matches with a class of reference examples---other members of the species.

### Leibniz's Law
Leibniz introduced one path to study the process of identity known as Leibniz' Law.

The first part of this law is to explain how equality is to be used.  
#### Indiscernability of Identicals
\[
    x=y \quad \Rightarrow \quad (\forall P)(P(x)\Leftrightarrow P(y))
\]
You may hear of this as "replacing like with like".  Once $x=y$ we can use $x$ and $y$ interchangeably.  This is the first true obstacle to computation.  Quite often simply discovering that two pieces of data are the same does not take us as far as being able to use them in software the same way.  At minimum having two copies of the same data results in storing **twice as much data**. 

#### Identity of Indiscernables
So how do identify data in the first place?  One answer is to reverse the use of identity.
\[
    x=y \quad \Leftarrow \quad (\forall P)(P(x)\Leftrightarrow P(y))
\]
This introduces the second challenge to computational work on identity.  How are we to test every property or use of data to see that the two never differ?  It is typically an infinite process.

Mathematicians of a classical sort will often claim their reasoning is founded in some form of Set Theory.  In Set Theory there is a single primitive predicate 
\[
    P_x^S :\equiv x\in S
\]
where $x$ and $S$ are variables taken to be sets  Sometimes membership comes in hidden language.  For example the subset predicate is just short hand for membership:
\[
\begin{aligned}
S\subset T & :\equiv (\forall s)(s\in S\Rightarrow s\in T)\\
\end{aligned}
\]
While we can make many complicated sets the only test we can perform is membership.  The result is that we can tame the identity of indiscernables because we have only two predicates to test
\[ 
    P_z(X):\equiv z\in X
    \qquad
    P^X(z):\equiv z\in X
\]
The law thus becomes
\[
\begin{aligned}
    X=Y \quad & \Leftarrow \quad (\forall z)(z\in X\Leftrightarrow z\in Y)
    \wedge (\forall Z)(x\in Z\Leftrightarrow y\in Z)
\end{aligned}
\]
In Set Theory the [Axiom of Extension](https://en.wikipedia.org/wiki/Zermelo%E2%80%93Fraenkel_set_theory#Axiom_of_extensionality) simply chooses the right-hand-side to be true by decree.  In fact most Set Theories go even further and make the second term derivable from the first.
\[
\begin{aligned}
    (\forall z)(z\in X\Leftrightarrow z\in Y)
    & \Rightarrow (\forall Z)(X\in Z\Leftrightarrow Y\in Z)\\
    & \equiv: X=Y.
\end{aligned}
\]
So in conventional Zermelo-Fraenkel Set Theory Identity of Indiscernables is assumed as the only means to identify data.

In computer science the Axiom of Extension is a near impossibility to derive from the computationally accessible data.  A range of increasingly stronger rules have been put in place as constructive remedies.  The first of these was by Per Martin-Lof to make only the reflexive law an axiom:
\[
    x:X \vdash refl(x) : x=_X x
\]
Since this many forms for equality axioms and type formers have been added.

#### Liebniz's Law
Taken together the Liebniz law is a declaration that defines equality strictly as the quality that every property is unchanged by replacing one term with the other.
\[
    x=y \quad \Leftrightarrow \quad (\forall P)(P(x)\Leftrightarrow P(y))
\]



## Isomorphism Problems List
Given a type of data and an equivalence relation
1. [Counting](#1-counting) Describe the number of equivalence classes, as a function of the parameters.
    1. Growth Counting: Estimate the asymptotic growth of the class, e.g. there are $2^{\Theta(n^2\log n)}$ simple graphs of order $n$ and $2^{\Theta((\log n)^3)}$ groups of order at most $n$.
    1. Enumerative Counting: Give enumerator or formula such as generating function, e.g. the number of groups of order exponent $p$ and order $p^{6}$ is [TBD Look it up].
    1. Filtered Counting: Estimate the number of equivalence classes, as a function of the parameters, that satisfy a given condition.
    
2. [Comparing](#2-comparing) Given two instances in a prescribed computational model decide equivalence.
    1. Comparison Complexity: place the problem along side known problems in complexity.
    2. Comparison Computation: realize algorithms to solve equivalence on specific cases.
    3. Comparison Cateforification: develop a unified model of isomorphism testing using categories. 
3. [Creating](#4-creating) Given a property, sample randomly from the equivalence classes of the objects with that property, or provide an enumerator that outputs a stream of such objects.
4. [Classification]() given a single object identify one in a database that is equivalent.

---

<small> Creidt: The Identicals, forging identities since 2001.</small>

