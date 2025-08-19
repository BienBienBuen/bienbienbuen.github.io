---
title: "What exactly are dumplings?"
collection: talks
type: "Talk"
permalink: /talks/1
#venue: "UC San Francisco, Department of Testing"
date: 2025-08-13
#location: "San Francisco, California"
---

This idea originated from my friends during my visiting studies at Oxford, after having too many dumplings from Glucester Green. One would like to rigorously define what a dumpling is. 

## 🥟🥟🥟

Some background motivation for dumplings: They are extremely versatile, simple, and tasty. I believe to most people this is enough to justify any form of thought experiment/waffling about them. Another thing I like is that, when we try to define objects that are not traditionally mathematical, we can often deeping our understanding of the object by doing so, making it a good mental exercise.

Hence, how can we, as mathematicians, begin to define what a dumpling is? Well, the standard practice (in my opinion) is to start by looking at properties of dumplings that we would like to keep (that makes us say "thats something a dumpling will satisfy") but could also be satisfied by other non-dumplings. In short, we want to extract some sufficient but not neccesary properties of dumplings, and use it to define a bigger "class" of dumpling-like objects. Really, that is what math is all about. 

Credit to my friends that came up with the following beautiful description (on a regular night out for kebabs): 

<p style="text-align: center;"><b> "a dumpling of a dumpling is a dumpling." </b></p>

I found this characterisation of dumplings very elegant, because you see, any sort of wrap can be called a dumpling ([a burrito of a burrito is a burrito!](https://youtube.com/shorts/QdwHTTZCVhc?si=7oVDs-a5-gumweE7)) This is a relationship that is neccesary for (real, edible) dumplings (when you make a dumpling filled with numerous smaller dumplings), but not sufficient. So how about we turn this around and make it a definition instead? i.e. make a more rigorous, and even mathematical statement about dumplings. 

The key here is the interpretation of the phrase "dumpling of a dumpling". When we say this, we really mean taking a dumpling dough and fill it with another dumpling. Then, we can think of "of a" as a binary operation, that we shall call **dumplification** $\*$, between some sort of dumpling wrap $w \in \mathcal{W}$ in a wrap space $\mathcal{W}$ and some filling $f \in \mathcal{F}$ in filling space $\mathcal{F}$. For setting the arena for dumplings, we want the filling space $\mathcal{F}$ to be an ambient space that contains everything (including dumplings and non-dumplings). This gives us flexibility to define "flavours" of dumplings via this filling space later on.  

Then, it is quite natural to define the wraps as an operator on the set of fillings $\mathcal{F}$, with $\mathcal{W} \subseteq \text{End}(F)$. This makes sense both semantically, because when we make actual dumplings we take the wrap and physically "operate" on the filling, and mathematically, as operators are quite general and give us a lot of flexibility on the choices of wraps. Then, dumplification is just the evaluation of the wrap operator at the filling: $w \* f = w(f)$. 

Furthermore, we want to be able to unwrap the dumpling and get back the same filling. Imagine making a dumpling with some halal beef filling, and for some diabolical reason you want to eat it without the dough wrap. You carefully peel the wrap off, only to find the internals to be filled with pork and cabbage. Astaghfirullah! You exclaim, baffled by how the wrapping process is non-injective. In formal language, we require every wrap operator to have a left inverse $w^{\-1}$ for some $w^{-1} \in \text{End}(F)$, satisfying $w^{-1}(w(f)) = f$ for all $f \in F$. 

We also want the set of wraps $\mathcal{W}$ to be closed and associative, since any composition of wraps should still give use a valid wrap (imagine layering two dumpling doughs together and press them together to form a thicker wrap). Formally, $w_1 \circ w_2 \in \mathcal{W}$ for all $w_1, w_2 \in \mathcal{W}$, where $\circ$ denotes composition of operators.

Lastly, what sort of structure should we impose on the filling space $\mathcal{F}$? Well, I think we should assume that there is a set of fillings $S$ that themselves are not dumplings, in an axiomatic sense. There is danger of circular reasoning here, because we haven't formally defined what a dumpling is yet, so it isn't rigorous to say that there exist some non-dumpling fillings. What I really should say is, we assume we can always pick a non-empty subset $S \subseteq \mathcal{F}$, and we wish to use this subset to define dumplings, in alignment with the semantic interpretation that in real dumplings, there are raw fillings, like meat, vegetables, etc.. This motivates us to add a further restriction to the wraps, where no wrap operator should map any element of fillings space $\mathcal{F}$ back to $S$. 

With all of these properties, I think we have enough material to assemble a barebone definition of a dumpling system:

## Definition 1 (Dumpling System): 

A *dumpling system* is a tuple
$$
\mathcal D=(\mathcal{F},S,\mathcal{W}, *),
$$
where:
- $\mathcal{F}$ is a general *filling space*,
- $S \subseteq F$ is the set of raw fillings, 
- $\mathcal{W}$ is a set of *wrap operators* $w:F\to F$, that is closed under an associative composition $\circ$, where $w_1 \circ w_2 \in \mathcal{W} \;\; \forall \;\; w_1, w_2 \in \mathcal{W}$, and further satisfying $\forall w \in \mathcal{W}$:
  -  $\text{Im}(w) \cap S=\varnothing$, 
  -  $\exists \; w^{-1} \in \text{End}(F)$, with $w^{-1}(w(f)) = f$ for all $f \in F$
- Dumplification $\*$ defined as $w\*f := w(f)$ for all $w \in W$ and $f \in F$.

Within this dumpling system $\mathcal{D}$, we can define the set of dumplings as the orbit of the raw fillings set $S$ under successive wraping/dumplification:

## Definition 2 (Dumplings): 

Define the semigroup generated by wraps as

$$
\langle \mathcal{W} \rangle := \{ w_1 \circ w_2 \circ \cdots \circ w_k \mid k \ge 1, \; w_i \in \mathcal{W} \}.
$$

For a raw fillings set $S \subseteq \mathcal{F}$, the The set of **dumplings** is defined to be the orbit of $S$ under $\langle \mathcal{W} \rangle$:

$$
\mathrm{Dum}(S, \langle \mathcal{W} \rangle) := \{ w * s \mid s \in S, \; w \in \langle \mathcal{W} \rangle \}.
$$

*Remark: One thing to note that since we already assume $\mathcal{W}$ is closed under composition, it is a bit redundent to define the semigroup $\langle \mathcal{W} \rangle$, which is just $\mathcal{W}$ itself. But I think having this better visualises the succesive wrapping process, and reiterates the essence of "dumpling of a dumpling is a dumpling".*


This defintion is very fundemental and abstract, and sets a good foundation for the rest of the theory. The problem it has is that it is a bit too structureless. We did not impose much limitation to $\mathcal{F}$, which is good in the sense that we can define dumplings in any space, but the downside is losing track of how fillings and dumplings interact. Roughly speaking, we have built individual strands of "dumpling towers" built with wraps. Yes, they are simple and pretty, but what else can we do with it? 

The next natural step is to define an "addition" between elements in the filling space $\mathcal{F}$ (a gentle reminder that this space contains both the raw fillings, dumplings, and non-dumplings). To keep it more structured, we can define a binary operation $\oplus$ on $\mathcal{F}$ that is associative and commutative, allowing us to essentially become a better chef, where we can now add fillings together, add fillings with dumplings, and add dumplings with dumplings to make even tastier dumplings.


## Definition 3 (Mixed Dumpling System): 

For a *dumpling system* $\mathcal D=(\mathcal{F},S,\mathcal{W}, *)$, a mixed dumpling system is defined as 

$$
\mathcal D_{\oplus}=((\mathcal{F}, \oplus),S,\mathcal{W}, *),
$$

where $\oplus$ is a binary operation on $\mathcal{F}$ that is associative and commutative. We define the general filling as the additive closure of the raw fillings set $S$ under $\oplus$:

$$
S_{\oplus} := \langle S \rangle_{\oplus} = \{ s_1 \oplus s_2 \oplus \cdots \oplus s_k \mid k \ge 1, \; s_i \in S \}
$$

Define two sequences for $n \ge 0$:

$$
\begin{align}
M_{0} &:= S_{\oplus}, \quad D_{0} := \{w * u \mid w \in \mathcal{W}, u \in M_{0}\}\\
M_{n+1} &:= \langle M_{n} \cup D_{n} \rangle_{\oplus}, \quad D_{n+1} := \{w * u \mid w \in \mathcal{W}, u \in M_{n+1}\}
\end{align}
$$

The set of **mixed dumplings** is defined as the union of all the layers of $D_{n}$:

$$
\mathrm{Dum}_{\oplus}(S, \langle \mathcal{W} \rangle) := \bigcup_{n=0}^{\infty} D_{n}
$$







*Remark: Essentially, the sequence $M_{n}$ is for mixing of earlier layers of dumplings as fillings, and $D_{n}$ is responsible for wrapping the mixed fillings.*

With all of this theory set up, we basically wrote ourselves a dumpling culinary book. Now its time to start cooking! We can now begin specifying concrete dumpling systems of different "flavour", and I have tried to cook up a few examples below:


## The set dumpling

we define the **filling space:** as the set of all hereditarily finite sets, i.e.

$$
\mathcal{F} = H_{\aleph_0}
$$  

With the raw fillings being the following Neumann ordinals (i.e. construction of numbers via set theory):

$$S = \{\emptyset, \{\emptyset\}, \{\{\emptyset\}\}, \{\{\{\emptyset\}\}\}\} = \{0, 1, 2, 3\}$$  


**Wrap operator:**  
For $x \in \mathcal{F}$, we define a singleton wrap operator set where:

$$
\mathcal{W}=\{w\} \quad w(x) := \{x\}.
$$

**Addition:**  
For $A,B \in \mathcal{F}$, the addition operator is defined as:

$$
A \oplus B := A \cup B.
$$  


This gives us some very nice dumplings:

$$ \{1\}, \{\{1\}\}, \{\{\{1\}\}\}, \dots $$

and also mixed dumpings, for example:

$$ \{\,\{0\}, 1, \{\{2\}, 3\}\,\}$$  

This system is quite neat in the sense that it is very "visualizable": each curly braket $$\{\}$$ is very reminiscent of physical dumpling wraps. 


## The numerical dumpling

We define the **filling space** as the natural numbers:  

$$
\mathcal{F} = \mathbb{N}
$$  

With the raw fillings being:  

$$
S = \{0\}   
$$  

**Wrap operator:**  
We define an infinite family of successor wraps:  

$$
\mathcal{W} = \{ w_i \mid i \in \mathbb{N}_{>0} \}, \quad w_i(n) := n+i
$$  

Note that $\mathcal{W}$ is closed under composition:  

$$
w_i \circ w_j = w_{i+j}
$$  

**Addition:**  
For $m,n \in \mathbb{N}$, the addition operator is defined as the normal addition between numbers:  

$$
m \oplus n := m+n
$$  

In this system, dumplings are just natural numbers, and mixed dumplings are just sums of natural numbers, for example:

$$ w_2(2 \oplus 3) = 7 $$  

In this system, the mixed dumplings doesn't give an extra collection of dumplings. This can be due to starting with a filling system that is too simple, or a wrap operator that is too extensive, where all the additional dumplings are equivalant to wrapping the raw filling successively. One could introduce further complication by reducing the power of wraps, for example, defining $w_i(n) = 2^{i+n}$. 

## The matrix dumpling


We define the **filling space** as the set of finite square matrices over a field $\mathbb{K}$ (e.g. $\mathbb{R}$ or $\mathbb{C}$):  

$$
\mathcal{F} = \bigcup_{n \geq 1} M_n(\mathbb{K}).
$$  

With the raw filling being the seed:  

$$
S = \{ I_1 \}, \quad I_1 = [1] \in M_1(\mathbb{K}).
$$  

**Wrap operator:**  
We restrict the wraps to the actions of invertible $2 \times 2$ matrices, where for each $M \in GL_2(\mathbb{K})$, define the wrap operator  

$$
w_M : M_n(\mathbb{K}) \to M_{2n}(\mathbb{K})
$$  

by  

$$
w_M(A) := M \otimes A
$$  

where $\otimes$ denotes the Kronecker product. Equivalently, we have:

$$
\mathcal{W} = \{M \otimes \cdot \mid M \in GL_2(\mathbb{K})\}
$$

Semantically, we are fitting the filling matrix $A$ into the 4 entries of the wrap $M$. Since we required each $M$ to be invertible, we can always invert the wrap to get back the filling, which in a way perserves the structure of the filling during wrapping.

**Addition:**  
For $A \in M_m(\mathbb{K}), B \in M_n(\mathbb{K})$, the addition operator is defined as the block diagonal sum:  

$$
A \oplus B := 
\begin{bmatrix}
A & 0 \\
0 & B
\end{bmatrix} \in M_{m+n}(\mathbb{K})
$$  

This corresponds to mixing fillings/dumplings side by side without interaction.  

**Examples:**  
A simple wrapped dumpling:  

$$
w_W(I_1) = W \otimes I_1 = W
$$  

Double wrap:  

$$
w_{W_2}(w_{W_1}(I_1)) = W_2 \otimes (W_1 \otimes I_1) = (W_2 \otimes W_1)
$$  

Mixed dumplings:  

$$
(w_{W_1}(I_1)) \oplus (w_{W_2}(I_1)) = 
\begin{bmatrix}
W_1 & 0 \\
0 & W_2
\end{bmatrix}
$$  


## Closing remarks

The dumpling definition in the end was quite neat, but getting here was not easy! We started slowly with setting up what mathematical objects wraps and fillings are, and the properties we expect them to have. 

I think the system is quite rich, and I still have some ideas to explore regarding the dumpling system. For example, one might attempt to pull an algebraic trick of defining the raw filling set as an equivalance class and quotienting out the equivalence relation, with something like:

$$x \sim y \iff x,y \in S$$

$$\mathcal{F}_{\sim} = \mathcal{F} / \!\!\sim \;=\;\{ [x]_\sim \mid x \in \mathcal{F}\}$$

Not sure how this will make our dumplings look like, but again, might come back to this small thought experiment and play around with it when I get jobless again. 





