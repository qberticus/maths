# **Numbers and Math**s

---

— Quod gratis asseritur, gratis negatur —

---
### Author
Richard P. Schuler, Ph.D.

#### LLM/ML Disclosure
LLM/ML was used during the creation of this document. 

---

---

# Abstract ^abstract

Modern mathematics and theoretical physics are built across an archipelago of seemingly separate foundations: Peano's axioms for whole-number counting, Dedekind cuts for the smooth real continuum, Shannon's axioms for information and entropy, Hensel's completions for $p$-adic arithmetic, and complex harmonic analysis for the Riemann zeta function. Because each discipline begins with its own pre-packaged primitives—numbers, infinite sets, continuity, or probability—the profound structural equivalences linking them often appear as isolated miracles rather than necessary consequences of a single underlying reality.

This treatise demonstrates that those separate foundations are neither independent inventions nor irreducible starting assumptions. Instead, it constructs a unified, strictly feed-forward deductive chain beginning at the minimal discrete substrate imaginable: an alphabet containing a single indistinguishable tally mark, $\Sigma = \{\Xi\}$. By examining what happens when this single mark is repeated, bundled, stripped in energy-reducing steps, partitioned across prime-sized modular clocks, refined to infinite resolution, and analyzed through wave duality, the treatise proves that classical arithmetic, Shannon channel orthogonality, carry-free digital hardware, Cantor fractal topology, Fisher information geometry, the transcendental constants $\pi$ and $e$, Pontryagin self-dual adeles, and Weil's spectral positivity criterion for the Riemann Hypothesis all emerge inevitably from one combinatorial root.

Through this constructive lens, familiar concepts reveal deeper cross-disciplinary identities: addition is linear concatenation and multiplication is uniform token substitution; pairwise coprimality of prime moduli is mathematically identical to zero Shannon mutual information ($I(X_{i}; X_{j}) = 0$); $\pi$ and $e$ govern the transverse two-dimensional non-collision geometry and longitudinal one-dimensional bit density of prime packing; and the functional symmetry of the Riemann zeta function is the Fourier self-duality of a scale-conserved arithmetic phase space.

Designed for readers across computer science, information theory, theoretical physics, and pure mathematics, the treatise pairs step-by-step formal proofs with intuitive roadmaps, concrete numerical traces, and a cross-disciplinary Rosetta Stone—offering a complete, self-contained path from a single tally mark to the frontier of spectral number theory. This work is neither a textbook restatement of known results nor a philosophical survey detached from proof. Every definition, lemma, and theorem is derived constructively from below without smuggling external numbers or analytic constants into upstream steps, while every classical landmark is re-contextualized within this collective work.


---

# Introduction ^introduction

## I. What This Treatise Is: Draining the Ocean Between Mathematical Islands ^intro-1

When you learn (sometimes forced) mathematics, computer science, and physics through standard textbooks, you encounter them as an archipelago of separate islands. On one island sits elementary arithmetic, where numbers and their rules of addition and multiplication are handed to you as self-evident facts. Across a stretch of water sits probability and information theory, where randomness, entropy, and communication channels are introduced through axioms about uncertainty. Further out lie calculus and geometry, built on smooth curves, limits, and the circles and exponentials that define $\pi$ and $e$. Still further lie abstract algebra, fractal topology, $p$-adic numbers, and the deep analytic theory of prime numbers and the Riemann zeta function.

Because each island is taught using its own starting assumptions, bridges between them feel surprising—almost mysterious. Why should prime numbers, which belong to discrete whole-number counting, obey statistical laws governed by $\pi$, a constant born from the geometry of smooth circles? Why should factoring an integer into prime remainders behave identically to splitting a radio signal into interference-free frequency channels? Why should the distribution of primes be encoded in the zeros of a complex wave transform?

**This document is an effort to drain the ocean between those islands and reveal the single continuous continental shelf underneath them.**

To appreciate what this treatise is, it helps to distinguish it from three familiar genres of mathematical writing:

1. **It is not a textbook restatement.** A restatement takes an established subject—such as elementary number theory or Fourier analysis—and rewrites its theorems using slightly different symbols while relying on the same underlying assumptions. Here, we refuse to assume *any* pre-existing numbers, sets of infinite objects, continuous lines, or probability measures at the start. Every single one of those structures must be earned from scratch.
2. **It is not an informal metaphor.** While every section includes intuitive explanations and concrete worked examples, nothing is left to hand-waving. Every claim is proved step by step in an unbroken chain of logical deductions, starting from a single symbol $\Xi$ and advancing strictly forward without circularity.
3. **It is not a compartmentalized encyclopedia.** Standard reference works treat logic, algebra, information theory, topology, and complex analysis as separate compartments. Here, each domain emerges *because* the preceding domain hits a concrete computational or representational limit that can only be solved by building the next layer.

When you strip away every borrowed assumption, you are left with the simplest possible distinction: the ability to make a single, indivisible mark ($\Xi$) and to repeat it. Everything else in this treatise grows deterministically out of that single seed.

---

## II. How We Build Without Borrowing: The Construction Methods Explained ^intro-2

If you have never read a constructive foundations treatise before, the most unfamiliar aspect of this document is not its conclusions—many of which you will recognize—but **how it builds mathematical objects without assuming they already exist**. In everyday mathematics, if we want a negative number or a fraction or a limit, we simply write $-3$, $2/3$, or $\pi$ and rely on rules learned in school. In a first-principles construction, writing $-3$ before defining subtraction is cheating: it imports the very structure we are trying to explain.

To make every step completely transparent, the treatise relies on **five core construction methods**. Understanding these five tools in plain language before reading Section 1 will allow you to follow every derivation effortlessly.

### II.a Initial Algebras and Structural Induction (Building From One Mark) ^intro-2-1

How do you define "all whole numbers" if you are not allowed to use the words *number*, *count*, or *infinity* yet? You specify a **tiny factory** with two rules:

* **Rule 1 (The Empty Starting State):** You may start with a blank slate, written $\varepsilon$.
* **Rule 2 (The Single-Step Action):** Whenever you have built a valid object $w$, you may append one indivisible mark $\Xi$ to produce a new object $S(w) \coloneq \text{cons}(w, \Xi)$.

In computer science and logic, the collection $\Sigma^*$ of everything this factory can produce is called an **initial algebra**. "Initial" means the factory obeys two common-sense guarantees: **no junk** (nothing exists in $\Sigma^*$ except what can be built by starting at $\varepsilon$ and applying $S$ a finite number of times) and **no confusion** (appending a mark never loops back to the blank slate $\varepsilon$, and two build histories produce the exact same object only if they were identical at every step).

Because every object in $\Sigma^*$ is built step by step by this factory, we can prove universal laws using **structural induction**: if a property holds for the blank slate $\varepsilon$, and whenever it holds for $w$ it also holds for $S(w)$, then it must hold for *every* object in $\Sigma^*$—like an infinite row of dominoes where knocking over the first domino guarantees every subsequent domino falls.

### II.b Endomorphic Substitution and Term Rewriting (Computation as Physics) ^intro-2-2

Once we have strings of tally marks, how do we multiply or divide without appealing to external arithmetic tables? We use **string transformations**:

* **Substitution (`flatMap`):** To multiply two tally strings $u$ and $v$, we walk through $u$ and replace every single mark $\Xi$ with a full copy of $v$, gluing the copies end-to-end. Because this operation maps strings inside $\Sigma^*$ back into $\Sigma^*$, mathematicians call it an **endomorphism**.
* **Terminating Term Rewriting ($\to_{B}$):** To divide a dividend string $w$ by a non-empty divisor string $B$, we set up a mechanical rewrite rule: whenever $w$ contains a copy of $B$ at its end, strip $B$ away and add one tally mark $\Xi$ to a quotient counter $q$, written $(w \cdot B, q) \to_{B} (w, q \cdot \Xi)$. How do we know this machine never runs forever? We assign each state an "energy" $\mu(w, q) \coloneq \text{len}(w)$ equal to the remaining length of $w$. Because $B$ has at least one mark, every step strictly lowers the energy by at least $1$, and since length cannot drop below $0$, the machine is *guaranteed* to halt at a unique remainder $r$ shorter than $B$.

### II.c Quotient Equivalence and Localization (Inventing Negatives and Fractions Safely) ^intro-2-3

Tally strings can grow longer, and we can strip smaller bundles from larger ones, but you cannot physically construct and have "minus three tally marks", much like how you cannot have "negative mass" to create a wormhole.  Then, how do mathematicians create negative integers ($\mathbb{Z}$) and fractions ($\mathbb{Q}$) purely out of positive tally strings? They use **pairs and equivalence classes**:

* **Grothendieck Group Completion (Building $\mathbb{Z}$):** Represent an integer as a pair of tally strings $(u, v)$, interpreted as "credits $u$ minus debits $v$." Different pairs can represent the same net balance: $(5 \text{ marks}, 2 \text{ marks})$ has the exact same net value as $(4 \text{ marks}, 1 \text{ mark})$ (but different potential construction or casual history); because $5 + 1 = 4 + 2$ (an equation that uses *only* addition, never subtraction!). By grouping all pairs that share the same cross-sum into a single bundle (an **equivalence class**), negative numbers emerge cleanly as pairs where $v$ is longer than $u$.
* **Localization (Building $\mathbb{Q}$):** Once $\mathbb{Z}$ is built, we repeat the exact same trick for division. A fraction is an ordered pair $(a, b)$ with $b \neq 0$, interpreted as $a / b$, where $(a_{1}, b_{1})$ and $(a_{2}, b_{2})$ represent the same fraction whenever $a_{1} \times b_{2} = a_{2} \times b_{1}$. Again, division is defined purely in terms of multiplication.

### II.d Metric Completions and Projective Limits (Capturing Infinity Without Guessing) ^intro-2-4

To move from discrete fractions to continuous geometry and infinite prime systems, the treatise uses two complementary ways of taking limits:

* **Metric Completion (Filling in the Gaps):** On the rational numbers $\mathbb{Q}$, sequences like $1, 1.4, 1.41, 1.414, \dots$ get closer and closer together without landing on a rational number. By declaring that every such "shrinking-step" sequence (a **Cauchy sequence**) defines a point, we fill in all the missing gaps to obtain the smooth real line $\mathbb{R}$. Remarkably, if we measure "closeness" not by ordinary distance, but by *how high a power of a prime $p$ divides the difference between two numbers*, the exact same gap-filling procedure produces the **$p$-adic numbers** $\mathbb{Q}_{p}$.
* **Projective / Inverse Limits ($\varprojlim$):** Instead of filling gaps on a line, imagine an infinite tower of modular clocks: a $2$-hour clock, a $11$-hour clock, a $31$-hour clock, and so on, where each larger clock wraps evenly around the smaller ones. A **coherent thread** is an infinite sequence of clock readings $(r_{1}, r_{2}, r_{3}, \dots)$ that never contradict one another when you project a larger clock down onto a smaller one. The collection of all such coherent threads is called the **projective limit** ($R_{\infty}$ or $\mathbb{Z}_{p}$). It captures infinite precision without ever needing an "infinitely large integer."


---

## III. Four Everyday Intuitions that Help ^intro-3

Even when the notation grows dense in later chapters, every single equation in this treatise is a precise formalization of four physical and cognitive experiences you already understand intuitively.

### III.a Tallying, Bundling, and Stripping (The Physical Birth of Arithmetic) ^intro-3-1

Imagine you are keeping track of objects using scratches on a wooden stick: one scratch ($\Xi$), another scratch, and another. You have no names like "seven" or "three"—only the scratches themselves.

If you lay a stick of two scratches end-to-end with a stick of three scratches, you get a combined stick of five scratches. Notice that it does not matter whether you place the two-scratch stick on the left or the right: the physical collection of scratches is identical. That physical invariance is **commutativity of addition**. Now imagine taking a bundle of three scratches and replacing *each* scratch on a two-scratch stick with a copy of that three-scratch bundle: you get two bundles of three, or six scratches. If instead you had replaced each scratch on a three-scratch stick with a bundle of two scratches, you would get three bundles of two—the exact same six scratches arranged in a $2 \times 3$ rectangle rotated by ninety degrees. That symmetry is **commutativity of multiplication**.

In Section 1, we show that this physical tally-and-bundle mechanics is not merely an illustration of arithmetic—it *is* arithmetic, completely and rigorously.

### III.b Modular Clocks and Zero-Crosstalk Radio Channels (Why Primes Are Independent) ^intro-3-2

Everyone knows how a clock wraps around: $14$ hours after midnight is $2$ o'clock on a $12$-hour clock. In mathematics, this wrap-around arithmetic is called **modular arithmetic**.

Now imagine replacing a single $6$-hour clock with two smaller clocks running side by side: a **$2$-hour clock** (which only tells you whether a number is even or odd, $0$ or $1$) and a **$3$-hour clock** (which tells you the remainder after dividing by $3$, namely $0, 1$, or $2$). Let us watch what happens as we count from $0$ to $5$:

* $0$ reads $(0, 0)$ on the $(2\text{-clock}, 3\text{-clock})$.
* $1$ reads $(1, 1)$.
* $2$ reads $(0, 2)$.
* $3$ reads $(1, 0)$.
* $4$ reads $(0, 1)$.
* $5$ reads $(1, 2)$.

Every single hour from $0$ to $5$ produces a **unique pair of clock readings**; Why? Because $2$ and $3$ are **prime** to each other (they share no common factors). Suppose Alice secretly picks one of the six numbers $\{0, 1, 2, 3, 4, 5\}$ at random and tells Betty *only* the $2$-clock reading—say, "the number is even" ($0$ on the $2$-clock). The remaining candidates are $\{0, 2, 4\}$, whose readings on the $3$-clock are $0$, $2$, and $1$ are still equally likely; knowing the $2$-clock gives Betty **zero information** about the $3$-clock (this is the basis for encryption).

In Section 2, we prove that when you scale this up to *all* prime numbers ($2, 3, 5, 7, 11, \dots$), prime factorization transforms whole-number arithmetic into a **parallel communication network** where every prime modulus acts as an orthogonal, zero-crosstalk information channel ($I(X_{i}; X_{j}) = 0$).

### III.c Infinite Zoom, Fractals, and Information Curvature (From Pixels to Geometry) ^intro-3-3

Think about zooming into a digital map or measuring a coastline. At coarse zoom, an entire neighborhood collapses into a single square pixel; as you zoom in, that pixel subdivides into smaller pixels, which subdivide into even finer pixels without end.

Using a single prime clock ($p_{1} = 2$) divides the universe into $2$ coarse regions. Adding the second prime clock ($p_{2} = 3$) splits each region into $3$ sub-regions, giving $2 \times 3 = 6$ pixels. Adding $p_{3} = 5$ gives $30$ pixels; adding $p_{4} = 7$ gives $210$ pixels. When you zoom in across *all* primes simultaneously ($k \to \infty$), each pixel shrinks to a single point in a totally disconnected fractal dust—the **Cantor space**—that nevertheless has the exact same total probability volume as the continuous unit interval $[0, 1]$.

At every zoom level $k$, three fundamental quantities describe a single pixel $B_{k}$:
1. **Its geometric size (Haar measure):** $\mu(B_{k}) = 1 / N_{k}$.
2. **Your uncertainty about where a point lies inside it (Shannon entropy):** $H_{k} = \log_{2} N_{k}$ bits.
3. **Your resolving power to distinguish neighboring states (Fisher curvature):** $g^{(k)} = N_{k}^{2}$.

In Section 4, we prove that these three quantities are locked together by the exact identity $\mu(B_{k}) = 2^{-H_{k}} = (g^{(k)})^{-1/2}$, uniting geometry, information theory, and statistical curvature into a single formula.

### III.d Scale Conservation and Wave Prisms (How Local Rulers Fuse Into the Adele Universe) ^intro-3-4

In physics, a conservation law states that a system cannot change a conserved quantity in one place without creating an equal and opposite change somewhere else. Something remarkably similar happens with fractions when you measure them using *all* prime clocks alongside the ordinary number line.

Take the fraction $q = 5/6$. On the ordinary real number line, its size is $\lvert 5/6 \rvert_{\infty} = 5/6$. Now measure $q$ using prime clocks:
* On the **$2$-adic ruler** (which measures powers of $2$ in the denominator), $5/6 = \frac{5}{2 \cdot 3}$ has a single factor of $2$ downstairs, so its $2$-adic size is $\lvert 5/6 \rvert_{2} = 2^{1} = 2$.
* On the **$3$-adic ruler**, $5/6$ has a single factor of $3$ downstairs, so its $3$-adic size is $\lvert 5/6 \rvert_{3} = 3^{1} = 3$.
* On the **$5$-adic ruler**, $5/6$ has a single factor of $5$ *upstairs*, so its $5$-adic size is $\lvert 5/6 \rvert_{5} = 5^{-1} = 1/5$.
* On every other prime ruler ($p = 7, 11, 13, \dots$), $5/6$ has no factors of $p$ upstairs or downstairs, so its size is $1$.

Multiply all of these sizes together across every ruler in the universe:

$$
\left(\frac{5}{6}\right) \times 2 \times 3 \times \left(\frac{1}{5}\right) \times 1 \times 1 \times \cdots = 1
$$

Every single factor cancels out to $1$! This is **Artin's Product Formula**: when you fuse the real line $\mathbb{R}$ and all $p$-adic fields $\mathbb{Q}_{p}$ into a single master arena—the **restricted adele ring** $\mathbb{A}_{\mathbb{Q}}$—every non-zero rational number obeys a global conservation law of scale. Within this conserved universe, $\pi$ and $e$ emerge from prime statistics, and applying **Fourier wave analysis** (the mathematical prism that decomposes signals into pure frequencies) reveals that the symmetry of the Riemann zeta function is the self-duality of a single Gaussian wave.

---

## IV. The Six-Stratum Engine: How Each Bottleneck Forces the Next Discovery ^intro-4

Rather than reading this treatise as a static list of theorems, follow it as a **six-stage engineering story** in which each stage solves a concrete crisis created by the stage before it:

1. **Stratum 1 — From Single Marks to the Number Tower (Section 1):**
   * *What is built:* Starting from $\Sigma = \{\Xi\}$, we prove addition and multiplication laws directly on tally strings, derive Peano arithmetic ($\mathbb{N}$), construct terminating prefix-stripping division ($\to_{B}$), and build $\mathbb{Z}$, $\mathbb{Q}$, and $\mathbb{R}$.
   * *The Bottleneck:* Representing the number $N$ as a unary string requires $N$ physical tokens ($O(N)$ memory) and sequential carry propagation across every mark.
2. **Stratum 2 — From Linear Tallies to Orthogonal Prime Channels (Section 2):**
   * *What is built:* The definition of divisibility via string substitution, prove Euclid's infinitude of prime words and unique prime word factorization, and prove the Chinese Remainder Theorem ring isomorphism $\Psi_{k}$ alongside zero Shannon mutual information ($I(X_{i}; X_{j}) = 0$).
   * *The Bottleneck:* Arithmetic modulo a primorial $N_{k} = p_{1} \cdots p_{k}$ wraps around to zero whenever a calculation exceeds $N_{k}$, and tally strings cannot yet represent negative exponents.
3. **Stratum 3 — From Wrapping Clocks to Bounded-Carry Automata (Section 3):**
   * *What is built:* Paring parallel prime-clock remainders with an unbounded quotient scale in mixed-radix tuples $\mathcal{Z}_{k} = \mathbb{Z} \times \{0, \dots, N_{k} - 1\}$ (proving that every addition carry lies strictly in $\{0, 1\}$ and every subtraction borrow lies in $\{0, -1\}$), construct signed floating-point Tri-Strings $\mathcal{F}_{\mathbb{Z}}$, and build the deterministic Chiral Prime Parity Finite-State Transducer $\mathcal{M}$ over $(\mathbb{Z}/6\mathbb{Z})^\times$.
   * *The Bottleneck:* Any fixed primorial stage $k$ truncates resolution at finite depth $N_{k}$.
4. **Stratum 4 — From Finite Precision to Profinite Continua (Section 4):**
   * *What is built:* Taking the projective limit $R_{\infty} \coloneq \varprojlim_{k} (\mathbb{Z}/N_{k}\mathbb{Z})$, we prove that $R_{\infty}$ is topologically a Cantor space ($\mathbf{2}^{\mathbb{N}}$) and measure-theoretically isomorphic to $([0, 1], \lambda)$, establish ultrametric tree geodesics, define non-Archimedean van der Put derivatives and Haar integrals, and prove the tripartite equivalence linking Haar measure, Shannon entropy, and Fisher curvature.
   * *The Bottleneck:* Because $R_{\infty}$ is built from square-free moduli $N_{k}$, it tracks divisibility by $p$ but discards higher prime powers $p^{2}, p^{3}, \dots$ required for full rational arithmetic.
5. **Stratum 5 — From Square-Free Limits to Conserved Adelic Space (Section 5):**
   * *What is built:* A derivation of $\pi$ from two-dimensional prime-pair non-collision density and $e$ from one-dimensional primorial entropy density, construct vertical prime-power towers ($\mathbb{Z}_{p}$ and $\mathbb{Q}_{p}$), resolve the exact relationship between $R_{\infty}$ and $\widehat{\mathbb{Z}}$, and assemble the restricted adele ring $\mathbb{A}_{\mathbb{Q}}$, proving Artin's product formula ($\prod_{v \le \infty} \lvert q \rvert_{v} = 1$) and Pontryagin self-duality ($\mathbb{Q}^\perp = \Delta(\mathbb{Q})$).
   * *The Bottleneck:* We now possess a locally compact, scale-conserved, self-dual arithmetic universe—inviting harmonic analysis to uncover its global spectral invariants.
6. **Stratum 6 — From Adelic Wave Duality to Zeta Symmetry and Positivity (Section 6):**
   * *What is built:* Applying adelic Fourier analysis and Poisson summation to the Gaussian-ball product kernel $f(x) = e^{-\pi x_{\infty}^{2}} \prod_{p} \mathbf{1}_{\mathbb{Z}_{p}}(x_{p})$, we prove Fourier self-duality ($\widehat{f} = f$), factorize the global idele zeta integral into $\Lambda(s) = \pi^{-s/2}\Gamma(s/2)\zeta(s)$, prove Tate's functional equation $\Lambda(1 - s) = \Lambda(s)$, derive the Weil-Guinand explicit formula balancing prime powers against zeta zeros, and establish the bidirectional equivalence between Weil positivity ($W(g_{0} * g_{0}^*) \ge 0$) and the Riemann Hypothesis ($\operatorname{Re}(\rho) = \frac{1}{2}$).

---

## V. How This Treatise Relates to Existing Mathematics, Physics, and Computation ^intro-5

Every major theorem contained within corresponds to a pillar of modern science, yet the **order of derivation** transforms how those pillars relate to one another:

| Domain | Classical Textbook Approach (Top-Down) | This Treatise's Constructive Approach (Bottom-Up) |
| :--- | :--- | :--- |
| **Foundations & Arithmetic** | Assumes set theory and Peano's axioms; proves Euclidean division using pre-existing order and subtraction. | Proves commutative semiring laws directly on unary words $\Sigma^*$; derives Peano's axioms and terminating rewrite division ($\to_{B}$) intrinsically. |
| **Algebra & Number Theory** | Proves the Chinese Remainder Theorem as an existence theorem for simultaneous congruences. | Derives CRT as a ring isomorphism $\Psi_{k}$ that decomposes linear tally length into parallel, carry-free prime coordinates. |
| **Information Theory & Statistics** | Axiomatizes Shannon entropy $H$ and mutual information $I(X; Y)$ separately from number theory. | Proves $I(X_{i}; X_{j}) = 0$ directly from prime coprimality, showing statistical independence and coprimality are identical. |
| **Topology & Measure Theory** | Constructs the Cantor set via middle-thirds removal and Lebesgue measure via outer measure on $\mathbb{R}$. | Obtains Cantor topology ($\mathbf{2}^{\mathbb{N}}$) and Rohlin Lebesgue equivalence ($[0, 1]$) automatically as the projective limit of prime clocks ($R_{\infty}$). |
| **Analysis & Transcendentals** | Defines $\pi$ via Euclidean circles and $e$ via differential equations or compound interest limits. | Extracts $\pi$ from 2D prime-pair non-collision density and $e$ from 1D primorial Shannon entropy density per unit prime length. |
| **Harmonic & Spectral Theory** | Proves Riemann's functional equation via theta-function contour integrals and states Weil positivity separately. | Unifies $\mathbb{R}$ and all $\mathbb{Q}_{p}$ into self-dual $\mathbb{A}_{\mathbb{Q}}$, deriving $\Lambda(1 - s) = \Lambda(s)$ and Weil positivity from one self-dual kernel $\widehat{f} = f$. |

---

## VI. Three Disciplinary Reading Pathways ^intro-6

Because the same underlying substrate supports computation, physical measurement, and pure algebraic structure, this document can be read through multiple disciplinary lens:

* **Pathway A — Computer Science, Software Engineering & Automata Theory:**
  * Follow how a minimal unary data structure (`cons` over $\Sigma = \{\Xi\}$) evolves into a monadic substitution engine (`flatMap` in Section 1.2) and a strongly normalizing term-rewriting divider (Section 1.4).
  * In Sections 2 and 3, watch these constructs become a **carry-free Residue Number System (RNS)** arithmetic logic unit ($\mathcal{Z}_{k}$), a signed-exponent floating-point representation ($\mathcal{F}_{\mathbb{Z}}$), and a deterministic **finite-state transducer** ($\mathcal{M}$) that filters composite multiples of $3$ in prime gap sequences.
  * In Section 4, see how the projective limit $R_{\infty}$ forms the infinite path boundary of a **prefix trie** ($\mathcal{T}$) whose address resolution obeys exact information-theoretic bounds.
* **Pathway B — Physics, Signal Processing & Information Theory:**
  * Track how discrete microstate counting on $\Omega_{k} = \mathbb{Z}/N_{k}\mathbb{Z}$ generates **Shannon entropy** and zero-crosstalk orthogonal channels (Section 2.4), and how zooming down the primorial trie induces **Kullback-Leibler divergence** (Section 4.5) and **Fisher information curvature** $g^{(k)}$ (Section 4.7).
  * In Section 5, watch $\pi$ and $e$ emerge as transverse and longitudinal scaling constants of the prime lattice, and see **Artin's product formula** ($\prod_{v \le \infty} \lvert q \rvert_{v} = 1$) enforce global scale conservation across all local and Archimedean places.
  * In Section 6, follow how Fourier wave analysis on $\mathbb{A}_{\mathbb{Q}}$ turns the Gaussian-ball product state $f$ into a **self-dual vacuum eigenstate** ($\widehat{f} = f$) and translates the Riemann Hypothesis into **reflection positivity** ($W(g_{0} * g_{0}^*) \ge 0$).
* **Pathway C — Pure Mathematics (Algebra, Topology & Number Theory):**
  * Observe how initial-algebra freeness, Grothendieck completion, and localization construct $\mathbb{N}, \mathbb{Z}, \mathbb{Q}, \mathbb{R}$ without set-theoretic ordinals (Section 1); and
  * How Stone-Haar duality, Brouwer's characterization, and Rohlin's isomorphism identify $R_{\infty}$ with $\mathbf{2}^{\mathbb{N}}$ and $[0, 1]$ while distinguishing square-free $R_{\infty} \cong \widehat{\mathbb{Z}}/\operatorname{rad}(\widehat{\mathbb{Z}})$ from full profinite $\widehat{\mathbb{Z}}$ (Sections 4 and 5).
  * Follow the complete, self-contained proof of **Tate's functional equation** and the **Weil-Guinand explicit formula** in Section 6, including the exact exponentially weighted Schwartz test algebra $\mathcal{S}_{\text{exp}}(\mathbb{R})$ required for off-line holomorphic continuation.

---

## VII. Anatomy of a Formal Section: How to Read the Derivations ^intro-7

To ensure that no step is ever hidden or taken on faith, every formal section in this treatise adheres to five uniform structural conventions:

1. **Explicit Causal Lineage (`*Parent Derivation:*`):** Every Axiom, Postulate, Definition, Lemma, Theorem, Corollary, and Remark begins with a `*Parent Derivation:*` line listing the exact upstream nodes from which it is derived. Nothing ever cites a result that appears later in the text—you can trace any theorem all the way back to `Axiom 1.1` ($\Sigma = \{\Xi\}$) simply by following its parent links upward.
2. **Intuition Roadmaps (`*Intuition:*`):** Before every multi-step proof, a concise two-sentence intuition block explains the geometric, probabilistic, or mechanical idea behind the proof in plain English so you see *why* the theorem is true before checking the algebra.
3. **Discretized Operational Proofs (`1. **[Step Name]:** ...`):** Every proof—regardless of length—is structured as an ordered, numbered list of labeled deductive phases (`1. **Base Case:**`, `2. **Inductive Step:**`, `3. **Closure:**`), making every logical inference isolated, citeable, and easy to verify.
4. **Worked Examples and Category Guards:** Concrete numerical traces (such as dividing $\Xi^{7}$ by $\Xi^{3}$, mapping $\mathbb{Z}/6\mathbb{Z} \cong \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z}$, computing signed arithmetic in $\mathcal{Z}_{2}$, and verifying adelic reciprocity at $q = 5/6$) instantiate abstract symbols immediately after key theorems, while explicit **Category Guards** (`Remark 4.1` and `Remark 5.1`) warn against subtle topological or algebraic pitfalls.
5. **Emergent Isomorphism Bridges:** Post-proof synthesis blocks explicitly connect each newly built constructive object to its classical counterparts across mathematics, computer science, and physics.

---

## VIII. Transition to the Formal Architecture ^intro-8

With the conceptual landscape, construction methods, everyday intuitions, and reading conventions in place, we are ready to formalize the treatise's methodological rules. **Section 0 (Architectural Prologue & Reader's Orientation)** codifies the principle of zero-primitive constructivism (`Postulate 0.1`), formally defines the **Emergent Isomorphism Bridge** pattern and monotonic dependency graph, and presents the **Six-Stratum Causal Ladder** governing Sections 1 through 6 and Appendix A.


---

---

# Section 0: Architectural Prologue & Reader's Orientation ^sec-0

## 0.1 The Foundational Bootstrapping Problem and Unification Thesis ^sec-0-1

Classical mathematics and theoretical physics are typically encountered as separate conceptual islands. Arithmetic begins with Peano's axioms; the continuum is built separately via Dedekind cuts or Cauchy sequences; information capacity is postulated via Shannon's entropy axioms; non-Archimedean geometry is constructed via $p$-adic completions; and the distribution of prime numbers is analyzed through complex-analytic continuation of the Riemann zeta function. Because each island imports external primitives—sets, ordinals, infinity, continuity, or measure—their deep structural unity appears accidental rather than inevitable.

This treatise eliminates those ungrounded primitives and derives all six domains sequentially from a single discrete root: an alphabet containing one indistinguishable token $\Xi$. Rather than restating textbook theorems in unfamiliar symbols, the calculus demonstrates that arithmetic, Shannon channel orthogonality, bounded-carry automata, Cantor topology, Fisher information geometry, the transcendental constants $\pi$ and $e$, Pontryagin self-dual adeles, and Weil's spectral positivity criterion are **emergent structural invariants** of one continuous, feed-forward derivation chain.


<br>

##### Postulate 0.1: Methodological Principle of Zero-Primitive Constructivism ^postulate-0-1

*Parent Derivation:* Root epistemological initialization ($t_{\text{meta}}$); no upstream formal dependencies.

No external numerical sets ($\mathbb{N}, \mathbb{Z}, \mathbb{Q}, \mathbb{R}$), topological spaces, probability measures, or analytic constants ($\pi, e$) may be invoked as primitive assumptions. Every algebraic structure, metric, measure, and functional identity in this treatise must be constructed strictly forward from an initial discrete signature using finitary structural induction and explicit quotient, localization, or projective-limit completions.

---

## 0.2 The Construct-First, Recognize-Second Discipline ^sec-0-2

A first-principles unification faces two symmetric pedagogical hazards:

1. **Premature Naming (Circularity Hazard):** Introducing classical labels such as natural numbers, Chinese Remainder Theorem, or Shannon entropy before constructing their underlying mechanisms creates circular dependencies and obscures how those laws arise.
2. **Shadowed Landmarks (Disorientation Hazard):** Concealing the classical identity of newly constructed objects forces readers from computer science, physics, or pure mathematics to traverse unfamiliar notation without recognizing the familiar mathematical landmarks crystallizing in front of them.

To resolve both hazards simultaneously, every major transition in this document obeys a strict three-phase **Construct-First, Recognize-Second** cadence.


<br>

##### Definition 0.1: Emergent Isomorphism Bridge ^def-0-1

*Parent Derivation:* [[#^postulate-0-1|Postulate 0.1]].

An **Emergent Isomorphism Bridge** is a post-proof structural identification consisting of three ordered phases across consecutive constructive strata $S_{m}$ and $S_{m+1}$:

1. **Operational Bottleneck:** Identification of an explicit computational, representational, or topological limitation inherent to stratum $S_{m}$.
2. **Intrinsic Forward Derivation:** Construction of an upgraded algebraic or topological structure $\mathcal{X}_{m+1}$ and proof of its governing laws using exclusively entities defined in $\bigcup_{j=0}^{m} S_{j}$.
3. **Unshadowed Re-Contextualization:** Exhibition of an explicit structure-preserving map $\Phi: \mathcal{X}_{m+1} \xrightarrow{\cong} \mathcal{C}$ onto a classical mathematical or physical object $\mathcal{C}$ *after* the intrinsic proof is complete, contrasting how $\mathcal{C}$ is postulated top-down in standard literature with how $\mathcal{X}_{m+1}$ emerges bottom-up here.


<br>

##### Definition 0.2: Monotonic Causal Dependency Graph ^def-0-2

*Parent Derivation:* [[#^postulate-0-1|Postulate 0.1]], [[#^def-0-1|Definition 0.1]].

The deductive architecture of this treatise is modeled as a finite directed acyclic graph $\mathcal{G} \coloneq (\mathcal{V}, \mathcal{E})$, where $\mathcal{V}$ is the set of formal nodes (axioms, definitions, lemmas, theorems, corollaries, and remarks) and $(u \to v) \in \mathcal{E}$ denotes that node $u$ is cited as an upstream parent dependency of node $v$. Equip $\mathcal{V}$ with a chronological stratum rank $\tau: \mathcal{V} \to \{t_{0}, t_{1}, t_{2}, t_{3}, t_{4}, t_{5}, t_{6}\}$ satisfying:

$$
\forall (u \to v) \in \mathcal{E}, \quad \tau(u) \le \tau(v) \quad \land \quad \operatorname{pos}(u) < \operatorname{pos}(v)
$$

where $\operatorname{pos}(w) \in \mathbb{N}_{\ge 1}$ denotes the linear textual position of node $w$ within the manuscript.

---

## 0.3 The Six-Stratum Causal Ladder ^sec-0-3

Applying [[#^postulate-0-1|Postulate 0.1]], [[#^def-0-1|Definition 0.1]], and [[#^def-0-2|Definition 0.2]] partitions the entire treatise into a root initialization epoch $t_{0}$ followed by six progressive strata $S_{1}$ through $S_{6}$.


<br>

##### Definition 0.3: Six-Stratum Constructive Hierarchy ^def-0-3

*Parent Derivation:* [[#^def-0-1|Definition 0.1]], [[#^def-0-2|Definition 0.2]].

Define the **Six-Stratum Constructive Hierarchy** as the ordered sequence of formal domains $(S_{1}, S_{2}, S_{3}, S_{4}, S_{5}, S_{6})$ anchored at root substrate $t_{0}$:

1. **Stratum $S_{1}$ (Epoch $t_{1}$ — Singleton Monoid & Constructive Number Rings):** Generates the free initial algebra $\Sigma^*$ from $\Sigma \coloneq \{\Xi\}$, proves commutative semiring laws intrinsically via concatenation ($\cdot$) and substitution ($\text{flatMap}$), derives Peano arithmetic ($\mathbb{N}$), establishes terminating Euclidean prefix-rewriting ($\to_{B}$), and constructs $\mathbb{Z}$, $\mathbb{Q}$, and the Cauchy real field $\mathbb{R}$.
2. **Stratum $S_{2}$ (Epoch $t_{2}$ — Unary Prime Sieve, CRT & Orthogonal Channels):** Overcomes the $O(N)$ storage bottleneck of unary strings by defining unary divisibility ($\mid_{\Sigma}$), generating the infinite prime word sequence $\mathcal{P}$, proving unique prime word factorization, and establishing the Chinese Remainder Theorem ring isomorphism $\Psi_{k}: \mathbb{Z}/N_{k}\mathbb{Z} \xrightarrow{\cong} \prod_{i=1}^{k} \mathbb{F}_{p_{i}}$ along with zero Shannon mutual information $I(X_{i}; X_{j}) = 0$ across prime channels.
3. **Stratum $S_{3}$ (Epoch $t_{3}$ — Finite Algebraic Automata):** Overcomes finite modular wrap-around at $N_{k}$ by constructing unbounded mixed-radix quotient-residue tuples $\mathcal{Z}_{k} = \mathbb{Z} \times \{0, \dots, N_{k} - 1\}$ with unit-bounded carries/borrows and carry-free RNS residue execution, signed floating-point Tri-Strings $\mathcal{F}_{\mathbb{Z}}$, and the deterministic Chiral Prime Parity Finite-State Transducer $\mathcal{M}$ over $(\mathbb{Z}/6\mathbb{Z})^\times$.
4. **Stratum $S_{4}$ (Epoch $t_{4}$ — Profinite Stone Limits & Ultrametric Calculus):** Overcomes fixed resolution depth $k$ by passing to the inverse limit $R_{\infty} \coloneq \varprojlim_{k} (\mathbb{Z}/N_{k}\mathbb{Z})$, proving homeomorphism to the Cantor space $\mathbf{2}^{\mathbb{N}}$, measure-theoretic Rohlin equivalence to $([0, 1], \lambda)$, non-Archimedean van der Put differentiation, Riemann-Haar integration, and the tripartite equivalence $\mu(B_{k}) = 2^{-H_{k}} = (g^{(k)})^{-1/2}$ linking Haar volume, Shannon entropy, and Fisher curvature.
5. **Stratum $S_{5}$ (Epoch $t_{5}$ — Emergent Transcendentals & Adelic Self-Duality):** Overcomes the exclusion of prime powers $p^{m}$ in square-free $R_{\infty}$ by extracting $\pi$ from two-dimensional bivariate non-collision density and $e$ from one-dimensional primorial entropy density, constructing vertical $p$-adic towers $\mathbb{Q}_{p}$, fusing $\mathbb{R}$ and all $\mathbb{Q}_{p}$ into the restricted adele ring $\mathbb{A}_{\mathbb{Q}}$, resolving $R_{\infty} \cong \widehat{\mathbb{Z}}/\operatorname{rad}(\widehat{\mathbb{Z}})$, and proving Artin's product formula, Tamagawa volume $1$, and Pontryagin autoduality $\mathbb{Q}^\perp = \Delta(\mathbb{Q})$.
6. **Stratum $S_{6}$ (Epoch $t_{6}$ — Adelic Poisson Summation, Tate's Equation & Weil Positivity):** Applies Fourier analysis on the self-dual adele ring $\mathbb{A}_{\mathbb{Q}}$ to the Gaussian-ball kernel $f(x) = e^{-\pi x_{\infty}^{2}} \prod_{p} \mathbf{1}_{\mathbb{Z}_{p}}(x_{p})$, proving $\widehat{f} = f$, idele zeta factorization, Tate's functional equation $\Lambda(1 - s) = \Lambda(s)$, the Weil-Guinand explicit distribution formula, and the bidirectional equivalence between Weil positivity on $\mathcal{S}_{\text{exp}}(\mathbb{R})$ and the Riemann Hypothesis.

The causal dependency flow across all strata is summarized in the following architectural ladder:

```text
[t0] Root Substrate: Singleton Alphabet (\Sigma = {\Xi}) & Initial Algebra (\Sigma*)
       |
       v
[t1] Section 1: Monoid (\cdot), Substitution (flatMap) ---> Peano N, Ring Z, Field Q, Continuum R
       |
       v
[t2] Section 2: Unary Prime Sieve (P) & CRT (\Psi_k) ---> Orthogonal Channels (I(X_i; X_j) = 0)
       |
       v
[t3] Section 3: Mixed-Radix Tuples (Z_k), Tri-Strings (F_Z) & Chiral Parity FST (M)
       |
       v
[t4] Section 4: Profinite Limit (R_\infty) ---> Cantor Space (2^N), Rohlin [0,1], Fisher Metric (g^(k))
       |
       v
[t5] Section 5: Transcendentals (\pi, e) & p-adic Towers (Q_p) ---> Self-Dual Adele Ring (A_Q)
       |
       v
[t6] Section 6: Adelic Poisson Summation ---> Tate's \Lambda(1-s) = \Lambda(s) & Weil Positivity (RH)
       |
       v
[App. A] Cross-Disciplinary Rosetta Stone & Unified Symbol Index
```

The table below indexes the operational bottleneck solved by each section alongside its emergent classical counterparts:

| Section | Epoch | Core Constructive Machinery | Bottleneck Resolved | Emergent Classical Landmarks |
| :--- | :--- | :--- | :--- | :--- |
| **Section 1** | $t_{0} \to t_{1}$ | $(\Sigma^*, \cdot, \text{flatMap}, \varepsilon, \Xi)$, $\to_{B}$, $\mathbb{Z}, \mathbb{Q}, \mathbb{R}$ | Absence of numerical primitives, subtraction, ratios, and limits | Peano arithmetic, Euclidean division, $\mathbb{N}, \mathbb{Z}, \mathbb{Q}, \mathbb{R}$ |
| **Section 2** | $t_{1} \to t_{2}$ | $\mid_{\Sigma}$, prime sequence $\mathcal{P}$, primorial $N_{k}$, $\Psi_{k}$ | $O(N)$ unary storage cost and sequential carry coupling | Fundamental Theorem of Arithmetic, CRT, Shannon entropy |
| **Section 3** | $t_{2} \to t_{3}$ | $\mathcal{Z}_{k} = \mathbb{Z} \times \{0, \dots, N_{k}-1\}$, $\mathcal{F}_{\mathbb{Z}}$, FST $\mathcal{M}$ | Finite modular wrap-around at $N_{k}$ and negative exponents | Mixed-radix RNS hardware, floating-point, mod-$6$ wheel sieve |
| **Section 4** | $t_{3} \to t_{4}$ | $R_{\infty} = \varprojlim_{k} \mathbb{Z}/N_{k}\mathbb{Z}$, $d(x,y)$, $D_{\mathcal{T}}^{(k)}$, $g^{(k)}$ | Truncated primorial resolution at fixed finite depth $k$ | Stone-Cantor space $\mathbf{2}^{\mathbb{N}}$, Rohlin $[0,1]$, Fisher metric |
| **Section 5** | $t_{4} \to t_{5}$ | $\rho_{k} \to 6/\pi^{2}$, $N_{k}^{1/\text{len}(p_{k})} \to e$, $\mathbb{Q}_{p}$, $\mathbb{A}_{\mathbb{Q}}$, $\psi$ | Omission of prime powers $p^{m}$ and lack of global scale invariance | Constants $\pi$ and $e$, $p$-adic numbers, Chevalley-Weil adeles |
| **Section 6** | $t_{5} \to t_{6}$ | $\mathcal{S}(\mathbb{A}_{\mathbb{Q}})$, $\widehat{f} = f$, $\mathbb{I}_{\mathbb{Q}}$, $\Lambda(s)$, $W(g_{0} * g_{0}^*)$ | Lack of global spectral duality linking primes to zeta zeros | Adelic Poisson summation, Tate's thesis, Weil RH criterion |
| **Appendix A** | $t_{6}$ | Cross-disciplinary translation matrix & symbol index | Terminological fragmentation across CS, physics, and math | Unified CS / Information-Physics / Mathematics Rosetta Stone |


<br>

##### Theorem 0.1: Acyclic Feed-Forward Closure of the Six-Stratum Architecture ^thm-0-1

*Parent Derivation:* [[#^postulate-0-1|Postulate 0.1]], [[#^def-0-1|Definition 0.1]], [[#^def-0-2|Definition 0.2]], [[#^def-0-3|Definition 0.3]].

The constructive hierarchy $(S_{1}, \dots, S_{6})$ of [[#^def-0-3|Definition 0.3]] satisfies strict topological monotonicity ($\tau(u) \le \tau(v)$ for every dependency edge $u \to v$)  without backward circularity.

*Intuition:* Each stratum introduces new algebraic or topological structure only after its preceding stratum supplies every required carrier set, operation, and metric, while classical mathematical identifications are attached strictly downstream of the proofs that construct them.

*Proof:*

1. **Base Substrate Initiation ($t_{0} \to t_{1}$):** By [[#^postulate-0-1|Postulate 0.1]], Stratum $S_{1}$ begins solely from the singleton alphabet $\Sigma = \{\Xi\}$ at $t_{0}$, proving commutative semiring laws intrinsically on $\Sigma^*$ before defining $\mathbb{N}, \mathbb{Z}, \mathbb{Q}$, and the Cauchy completion $\mathbb{R}$, thereby providing the Archimedean continuum and $\log_{2}$ prior to any metric or entropic invocation in $S_{2}$–$S_{4}$.

2. **Monotonic Bottleneck-Driven Transitions ($t_{1} \to t_{5}$):** Under [[#^def-0-3|Definition 0.3]], each transition $S_{m} \to S_{m+1}$ ($1 \le m \le 4$) resolves an explicit representational bottleneck of $S_{m}$ using strictly upstream objects: unary length compression yields CRT channels ($S_{2}$); finite modular wrap-around yields unbounded mixed-radix registers and automata ($S_{3}$); finite primorial depth yields the projective Stone limit $R_{\infty}$ ($S_{4}$); and square-free truncation yields $p$-adic towers $\mathbb{Q}_{p}$, emergent constants $\pi, e$, and the self-dual adele ring $\mathbb{A}_{\mathbb{Q}}$ ($S_{5}$).

3. **Global Spectral Synthesis and Acyclic Closure ($t_{5} \to t_{6}$):** Stratum $S_{6}$ invokes solely the locally compact Pontryagin self-dual ring $\mathbb{A}_{\mathbb{Q}}$ and Artin scale invariance established in $S_{5}$ to prove Tate's functional equation and the Weil positivity criterion, while [[#^def-0-1|Definition 0.1]] confines all classical identifications to post-proof Emergent Isomorphism Bridges, guaranteeing $\operatorname{pos}(u) < \operatorname{pos}(v)$ across $\mathcal{G}$ in compliance with [[#^def-0-2|Definition 0.2]].


<br>

##### Remark 0.1: Methodological Scope of External Analytical Bridges ^rem-0-1

*Parent Derivation:* [[#^postulate-0-1|Postulate 0.1]], [[#^thm-0-1|Theorem 0.1]].

While Strata $S_{1}$ through $S_{3}$ and all algebraic, measure-theoretic, and Fourier-duality derivations in Strata $S_{4}$ through $S_{6}$ are proved constructively from [[#^axiom-1-1|Axiom 1.1]], four classical theorems of topology and complex analysis are invoked explicitly as downstream analytical bridges rather than re-proved from scratch: Brouwer's characterization of the Cantor space (`Theorem 4.2`), Rohlin's standard Borel isomorphism (`Theorem 4.8`), the Wiener–Ikehara Tauberian Prime Number Theorem (`Lemma 5.4a`), and Paley–Wiener–Schwartz / Riemann–von Mangoldt zero-density bounds (`Definition 6.5`–`Theorem 6.6`).

---

## 0.4 Reader's Navigation Guide and Structural Key ^sec-0-4

Readers entering from different technical backgrounds can track their native concepts as they emerge along the causal ladder:

* **Computer Science & Formal Automata:** Focus on initial-algebra structural induction (`Section 1.1`), strongly normalizing term rewriting (`Section 1.4`), carry-free Residue Number System (RNS) execution (`Section 3.3`), deterministic finite-state transducers (`Section 3.5`), and prefix trie geodesics (`Section 4.5`).
* **Information Theory & Theoretical Physics:** Focus on prime-channel statistical independence and zero mutual information (`Section 2.4`), branch Kullback-Leibler divergence (`Section 4.5`), the tripartite equivalence between Haar measure, Shannon entropy, and Fisher curvature (`Section 4.7`), global scale conservation via Artin's product formula (`Section 5.4`), and reflection positivity (`Section 6.5`).
* **Pure Algebra, Topology & Number Theory:** Focus on Grothendieck ring and field completions (`Section 1.5`), primorial CRT ring isomorphisms (`Section 2.2`), profinite Stone-Haar spaces and Rohlin measure isomorphism (`Section 4.1`–`Section 4.4`), non-Archimedean van der Put calculus (`Section 4.6`), Pontryagin autoduality of $\mathbb{A}_{\mathbb{Q}}$ (`Section 5.5`), and Tate's adelic zeta integral (`Section 6.2`–`Section 6.4`).

Throughout Sections 1 through 6, four standardized pedagogical markers structure the exposition:

1. **Formal Nodes (`Axiom`, `Definition`, `Lemma`, `Theorem`, `Corollary`, `Remark`):** Self-contained mathematical statements with unique lowercase kebab-case anchors, explicit `*Parent Derivation:*` lineage links pointing strictly upstream, and step-by-step numbered proofs.
2. **Intuition Roadmaps (`*Intuition:*`):** Concise two-sentence conceptual previews placed immediately before multi-step proofs to illuminate the geometric or informational mechanism behind the algebra.
3. **Worked Examples:** Concrete numerical and symbolic traces instantiating abstract operators (such as `flatMap`, Euclidean rewriting, CRT coordinate tables, signed $\mathcal{Z}_{k}$ arithmetic, chiral FST transitions, ultrametric distances, and adelic reciprocity).
4. **Emergent Isomorphism Bridges:** Post-derivation synthesis blocks explicitly connecting newly constructed structures to classical mathematics and physics in accordance with [[#^def-0-1|Definition 0.1]].

---

---

# Section 1: Foundations — The Singleton Monoid Substrate and Constructive Number Rings ^sec-1

*Entry Primer:* How do we construct counting, addition, multiplication, remainder division, negative integers, fractions, and the real continuum from an alphabet containing a single indistinguishable symbol and zero pre-existing numbers? In this section, we build the entire numerical tower from a unary tally word generator, proving all algebraic laws intrinsically by structural induction before connecting them to classical arithmetic.

## 1.1 Substrate Initialization and Intrinsic Commutative Monoid ^sec-1-1

To construct a mathematically rigorous foundation without smuggling ungrounded numerical primitives or external set-theoretic ordinals ([[#^postulate-0-1|Postulate 0.1]]), the calculus begins at the minimal discrete combinatorial substrate: an alphabet containing a single indistinguishable token.


<br>

##### Axiom 1.1: Singleton Alphabet ^axiom-1-1

*Parent Derivation:* [[#^postulate-0-1|Postulate 0.1]].

Let $\Sigma$ be the degenerate alphabet containing exactly one indistinguishable token $\Xi$:

$$
\Sigma \coloneq \{\Xi\}
$$

*Notation Rationale:* The Greek letter $\Xi$ ("Xi") is chosen as a symmetric, indivisible horizontal tally bar visually evoking discrete parallel rungs.


<br>

##### Definition 1.1: Initial Algebra of the Free Monoid ^def-1-1

*Parent Derivation:* [[#^axiom-1-1|Axiom 1.1]].

The set of all finite words $\Sigma^*$ is generated as the free initial algebra over the signature $(\varepsilon, S)$:

1. **Base Constructor:** The empty word $\varepsilon \in \Sigma^*$.

2. **Unary Successor Constructor:** For every word $w \in \Sigma^*$, the successor constructor appends a single token $\Xi$:

$$
S(w) \coloneq \text{cons}(w, \Xi) \in \Sigma^*
$$

3. **Initial Algebra Freeness and Structural Induction Schema:** The constructors $\varepsilon$ and $S$ have disjoint images ($\forall w \in \Sigma^*, \, S(w) \neq \varepsilon$) and $S$ is injective ($\forall u, v \in \Sigma^*, \, S(u) = S(v) \implies u = v$). For any unary predicate $\Phi$ over $\Sigma^*$, truth on the base word and preservation under successor application imply universal truth across $\Sigma^*$:

$$
\left[ \Phi(\varepsilon) \land \left( \forall w \in \Sigma^*, \, \Phi(w) \implies \Phi(S(w)) \right) \right] \implies \forall w \in \Sigma^*, \, \Phi(w)
$$


<br>

##### Definition 1.2: Canonical Unit Word and Concatenation Operation ^def-1-2

*Parent Derivation:* [[#^def-1-1|Definition 1.1]].

Define the canonical unit word $\Xi \coloneq S(\varepsilon) \in \Sigma^*$ (identifying the singleton token with the single-step successor of $\varepsilon$) and define binary word concatenation $\cdot : \Sigma^* \times \Sigma^* \to \Sigma^*$ recursively by structural induction on its second argument:

$$
\forall u \in \Sigma^*, \quad u \cdot \varepsilon \coloneq u
$$

$$
\forall u, v \in \Sigma^*, \quad u \cdot S(v) \coloneq S(u \cdot v)
$$

Evaluating at $v = \varepsilon$ yields $u \cdot \Xi = u \cdot S(\varepsilon) = S(u \cdot \varepsilon) = S(u)$ for every $u \in \Sigma^*$.


<br>

##### Theorem 1.1: Commutative Monoid Laws on $\Sigma^*$ ^thm-1-1

*Parent Derivation:* [[#^def-1-1|Definition 1.1]], [[#^def-1-2|Definition 1.2]].

The algebraic structure $(\Sigma^*, \cdot, \varepsilon)$ forms a commutative monoid satisfying two-sided identity, associativity, and commutativity for all $u, v, w \in \Sigma^*$:

$$
u \cdot \varepsilon = \varepsilon \cdot u = u
$$

$$
(u \cdot v) \cdot w = u \cdot (v \cdot w)
$$

$$
u \cdot v = v \cdot u
$$

*Intuition:* Because every word in $\Sigma^*$ is built by repeatedly applying a single unary successor $S$ to $\varepsilon$, shifting a successor step across an intermediate word preserves total step count, forcing concatenation to be both associative and commutative without invoking external numbers.

*Proof:*

1. **Right Identity Verification:** By [[#^def-1-2|Definition 1.2]], $u \cdot \varepsilon = u$ holds identically for all $u \in \Sigma^*$.

2. **Left Identity Induction:** At $u = \varepsilon$, [[#^def-1-2|Definition 1.2]] gives $\varepsilon \cdot \varepsilon = \varepsilon$. Assuming $\varepsilon \cdot u = u$, applying [[#^def-1-2|Definition 1.2]] yields:

$$
\varepsilon \cdot S(u) = S(\varepsilon \cdot u) = S(u)
$$

By structural induction ([[#^def-1-1|Definition 1.1]]), $\varepsilon \cdot u = u$ holds for all $u \in \Sigma^*$.

3. **Associativity Induction:** For arbitrary $u, v \in \Sigma^*$, the base case $w = \varepsilon$ satisfies $(u \cdot v) \cdot \varepsilon = u \cdot v = u \cdot (v \cdot \varepsilon)$ by [[#^def-1-2|Definition 1.2]]. Assuming $(u \cdot v) \cdot w = u \cdot (v \cdot w)$, applying [[#^def-1-2|Definition 1.2]] twice yields:

$$
(u \cdot v) \cdot S(w) = S((u \cdot v) \cdot w) = S(u \cdot (v \cdot w)) = u \cdot S(v \cdot w) = u \cdot (v \cdot S(w))
$$

By structural induction on $w$ via [[#^def-1-1|Definition 1.1]], associativity holds globally.

4. **Unit Commutativity ($\Xi \cdot u = u \cdot \Xi$):** At $u = \varepsilon$, Steps 1 and 2 give $\Xi \cdot \varepsilon = \Xi = \varepsilon \cdot \Xi$. Assuming $\Xi \cdot u = u \cdot \Xi$, using $S(z) = z \cdot \Xi$ ([[#^def-1-2|Definition 1.2]]) and Step 3 gives:

$$
\Xi \cdot S(u) = \Xi \cdot (u \cdot \Xi) = (\Xi \cdot u) \cdot \Xi = (u \cdot \Xi) \cdot \Xi = S(u) \cdot \Xi
$$

By structural induction on $u$, $\Xi \cdot u = u \cdot \Xi$ holds for all $u \in \Sigma^*$.

5. **General Commutativity Closure ($u \cdot v = v \cdot u$):** For arbitrary $u \in \Sigma^*$, the base case $v = \varepsilon$ holds by Steps 1 and 2 ($u \cdot \varepsilon = u = \varepsilon \cdot u$). Assuming $u \cdot v = v \cdot u$, combining [[#^def-1-2|Definition 1.2]], Step 3, and Step 4 yields:

$$
u \cdot S(v) = u \cdot (v \cdot \Xi) = (u \cdot v) \cdot \Xi = (v \cdot u) \cdot \Xi = v \cdot (u \cdot \Xi) = v \cdot (\Xi \cdot u) = (v \cdot \Xi) \cdot u = S(v) \cdot u
$$

By structural induction on $v$ via [[#^def-1-1|Definition 1.1]], $(\Sigma^*, \cdot, \varepsilon)$ is a commutative monoid.

---

## 1.2 Multiplicative Substitution Endomorphism and Intrinsic Semiring Laws ^sec-1-2

Concatenation combines words linearly; to generate quadratic and higher-order scaling purely within $\Sigma^*$, we define uniform token substitution.


<br>

##### Definition 1.3: Multiplicative Substitution Endomorphism ^def-1-3

*Parent Derivation:* [[#^def-1-1|Definition 1.1]], [[#^def-1-2|Definition 1.2]].

The binary substitution operator $\text{flatMap}: \Sigma^* \times \Sigma^* \to \Sigma^*$ is defined recursively on its first argument by replacing every token $\Xi$ in $u$ with a copy of the second word $v$:

$$
\forall v \in \Sigma^*, \quad \text{flatMap}(\varepsilon, v) \coloneq \varepsilon
$$

$$
\forall u, v \in \Sigma^*, \quad \text{flatMap}(u \cdot \Xi, v) \coloneq \text{flatMap}(u, v) \cdot v
$$

*Notation Rationale:* The identifier `flatMap` is drawn from functional programming's monadic bind operation, mapping each token $\Xi \mapsto v$ and flattening the resulting word sequence via concatenation.


<br>

##### Theorem 1.2: Intrinsic Commutative Semiring Structure of $(\Sigma^*, \cdot, \text{flatMap}, \varepsilon, \Xi)$ ^thm-1-2

*Parent Derivation:* [[#^def-1-1|Definition 1.1]], [[#^thm-1-1|Theorem 1.1]], [[#^def-1-3|Definition 1.3]].

Without invoking external numerical axioms, the structure $(\Sigma^*, \cdot, \text{flatMap}, \varepsilon, \Xi)$ forms a commutative semiring satisfying annihilation by $\varepsilon$, two-sided multiplicative unit $\Xi$, left and right distributivity, associativity, and commutativity for all $u, v, w \in \Sigma^*$:

$$
\text{flatMap}(u, \varepsilon) = \text{flatMap}(\varepsilon, u) = \varepsilon
$$

$$
\text{flatMap}(u, \Xi) = \text{flatMap}(\Xi, u) = u
$$

$$
\text{flatMap}(u \cdot v, w) = \text{flatMap}(u, w) \cdot \text{flatMap}(v, w)
$$

$$
\text{flatMap}(u, v \cdot w) = \text{flatMap}(u, v) \cdot \text{flatMap}(u, w)
$$

$$
\text{flatMap}(\text{flatMap}(u, v), w) = \text{flatMap}(u, \text{flatMap}(v, w))
$$

$$
\text{flatMap}(u, v) = \text{flatMap}(v, u)
$$

*Intuition:* Every semiring identity follows directly from structural induction on $\Sigma^*$: distributing a substituted block over a concatenated word splits the substitution across the prefix and suffix, while commutativity follows because replacing $u$ tokens by $v$ produces the same rectangular grid of tokens as replacing $v$ tokens by $u$.

*Proof:*

1. **Annihilation and Multiplicative Unit Laws:** By [[#^def-1-3|Definition 1.3]], $\text{flatMap}(\varepsilon, u) = \varepsilon$, and structural induction on $u$ using $\varepsilon \cdot \varepsilon = \varepsilon$ ([[#^thm-1-1|Theorem 1.1]]) gives $\text{flatMap}(u, \varepsilon) = \varepsilon$. Similarly, $\text{flatMap}(\Xi, u) = \text{flatMap}(\varepsilon \cdot \Xi, u) = \varepsilon \cdot u = u$, while induction on $u$ gives $\text{flatMap}(u \cdot \Xi, \Xi) = \text{flatMap}(u, \Xi) \cdot \Xi = u \cdot \Xi$, proving $\text{flatMap}(u, \Xi) = u$.

2. **Left Distributivity Induction:** Fix $u, w \in \Sigma^*$ and induct on $v$. At $v = \varepsilon$, [[#^thm-1-1|Theorem 1.1]] and Step 1 give $\text{flatMap}(u \cdot \varepsilon, w) = \text{flatMap}(u, w) = \text{flatMap}(u, w) \cdot \varepsilon = \text{flatMap}(u, w) \cdot \text{flatMap}(\varepsilon, w)$. Assuming $\text{flatMap}(u \cdot v, w) = \text{flatMap}(u, w) \cdot \text{flatMap}(v, w)$, associativity of $\cdot$ ([[#^thm-1-1|Theorem 1.1]]) and [[#^def-1-3|Definition 1.3]] yield:

$$
\text{flatMap}(u \cdot (v \cdot \Xi), w) = \text{flatMap}((u \cdot v) \cdot \Xi, w) = \text{flatMap}(u \cdot v, w) \cdot w = \text{flatMap}(u, w) \cdot (\text{flatMap}(v, w) \cdot w) = \text{flatMap}(u, w) \cdot \text{flatMap}(v \cdot \Xi, w)
$$

3. **Right Distributivity Induction:** Fix $v, w \in \Sigma^*$ and induct on $u$. At $u = \varepsilon$, $\text{flatMap}(\varepsilon, v \cdot w) = \varepsilon = \varepsilon \cdot \varepsilon$. Assuming $\text{flatMap}(u, v \cdot w) = \text{flatMap}(u, v) \cdot \text{flatMap}(u, w)$, applying [[#^def-1-3|Definition 1.3]] together with associativity and commutativity of $\cdot$ ([[#^thm-1-1|Theorem 1.1]]) gives:

$$
\text{flatMap}(u \cdot \Xi, v \cdot w) = (\text{flatMap}(u, v) \cdot \text{flatMap}(u, w)) \cdot (v \cdot w) = (\text{flatMap}(u, v) \cdot v) \cdot (\text{flatMap}(u, w) \cdot w) = \text{flatMap}(u \cdot \Xi, v) \cdot \text{flatMap}(u \cdot \Xi, w)
$$

4. **Associativity of Substitution:** Fix $v, w \in \Sigma^*$ and induct on $u$. At $u = \varepsilon$, both sides equal $\varepsilon$. Assuming $\text{flatMap}(\text{flatMap}(u, v), w) = \text{flatMap}(u, \text{flatMap}(v, w))$, Step 2 (left distributivity) yields:

$$
\text{flatMap}(\text{flatMap}(u \cdot \Xi, v), w) = \text{flatMap}(\text{flatMap}(u, v) \cdot v, w) = \text{flatMap}(\text{flatMap}(u, v), w) \cdot \text{flatMap}(v, w) = \text{flatMap}(u \cdot \Xi, \text{flatMap}(v, w))
$$

5. **Commutativity of Substitution:** Fix $v \in \Sigma^*$ and induct on $u$. At $u = \varepsilon$, Step 1 gives $\text{flatMap}(\varepsilon, v) = \varepsilon = \text{flatMap}(v, \varepsilon)$. Assuming $\text{flatMap}(u, v) = \text{flatMap}(v, u)$, combining [[#^def-1-3|Definition 1.3]], Step 1, and Step 3 (right distributivity) gives:

$$
\text{flatMap}(u \cdot \Xi, v) = \text{flatMap}(u, v) \cdot v = \text{flatMap}(v, u) \cdot \text{flatMap}(v, \Xi) = \text{flatMap}(v, u \cdot \Xi)
$$

Thus $(\Sigma^*, \cdot, \text{flatMap}, \varepsilon, \Xi)$ is an intrinsic commutative semiring.

**Worked Example 1 (Unary Word Substitution):** Let $u \coloneq \Xi \cdot \Xi$ (two tokens) and $v \coloneq (\Xi \cdot \Xi) \cdot \Xi$ (three tokens). Unrolling [[#^def-1-3|Definition 1.3]] step by step produces:

$$
\text{flatMap}(\Xi \cdot \Xi, v) = \text{flatMap}((\varepsilon \cdot \Xi) \cdot \Xi, v) = \text{flatMap}(\varepsilon \cdot \Xi, v) \cdot v = (\text{flatMap}(\varepsilon, v) \cdot v) \cdot v = (\varepsilon \cdot v) \cdot v = v \cdot v
$$

Expanding $v \cdot v$ via [[#^thm-1-1|Theorem 1.1]] yields the six-token word $\Xi \cdot \Xi \cdot \Xi \cdot \Xi \cdot \Xi \cdot \Xi$.

---

## 1.3 Emergent Peano Postulates and Scalar Tally Isomorphism ^sec-1-3

Having established the commutative semiring laws directly on $\Sigma^*$, we now prove that Peano's axioms emerge as intrinsic theorems of the initial algebra and define the canonical scalar tally isomorphism onto the natural numbers $\mathbb{N}$.


<br>

##### Theorem 1.3: Constructivist Emergence of Peano Postulates and Natural Numbers $\mathbb{N}$ ^thm-1-3

*Parent Derivation:* [[#^def-1-1|Definition 1.1]], [[#^def-1-2|Definition 1.2]], [[#^thm-1-1|Theorem 1.1]], [[#^thm-1-2|Theorem 1.2]].

The Peano arithmetic postulates hold as derived theorems of $(\Sigma^*, \cdot, \text{flatMap}, \varepsilon, \Xi)$:

1. **Zero Element:** $\varepsilon \in \Sigma^*$.

2. **Non-Surjectivity of Successor:** For every $w \in \Sigma^*$, $S(w) = w \cdot \Xi \neq \varepsilon$.

3. **Injectivity of Successor:** For all $u, v \in \Sigma^*$, $u \cdot \Xi = v \cdot \Xi \implies u = v$.

4. **Mathematical Induction:** Any unary predicate $\Phi$ holding at $\varepsilon$ and preserved under $w \mapsto w \cdot \Xi$ holds for all $w \in \Sigma^*$.

5. **Recursive Arithmetic Laws:** Addition ($u \cdot \varepsilon = u$, $u \cdot (v \cdot \Xi) = (u \cdot v) \cdot \Xi$) and multiplication ($\text{flatMap}(u, \varepsilon) = \varepsilon$, $\text{flatMap}(u, v \cdot \Xi) = \text{flatMap}(u, v) \cdot u$) hold identically on $\Sigma^*$.

*Proof:*

1. **Initial Algebra Axiom Extraction:** Postulates 1 through 4 follow immediately from the initial algebra freeness and structural induction properties of $(\varepsilon, S)$ established in [[#^def-1-1|Definition 1.1]] together with $S(w) = w \cdot \Xi$ from [[#^def-1-2|Definition 1.2]].

2. **Recursive Arithmetic Verification:** The recursive addition identities follow directly from [[#^def-1-2|Definition 1.2]], while the recursive multiplication identities follow by combining [[#^def-1-3|Definition 1.3]] with commutativity of `flatMap` proved in [[#^thm-1-2|Theorem 1.2]].


<br>

##### Definition 1.4: Recursive Tally Length Projection ^def-1-4

*Parent Derivation:* [[#^def-1-1|Definition 1.1]], [[#^thm-1-3|Theorem 1.3]].

Identifying the standard scalar natural number semiring $(\mathbb{N}, +, \times, 0, 1)$ with the Peano model of [[#^thm-1-3|Theorem 1.3]] under canonical Arabic numeral notation ($0 \coloneq \varepsilon$, $1 \coloneq \Xi$, $n + 1 \coloneq S(n)$), define the length evaluation map $\text{len}: \Sigma^* \to \mathbb{N}$ recursively on $\Sigma^*$:

$$
\text{len}(\varepsilon) \coloneq 0
$$

$$
\forall w \in \Sigma^*, \quad \text{len}(w \cdot \Xi) \coloneq \text{len}(w) + 1
$$

For each $n \in \mathbb{N}$, denote the unique canonical word of length $n$ (obtained by iterating $S$ $n$ times from $\varepsilon$) by $\Xi^{n} \in \Sigma^*$.


<br>

##### Theorem 1.4: Homomorphism of Concatenation to Natural Addition ^thm-1-4

*Parent Derivation:* [[#^def-1-1|Definition 1.1]], [[#^def-1-2|Definition 1.2]], [[#^thm-1-1|Theorem 1.1]], [[#^def-1-4|Definition 1.4]].

The length evaluation map transforms binary word concatenation into natural number addition:

$$
\forall u, v \in \Sigma^*, \quad \text{len}(u \cdot v) = \text{len}(u) + \text{len}(v)
$$

*Proof:*

1. **Base Case ($v = \varepsilon$):** By [[#^def-1-2|Definition 1.2]] and [[#^def-1-4|Definition 1.4]], for any $u \in \Sigma^*$:

$$
\text{len}(u \cdot \varepsilon) = \text{len}(u) = \text{len}(u) + 0 = \text{len}(u) + \text{len}(\varepsilon)
$$

2. **Inductive Step ($v \mapsto v \cdot \Xi$):** Assume $\text{len}(u \cdot v) = \text{len}(u) + \text{len}(v)$. Applying [[#^def-1-2|Definition 1.2]], [[#^def-1-4|Definition 1.4]], and associativity of addition ([[#^thm-1-1|Theorem 1.1]]) gives:

$$
\text{len}(u \cdot (v \cdot \Xi)) = \text{len}((u \cdot v) \cdot \Xi) = \text{len}(u \cdot v) + 1 = (\text{len}(u) + \text{len}(v)) + 1 = \text{len}(u) + (\text{len}(v) + 1) = \text{len}(u) + \text{len}(v \cdot \Xi)
$$

3. **Inductive Closure:** By structural induction on $v$ via [[#^def-1-1|Definition 1.1]], $\text{len}(u \cdot v) = \text{len}(u) + \text{len}(v)$ holds globally.


<br>

##### Theorem 1.5: Bijective Additive Monoid Isomorphism ^thm-1-5

*Parent Derivation:* [[#^thm-1-1|Theorem 1.1]], [[#^thm-1-3|Theorem 1.3]], [[#^def-1-4|Definition 1.4]], [[#^thm-1-4|Theorem 1.4]].

The evaluation map $\text{len}: (\Sigma^*, \cdot, \varepsilon) \to (\mathbb{N}, +, 0)$ is a bijective monoid homomorphism, establishing an exact isomorphism:

$$
(\Sigma^*, \cdot, \varepsilon) \cong (\mathbb{N}, +, 0)
$$

*Proof:*

1. **Injectivity Base Case ($\text{len}(u) = \text{len}(v) = 0$):** By [[#^def-1-4|Definition 1.4]] and [[#^thm-1-3|Theorem 1.3]], no successor word has length $0$, forcing $u = \varepsilon = v$.

2. **Injectivity Inductive Step ($\text{len}(u) = \text{len}(v) = k + 1$):** Assume injectivity holds for all words of length $k$. Because $\Sigma = \{\Xi\}$ is singleton, $u = u_{0} \cdot \Xi$ and $v = v_{0} \cdot \Xi$ with $\text{len}(u_{0}) = \text{len}(v_{0}) = k$. By the induction hypothesis, $u_{0} = v_{0}$, so $u = u_{0} \cdot \Xi = v_{0} \cdot \Xi = v$.

3. **Surjectivity and Isomorphism Closure:** For every $n \in \mathbb{N}$, $\text{len}(\Xi^{n}) = n$ by [[#^def-1-4|Definition 1.4]], establishing surjectivity; combining bijectivity with $\text{len}(\varepsilon) = 0$ and [[#^thm-1-4|Theorem 1.4]] completes the isomorphism.


<br>

##### Theorem 1.6: Homomorphism of Substitution to Natural Multiplication and Semiring Isomorphism ^thm-1-6

*Parent Derivation:* [[#^def-1-1|Definition 1.1]], [[#^def-1-3|Definition 1.3]], [[#^thm-1-2|Theorem 1.2]], [[#^def-1-4|Definition 1.4]], [[#^thm-1-4|Theorem 1.4]], [[#^thm-1-5|Theorem 1.5]].

The length evaluation map transforms word substitution into natural number multiplication, establishing a full commutative semiring isomorphism:

$$
\forall u, v \in \Sigma^*, \quad \text{len}(\text{flatMap}(u, v)) = \text{len}(u) \times \text{len}(v)
$$

$$
(\Sigma^*, \cdot, \text{flatMap}, \varepsilon, \Xi) \cong (\mathbb{N}, +, \times, 0, 1)
$$

*Proof:*

1. **Base Case ($u = \varepsilon$):** By [[#^def-1-3|Definition 1.3]] and [[#^def-1-4|Definition 1.4]], $\text{len}(\text{flatMap}(\varepsilon, v)) = \text{len}(\varepsilon) = 0 = 0 \times \text{len}(v) = \text{len}(\varepsilon) \times \text{len}(v)$.

2. **Inductive Step ($u \mapsto u \cdot \Xi$):** Assume $\text{len}(\text{flatMap}(u, v)) = \text{len}(u) \times \text{len}(v)$. Applying [[#^def-1-3|Definition 1.3]], [[#^thm-1-4|Theorem 1.4]], and distributivity ([[#^thm-1-2|Theorem 1.2]]) yields:

$$
\text{len}(\text{flatMap}(u \cdot \Xi, v)) = \text{len}(\text{flatMap}(u, v) \cdot v) = \text{len}(\text{flatMap}(u, v)) + \text{len}(v) = (\text{len}(u) \times \text{len}(v)) + \text{len}(v) = \text{len}(u \cdot \Xi) \times \text{len}(v)
$$

3. **Semiring Isomorphism Closure:** Combining structural induction on $u$ with the bijective additive isomorphism of [[#^thm-1-5|Theorem 1.5]] and $\text{len}(\Xi) = 1$ proves $(\Sigma^*, \cdot, \text{flatMap}, \varepsilon, \Xi) \cong (\mathbb{N}, +, \times, 0, 1)$.

**Emergent Isomorphism Bridge 1 (Peano Arithmetic and the Commutative Semiring $\mathbb{N}$):** In classical axiomatic mathematics, Peano's postulates and the associative, commutative, and distributive laws of $(\mathbb{N}, +, \times)$ are posited top-down as primitive rules of number manipulation. Here, [[#^thm-1-1|Theorem 1.1]], [[#^thm-1-2|Theorem 1.2]], [[#^thm-1-3|Theorem 1.3]], and [[#^thm-1-6|Theorem 1.6]] reveal that $(\mathbb{N}, +, \times, 0, 1)$ is canonically isomorphic to the free singleton monoid $(\Sigma^*, \cdot, \text{flatMap}, \varepsilon, \Xi)$: addition *is* linear string concatenation, multiplication *is* uniform token substitution, and Peano induction *is* the universal property of an initial algebra.

---

## 1.4 Term Rewriting Euclidean Division ^sec-1-4

Euclidean division and remainder extraction emerge constructively as a terminating term-rewriting system without invoking rational or real inverses.


<br>

##### Definition 1.5: Prefix Subtraction Rewrite Relation ^def-1-5

*Parent Derivation:* [[#^axiom-1-1|Axiom 1.1]], [[#^def-1-1|Definition 1.1]], [[#^def-1-2|Definition 1.2]].

Let $B \in \Sigma^* \setminus \{\varepsilon\}$ be a non-empty divisor word. Define the single-step rewrite relation $\to_{B}$ on state pairs $(w, q) \in \Sigma^* \times \Sigma^*$ (tracking the residual dividend word $w$ and accumulated quotient word $q$) by:

$$
(w \cdot B, \, q) \to_{B} (w, \, q \cdot \Xi)
$$


<br>

##### Theorem 1.7: Strict Termination and Strong Normalization of Prefix Rewriting ^thm-1-7

*Parent Derivation:* [[#^def-1-4|Definition 1.4]], [[#^thm-1-4|Theorem 1.4]], [[#^def-1-5|Definition 1.5]].

For every non-empty divisor $B \in \Sigma^* \setminus \{\varepsilon\}$, the rewrite relation $\to_{B}$ is strictly terminating and strongly normalizing.

*Proof:*

1. **Termination Energy Measure Definition:** Define the integer energy measure $\mu: \Sigma^* \times \Sigma^* \to \mathbb{N}$ by $\mu(w, q) \coloneq \text{len}(w)$.

2. **Strict Monotonic Decrease:** Suppose $(w_{1}, q_{1}) \to_{B} (w_{2}, q_{2})$. By [[#^def-1-5|Definition 1.5]], $w_{1} = w_{2} \cdot B$. Applying [[#^thm-1-4|Theorem 1.4]] yields $\text{len}(w_{1}) = \text{len}(w_{2}) + \text{len}(B)$. Because $B \neq \varepsilon$ implies $\text{len}(B) \ge 1$ by [[#^def-1-4|Definition 1.4]]:

$$
\mu(w_{2}, q_{2}) = \text{len}(w_{2}) = \text{len}(w_{1}) - \text{len}(B) < \text{len}(w_{1}) = \mu(w_{1}, q_{1})
$$

3. **Well-Foundedness Closure:** Because $(\mathbb{N}, <)$ is well-founded with minimum element $0$, no infinite descending chain exists, and every reduction sequence from $(w, \varepsilon)$ terminates in finitely many steps.


<br>

##### Theorem 1.8: Uniqueness of Normal Forms and Euclidean Reconstruction Invariant ^thm-1-8

*Parent Derivation:* [[#^thm-1-1|Theorem 1.1]], [[#^def-1-3|Definition 1.3]], [[#^thm-1-2|Theorem 1.2]], [[#^thm-1-5|Theorem 1.5]], [[#^def-1-5|Definition 1.5]], [[#^thm-1-7|Theorem 1.7]].

For any dividend $w \in \Sigma^*$ and non-empty divisor $B \in \Sigma^* \setminus \{\varepsilon\}$, the reduction sequence starting at $(w, \varepsilon)$ terminates at a unique irreducible normal form $(r, q)$ satisfying:

$$
(w, \varepsilon) \to_{B}^* (r, q)
$$

$$
\text{len}(r) < \text{len}(B)
$$

$$
w = \text{flatMap}(q, B) \cdot r
$$

*Intuition:* Each rewrite step strips one copy of $B$ from the dividend and appends one tally token $\Xi$ to the quotient, preserving the invariant $\text{flatMap}(q_{k}, B) \cdot w_{k} = w$ until the residual word $r$ is strictly shorter than $B$.

*Proof:*

1. **Remainder Bound Verification:** By [[#^thm-1-7|Theorem 1.7]], reduction reaches an irreducible pair $(r, q)$. If $\text{len}(r) \ge \text{len}(B)$, then by [[#^thm-1-5|Theorem 1.5]] there exists $r' \in \Sigma^*$ of length $\text{len}(r) - \text{len}(B)$ such that $r = r' \cdot B$, giving $(r, q) \to_{B} (r', q \cdot \Xi)$ and contradicting irreducibility. Thus $\text{len}(r) < \text{len}(B)$.

2. **Reconstruction Invariant Base Case ($k = 0$ steps):** At step $0$, $(w_{0}, q_{0}) = (w, \varepsilon)$. By [[#^thm-1-2|Theorem 1.2]] and [[#^thm-1-1|Theorem 1.1]], $\text{flatMap}(\varepsilon, B) \cdot w = \varepsilon \cdot w = w$.

3. **Reconstruction Invariant Inductive Step ($k \mapsto k + 1$):** Assume $w = \text{flatMap}(q_{k}, B) \cdot w_{k}$ and $(w_{k}, q_{k}) \to_{B} (w_{k+1}, q_{k+1})$, so $w_{k} = w_{k+1} \cdot B$ and $q_{k+1} = q_{k} \cdot \Xi$. Applying associativity and commutativity of $\cdot$ ([[#^thm-1-1|Theorem 1.1]]) alongside [[#^def-1-3|Definition 1.3]] yields:

$$
w = \text{flatMap}(q_{k}, B) \cdot (w_{k+1} \cdot B) = (\text{flatMap}(q_{k}, B) \cdot B) \cdot w_{k+1} = \text{flatMap}(q_{k} \cdot \Xi, B) \cdot w_{k+1} = \text{flatMap}(q_{k+1}, B) \cdot w_{k+1}
$$

4. **Uniqueness Closure:** At termination, $w = \text{flatMap}(q, B) \cdot r$ with $\text{len}(r) < \text{len}(B)$. By Euclidean uniqueness on $\mathbb{N}$ transported across $\text{len}$ ([[#^thm-1-5|Theorem 1.5]]), $\text{len}(q)$ and $\text{len}(r)$ are uniquely determined, making $(r, q)$ unique.

**Worked Example 2 (Term-Rewriting Division):** Let $w \coloneq \Xi^{7}$ and $B \coloneq \Xi^{3}$. Executing [[#^def-1-5|Definition 1.5]] from $(\Xi^{7}, \varepsilon)$ yields the two-step terminating trace:

$$
(\Xi^{7}, \varepsilon) = (\Xi^{4} \cdot \Xi^{3}, \varepsilon) \to_{\Xi^{3}} (\Xi^{4}, \Xi) = (\Xi \cdot \Xi^{3}, \Xi) \to_{\Xi^{3}} (\Xi, \Xi^{2})
$$

Since $\text{len}(\Xi) = 1 < 3 = \text{len}(\Xi^{3})$, $(\Xi, \Xi^{2})$ is irreducible and satisfies $\text{flatMap}(\Xi^{2}, \Xi^{3}) \cdot \Xi = \Xi^{6} \cdot \Xi = \Xi^{7}$ ($7 = 2 \times 3 + 1$).

**Emergent Isomorphism Bridge 2 (Euclidean Division Algorithm):** Classical arithmetic introduces quotient and remainder via division in $\mathbb{Q}$ or existential ordering axioms. [[#^thm-1-7|Theorem 1.7]] and [[#^thm-1-8|Theorem 1.8]] demonstrate that Euclidean division is a strongly normalizing term-rewriting system whose conserved energy invariant $w = \text{flatMap}(q, B) \cdot r$ operates entirely inside the free monoid $\Sigma^*$.

---

## 1.5 Constructive Ring $\mathbb{Z}$, Rational Field $\mathbb{Q}$, and Archimedean Continuum $\mathbb{R}$ ^sec-1-5

To support subtraction, signed exponents, rational valuations, and Archimedean limits in downstream strata without forward dependencies, we extend $(\Sigma^*, \cdot, \text{flatMap})$ sequentially to the ring of integers $\mathbb{Z}$, the rational field $\mathbb{Q}$, and the complete real field $\mathbb{R}$.


<br>

##### Definition 1.6: Grothendieck Group Completion to the Ring of Integers ^def-1-6

*Parent Derivation:* [[#^thm-1-2|Theorem 1.2]].

Define the equivalence relation $\sim_{+}$ on formal word pairs $\Sigma^* \times \Sigma^*$ by:

$$
(u_{1}, v_{1}) \sim_{+} (u_{2}, v_{2}) \iff u_{1} \cdot v_{2} = u_{2} \cdot v_{1}
$$

The ring of integers is the quotient set $\mathbb{Z} \coloneq (\Sigma^* \times \Sigma^*) / \sim_{+}$, where the equivalence class $[(u, v)]_{+}$ encodes the signed difference $\text{len}(u) - \text{len}(v)$. Define additive identity $0_{\mathbb{Z}} \coloneq [(\varepsilon, \varepsilon)]_{+}$, multiplicative identity $1_{\mathbb{Z}} \coloneq [(\Xi, \varepsilon)]_{+}$, negation $-[(u, v)]_{+} \coloneq [(v, u)]_{+}$, and binary operations:

$$
[(u_{1}, v_{1})]_{+} +_{\mathbb{Z}} [(u_{2}, v_{2})]_{+} \coloneq [(u_{1} \cdot u_{2}, \, v_{1} \cdot v_{2})]_{+}
$$

$$
[(u_{1}, v_{1})]_{+} \times_{\mathbb{Z}} [(u_{2}, v_{2})]_{+} \coloneq [(\text{flatMap}(u_{1}, u_{2}) \cdot \text{flatMap}(v_{1}, v_{2}), \, \text{flatMap}(u_{1}, v_{2}) \cdot \text{flatMap}(v_{1}, u_{2}))]_{+}
$$


<br>

##### Theorem 1.9: Well-Definedness and Commutative Ring Structure of $\mathbb{Z}$ ^thm-1-9

*Parent Derivation:* [[#^thm-1-1|Theorem 1.1]], [[#^thm-1-2|Theorem 1.2]], [[#^thm-1-5|Theorem 1.5]], [[#^def-1-6|Definition 1.6]].

The operations $+_{\mathbb{Z}}$ and $\times_{\mathbb{Z}}$ are independent of representative choices, and $(\mathbb{Z}, +_{\mathbb{Z}}, \times_{\mathbb{Z}}, 0_{\mathbb{Z}}, 1_{\mathbb{Z}})$ is a commutative ring into which $\Sigma^*$ embeds injectively via $w \mapsto [(w, \varepsilon)]_{+}$.

*Proof:*

1. **Equivalence Relation Transitivity:** Reflexivity and symmetry of $\sim_{+}$ follow immediately from [[#^thm-1-1|Theorem 1.1]]. If $(u_{1}, v_{1}) \sim_{+} (u_{2}, v_{2})$ and $(u_{2}, v_{2}) \sim_{+} (u_{3}, v_{3})$, then $u_{1} \cdot v_{2} = u_{2} \cdot v_{1}$ and $u_{2} \cdot v_{3} = u_{3} \cdot v_{2}$. Concatenating gives $(u_{1} \cdot v_{3}) \cdot (u_{2} \cdot v_{2}) = (u_{3} \cdot v_{1}) \cdot (u_{2} \cdot v_{2})$, and cancellativity of addition in $\mathbb{N}$ via [[#^thm-1-5|Theorem 1.5]] yields $u_{1} \cdot v_{3} = u_{3} \cdot v_{1}$.

2. **Representative Independence:** If $(u_{1}, v_{1}) \sim_{+} (u'_{1}, v'_{1})$ and $(u_{2}, v_{2}) \sim_{+} (u'_{2}, v'_{2})$, associativity and commutativity of $\cdot$ ([[#^thm-1-1|Theorem 1.1]]) yield $(u_{1} \cdot u_{2}) \cdot (v'_{1} \cdot v'_{2}) = (u'_{1} \cdot u'_{2}) \cdot (v_{1} \cdot v_{2})$, so $+_{\mathbb{Z}}$ is well-defined. Distributivity of `flatMap` over $\cdot$ ([[#^thm-1-2|Theorem 1.2]]) likewise preserves $\times_{\mathbb{Z}}$ across equivalent pairs.

3. **Ring Axioms and Embedding:** Commutativity, associativity, and distributivity inherit directly from the semiring laws of [[#^thm-1-2|Theorem 1.2]], while $[(u, v)]_{+} +_{\mathbb{Z}} [(v, u)]_{+} = [(u \cdot v, v \cdot u)]_{+} = 0_{\mathbb{Z}}$ supplies additive inverses. Since $[(w_{1}, \varepsilon)]_{+} = [(w_{2}, \varepsilon)]_{+} \iff w_{1} = w_{2}$, the canonical inclusion $\Sigma^* \hookrightarrow \mathbb{Z}$ is injective.


<br>

##### Definition 1.7: Multiplicative Localization to the Field of Fractions $\mathbb{Q}$ ^def-1-7

*Parent Derivation:* [[#^def-1-6|Definition 1.6]], [[#^thm-1-9|Theorem 1.9]].

Define the equivalence relation $\sim_{\times}$ on $\mathbb{Z} \times (\mathbb{Z} \setminus \{0_{\mathbb{Z}}\})$ by:

$$
(a_{1}, b_{1}) \sim_{\times} (a_{2}, b_{2}) \iff a_{1} \times_{\mathbb{Z}} b_{2} = a_{2} \times_{\mathbb{Z}} b_{1}
$$

The field of rational numbers is the quotient $\mathbb{Q} \coloneq (\mathbb{Z} \times (\mathbb{Z} \setminus \{0_{\mathbb{Z}}\})) / \sim_{\times}$, with zero $0_{\mathbb{Q}} \coloneq [(0_{\mathbb{Z}}, 1_{\mathbb{Z}})]_{\times}$, unit $1_{\mathbb{Q}} \coloneq [(1_{\mathbb{Z}}, 1_{\mathbb{Z}})]_{\times}$, and operations:

$$
[(a_{1}, b_{1})]_{\times} +_{\mathbb{Q}} [(a_{2}, b_{2})]_{\times} \coloneq [((a_{1} \times_{\mathbb{Z}} b_{2}) +_{\mathbb{Z}} (a_{2} \times_{\mathbb{Z}} b_{1}), \, b_{1} \times_{\mathbb{Z}} b_{2})]_{\times}
$$

$$
[(a_{1}, b_{1})]_{\times} \times_{\mathbb{Q}} [(a_{2}, b_{2})]_{\times} \coloneq [(a_{1} \times_{\mathbb{Z}} a_{2}, \, b_{1} \times_{\mathbb{Z}} b_{2})]_{\times}
$$


<br>

##### Theorem 1.10: Well-Definedness and Field Structure of $\mathbb{Q}$ ^thm-1-10

*Parent Derivation:* [[#^thm-1-2|Theorem 1.2]], [[#^def-1-7|Definition 1.7]], [[#^thm-1-9|Theorem 1.9]].

The operations $+_{\mathbb{Q}}$ and $\times_{\mathbb{Q}}$ are well-defined, and $(\mathbb{Q}, +_{\mathbb{Q}}, \times_{\mathbb{Q}}, 0_{\mathbb{Q}}, 1_{\mathbb{Q}})$ is a field into which $\mathbb{Z}$ embeds injectively via $a \mapsto [(a, 1_{\mathbb{Z}})]_{\times}$.

*Proof:*

1. **Integral Domain Closure:** Because $(\Sigma^*, \text{flatMap})$ has no zero divisors ([[#^thm-1-2|Theorem 1.2]]), [[#^thm-1-9|Theorem 1.9]] implies $b_{1} \neq 0_{\mathbb{Z}}$ and $b_{2} \neq 0_{\mathbb{Z}}$ force $b_{1} \times_{\mathbb{Z}} b_{2} \neq 0_{\mathbb{Z}}$, keeping denominators inside $\mathbb{Z} \setminus \{0_{\mathbb{Z}}\}$.

2. **Representative Independence and Field Axioms:** Cancellativity of non-zero multiplication in $\mathbb{Z}$ guarantees transitivity of $\sim_{\times}$ and invariance of $+_{\mathbb{Q}}$ and $\times_{\mathbb{Q}}$ under representative substitution. Ring laws follow from [[#^thm-1-9|Theorem 1.9]], and every non-zero element $[(a, b)]_{\times}$ ($a \neq 0_{\mathbb{Z}}$) possesses the multiplicative inverse $[(b, a)]_{\times}$ since $[(a, b)]_{\times} \times_{\mathbb{Q}} [(b, a)]_{\times} = [(a \times_{\mathbb{Z}} b, b \times_{\mathbb{Z}} a)]_{\times} = 1_{\mathbb{Q}}$.


<br>

##### Definition 1.8: Archimedean Absolute Value and Cauchy Real Completion $\mathbb{R}$ ^def-1-8

*Parent Derivation:* [[#^thm-1-5|Theorem 1.5]], [[#^def-1-6|Definition 1.6]], [[#^def-1-7|Definition 1.7]], [[#^thm-1-10|Theorem 1.10]].

For any integer $z = [(u, v)]_{+} \in \mathbb{Z}$, total ordering of $\mathbb{N}$ ([[#^thm-1-5|Theorem 1.5]]) determines a unique scalar magnitude $\lvert z \rvert \in \mathbb{N}$ via $\text{len}(u) = \text{len}(v) + \lvert z \rvert$ when $\text{len}(u) \ge \text{len}(v)$ and $\text{len}(v) = \text{len}(u) + \lvert z \rvert$ when $\text{len}(v) > \text{len}(u)$. Define the Archimedean absolute value $\lvert \cdot \rvert_{\infty}: \mathbb{Q} \to \mathbb{Q}_{\ge 0}$ by:

$$
\left\lvert [(a, b)]_{\times} \right\rvert_{\infty} \coloneq [(\lvert a \rvert, \lvert b \rvert)]_{\times}
$$

Let $\mathcal{C}_{\mathbb{Q}}$ denote the commutative ring of Cauchy sequences $(q_{n})_{n=1}^{\infty}$ in $(\mathbb{Q}, \lvert \cdot \rvert_{\infty})$ (satisfying $\forall \epsilon \in \mathbb{Q}_{> 0}, \, \exists N \in \mathbb{N}_{\ge 1}$ such that $\forall m, n \ge N, \, \lvert q_{m} - q_{n} \rvert_{\infty} < \epsilon$) and let $\mathcal{N}_{\mathbb{Q}} \subset \mathcal{C}_{\mathbb{Q}}$ denote the maximal ideal of null sequences ($\lim_{n \to \infty} \lvert q_{n} \rvert_{\infty} = 0_{\mathbb{Q}}$). Define the field of real numbers as the metric completion quotient:

$$
\mathbb{R} \coloneq \overline{\mathbb{Q}}_{\lvert \cdot \rvert_{\infty}} \coloneq \mathcal{C}_{\mathbb{Q}} / \mathcal{N}_{\mathbb{Q}}
$$


<br>

##### Theorem 1.11: Completeness of $\mathbb{R}$ and Exponential-Logarithmic Functions ^thm-1-11

*Parent Derivation:* [[#^thm-1-10|Theorem 1.10]], [[#^def-1-8|Definition 1.8]].

The quotient $(\mathbb{R}, +, \times, 0, 1, \lvert \cdot \rvert_{\infty})$ is a complete Archimedean ordered field into which $\mathbb{Q}$ embeds densely via $q \mapsto [(q)_{n=1}^{\infty}]$, admitting unique continuous mutually inverse exponential and logarithmic maps $\exp: \mathbb{R} \xrightarrow{\cong} \mathbb{R}_{> 0}$ and $\ln: \mathbb{R}_{> 0} \xrightarrow{\cong} \mathbb{R}$ (with base-$2$ logarithm $\log_{2}(x) \coloneq \ln(x) / \ln(2)$) defined independently of prime numbers.

*Proof:*

1. **Field and Metric Completeness:** Because $\mathcal{N}_{\mathbb{Q}}$ is a maximal ideal in $\mathcal{C}_{\mathbb{Q}}$ (any non-null Cauchy sequence is eventually bounded away from $0_{\mathbb{Q}}$ and hence invertible modulo $\mathcal{N}_{\mathbb{Q}}$), $\mathbb{R}$ is an ordered field containing $\mathbb{Q}$ as a dense subfield, and diagonalization over Cauchy sequences of Cauchy sequences proves every Cauchy sequence in $\mathbb{R}$ converges in $\mathbb{R}$.

2. **Analytic Exponential and Logarithm:** By completeness of $\mathbb{R}$, the power series $\exp(x) \coloneq \sum_{n=0}^{\infty} x^{n} / n!$ converges absolutely for all $x \in \mathbb{R}$, satisfies $\exp(x + y) = \exp(x)\exp(y)$ with $\exp'(x) = \exp(x) > 0$, and maps $\mathbb{R}$ homeomorphically onto $\mathbb{R}_{> 0}$, defining its continuous inverse $\ln: \mathbb{R}_{> 0} \xrightarrow{\cong} \mathbb{R}$ and $\log_{2}(x) \coloneq \ln(x) / \ln(2)$ prior to any prime-number construction.

*Exit Handoff:* We have constructed the complete numerical hierarchy $(\mathbb{N}, \mathbb{Z}, \mathbb{Q}, \mathbb{R})$ and terminating Euclidean division from $\Sigma = \{\Xi\}$ without circularity. However, unary words require $O(N)$ storage space and sequential carry propagation—motivating prime factorization and parallel modular channels in Section 2.

---

---

# Section 2: Number Theory as Information Theory — Prime Sieve, CRT, and Orthogonal Channels ^sec-2

*Entry Primer:* Unary words represent quantities transparently, but they scale linearly in length ($O(N)$ storage) and couple carries sequentially across tokens. How do we decompose arbitrary words into irreducible multiplicative atoms and project large integers onto parallel, statistically independent coordinates? In this section, we construct the prime sieve purely via word substitution, prove unique prime word factorization, and show that the Chinese Remainder Theorem is identical to Shannon channel orthogonality.

## 2.1 Unary String Divisibility, Prime Sieve, and Unique Factorization ^sec-2-1

Having established the constructive semiring $(\Sigma^*, \cdot, \text{flatMap}, \varepsilon, \Xi)$ and terminating Euclidean reduction in Section 1, we now define divisibility and primality purely in terms of endomorphic word substitution.


<br>

##### Definition 2.1: Unary String Divisibility Predicate ^def-2-1

*Parent Derivation:* [[#^def-1-1|Definition 1.1]], [[#^def-1-3|Definition 1.3]].

For any two non-empty words $u, v \in \Sigma^* \setminus \{\varepsilon\}$, define the unary divisibility predicate $u \mid_{\Sigma} v$ via the substitution endomorphism $\text{flatMap}$:

$$
u \mid_{\Sigma} v \iff \exists w \in \Sigma^* \setminus \{\varepsilon\} \quad \text{s.t.} \quad \text{flatMap}(w, u) = v
$$


<br>

##### Theorem 2.1: Homomorphic Equivalence to Natural Divisibility ^thm-2-1

*Parent Derivation:* [[#^thm-1-5|Theorem 1.5]], [[#^thm-1-6|Theorem 1.6]], [[#^def-2-1|Definition 2.1]].

Unary string divisibility is logically equivalent to integer divisibility of word lengths in $\mathbb{N}$:

$$
\forall u, v \in \Sigma^* \setminus \{\varepsilon\}, \quad u \mid_{\Sigma} v \iff \text{len}(u) \mid \text{len}(v)
$$

*Proof:*

1. **Forward Implication ($\implies$):** Assume $u \mid_{\Sigma} v$. By [[#^def-2-1|Definition 2.1]], there exists $w \in \Sigma^* \setminus \{\varepsilon\}$ such that $\text{flatMap}(w, u) = v$. Applying the multiplicative length homomorphism of [[#^thm-1-6|Theorem 1.6]] gives $\text{len}(v) = \text{len}(\text{flatMap}(w, u)) = \text{len}(w) \times \text{len}(u)$ with $\text{len}(w) \in \mathbb{N}_{\ge 1}$, establishing $\text{len}(u) \mid \text{len}(v)$.

2. **Reverse Implication ($\impliedby$):** Assume $\text{len}(u) \mid \text{len}(v)$. There exists $k \in \mathbb{N}_{\ge 1}$ such that $\text{len}(v) = k \times \text{len}(u)$. By surjectivity of $\text{len}$ ([[#^thm-1-5|Theorem 1.5]]), construct the canonical word $w \coloneq \Xi^{k} \in \Sigma^* \setminus \{\varepsilon\}$ satisfying $\text{len}(w) = k$.

3. **Isomorphic Reconstruction:** Evaluating lengths via [[#^thm-1-6|Theorem 1.6]] yields $\text{len}(\text{flatMap}(\Xi^{k}, u)) = k \times \text{len}(u) = \text{len}(v)$. By injectivity of $\text{len}$ ([[#^thm-1-5|Theorem 1.5]]), $\text{flatMap}(\Xi^{k}, u) = v$, confirming $u \mid_{\Sigma} v$.


<br>

##### Definition 2.2: Constructive Prime Predicate and Prime Set ^def-2-2

*Parent Derivation:* [[#^axiom-1-1|Axiom 1.1]], [[#^def-1-4|Definition 1.4]], [[#^def-2-1|Definition 2.1]].

A word $p \in \Sigma^*$ is prime if it contains at least two tokens and admits only trivial unary divisors in $\Sigma^* \setminus \{\varepsilon\}$; denote the set of all prime words by $\mathcal{P}$:

$$
\mathcal{Prime}(p) \iff (\text{len}(p) \ge 2) \land \forall d \in \Sigma^* \setminus \{\varepsilon\} \left[ d \mid_{\Sigma} p \implies (d = \Xi \lor d = p) \right]
$$

$$
\mathcal{P} \coloneq \{ p \in \Sigma^* \mid \mathcal{Prime}(p) \}
$$


<br>

##### Lemma 2.2a: Primality of Length-Minimal Non-Trivial Divisors ^lem-2-2a

*Parent Derivation:* [[#^thm-1-2|Theorem 1.2]], [[#^thm-1-5|Theorem 1.5]], [[#^def-2-1|Definition 2.1]], [[#^def-2-2|Definition 2.2]].

For every word $W \in \Sigma^*$ with $\text{len}(W) \ge 2$, the non-trivial divisor set $D(W) \coloneq \{d \in \Sigma^* \mid \text{len}(d) \ge 2 \land d \mid_{\Sigma} W\}$ contains a unique length-minimal element $w^* \coloneq \min_{<} D(W)$ under the strict length order $u < v \iff \text{len}(u) < \text{len}(v)$, and $\mathcal{Prime}(w^*)$ holds.

*Proof:*

1. **Non-Emptiness and Well-Ordering:** By the multiplicative unit law $\text{flatMap}(\Xi, W) = W$ of [[#^thm-1-2|Theorem 1.2]], $W \mid_{\Sigma} W$ holds, so $W \in D(W)$ and $D(W)$ is non-empty. Because $(\mathbb{N}, <)$ is well-ordered and $\text{len}$ is a bijection ([[#^thm-1-5|Theorem 1.5]]), $w^* \coloneq \min_{<} D(W)$ exists uniquely.

2. **Transitivity of Unary Divisibility:** Suppose $c \in \Sigma^* \setminus \{\varepsilon\}$ satisfies $c \mid_{\Sigma} w^*$ with $c \neq \Xi$ and $c \neq w^*$. By [[#^def-2-1|Definition 2.1]], there exist $u, v \in \Sigma^* \setminus \{\varepsilon\}$ such that $\text{flatMap}(u, c) = w^*$ and $\text{flatMap}(v, w^*) = W$.

3. **Contradiction via Minimality:** By associativity of $\text{flatMap}$ ([[#^thm-1-2|Theorem 1.2]]), we have:

$$
\text{flatMap}(\text{flatMap}(v, u), c) = \text{flatMap}(v, \text{flatMap}(u, c)) = \text{flatMap}(v, w^*) = W
$$

Hence $c \mid_{\Sigma} W$ with $2 \le \text{len}(c) < \text{len}(w^*)$, contradicting the minimality of $w^*$ in $D(W)$. By [[#^def-2-2|Definition 2.2]], $\mathcal{Prime}(w^*)$ holds.


<br>

##### Theorem 2.2: Unboundedness and Infinitude of the Prime Set ^thm-2-2

*Parent Derivation:* [[#^thm-1-2|Theorem 1.2]], [[#^thm-1-4|Theorem 1.4]], [[#^thm-1-6|Theorem 1.6]], [[#^thm-1-8|Theorem 1.8]], [[#^def-2-2|Definition 2.2]], [[#^lem-2-2a|Lemma 2.2a]].

The prime set $\mathcal{P}$ of [[#^def-2-2|Definition 2.2]] is non-empty and unbounded in word length: for every finite non-empty subset $\{q_{1}, \dots, q_{k}\} \subset \mathcal{P}$, there exists a prime word $w^* \in \mathcal{P}$ strictly longer than every $q_{i}$ ($\forall i \in \{1, \dots, k\}, \, \text{len}(w^*) > \text{len}(q_{i})$).

*Intuition:* Multiplying any finite collection of primes together via iterated `flatMap` and appending one tally token $\Xi$ produces a word whose Euclidean division by each listed prime leaves remainder $\Xi$, forcing its minimal prime divisor to be a strictly new prime.

*Proof:*

1. **Base Witness and Euclid Accumulator Construction:** The word $\Xi^{2}$ has no divisors of length strictly between $1$ and $2$, so $\Xi^{2} \in \mathcal{P}$. Given any finite non-empty subset $\{q_{1}, \dots, q_{k}\} \subset \mathcal{P}$, define the iterated substitution product $A_{k} \coloneq \text{flatMap}(q_{1}, \text{flatMap}(q_{2}, \dots, q_{k}))$ and form the accumulator $W_{k} \coloneq A_{k} \cdot \Xi$. By [[#^thm-1-4|Theorem 1.4]] and [[#^thm-1-6|Theorem 1.6]], $\text{len}(W_{k}) = \left(\prod_{i=1}^{k} \text{len}(q_{i})\right) + 1 > \max_{1 \le i \le k} \text{len}(q_{i}) \ge 2$.

2. **Non-Divisibility by Listed Primes:** For each $i \in \{1, \dots, k\}$, associativity and commutativity of $\text{flatMap}$ ([[#^thm-1-2|Theorem 1.2]]) yield $A_{k} = \text{flatMap}(c_{i}, q_{i})$ for a cofactor $c_{i} \in \Sigma^* \setminus \{\varepsilon\}$, so $W_{k} = \text{flatMap}(c_{i}, q_{i}) \cdot \Xi$. Because $\text{len}(\Xi) = 1 < 2 \le \text{len}(q_{i})$, uniqueness of Euclidean normal forms ([[#^thm-1-8|Theorem 1.8]]) forces $(W_{k}, \varepsilon) \to_{q_{i}}^* (\Xi, c_{i})$ with non-empty remainder $\Xi \neq \varepsilon$, proving $q_{i} \nmid_{\Sigma} W_{k}$.

3. **Minimal Prime Extraction:** By [[#^lem-2-2a|Lemma 2.2a]], the length-minimal non-trivial divisor $w^* \mid_{\Sigma} W_{k}$ satisfies $w^* \in \mathcal{P}$. Because $w^* \mid_{\Sigma} W_{k}$ while $q_{i} \nmid_{\Sigma} W_{k}$ for all $i \in \{1, \dots, k\}$, we have $w^* \notin \{q_{1}, \dots, q_{k}\}$, establishing that $\mathcal{P}$ is infinite and unbounded in length.


<br>

##### Definition 2.3: Constructive Prime Sequence ^def-2-3

*Parent Derivation:* [[#^def-1-4|Definition 1.4]], [[#^def-2-2|Definition 2.2]], [[#^thm-2-2|Theorem 2.2]].

Equip $\Sigma^*$ with the strict length order $u < v \iff \text{len}(u) < \text{len}(v)$. By [[#^thm-2-2|Theorem 2.2]], the set $\{w \in \mathcal{P} \mid \text{len}(w) > \text{len}(p_{k})\}$ is guaranteed non-empty for every $k \in \mathbb{N}_{\ge 1}$, defining the infinite prime sequence $\mathcal{P} = \{p_{1}, p_{2}, p_{3}, \dots\}$ recursively by minimal successor search:

$$
p_{1} \coloneq \Xi^{2}
$$

$$
p_{k+1} \coloneq \min_{<} \left\{ w \in \mathcal{P} \;\middle\vert{}\; \text{len}(w) > \text{len}(p_{k}) \right\}
$$

Consequently, $\text{len}(p_{k}) < \text{len}(p_{k+1})$ holds strictly for all $k \in \mathbb{N}_{\ge 1}$.


<br>

##### Theorem 2.2b: Fundamental Theorem of Unary Word Arithmetic ^thm-2-2b

*Parent Derivation:* [[#^thm-1-2|Theorem 1.2]], [[#^thm-1-5|Theorem 1.5]], [[#^thm-1-9|Theorem 1.9]], [[#^thm-1-10|Theorem 1.10]], [[#^thm-1-11|Theorem 1.11]], [[#^thm-2-1|Theorem 2.1]], [[#^lem-2-2a|Lemma 2.2a]], [[#^def-2-3|Definition 2.3]].

Every word $w \in \Sigma^*$ with $\text{len}(w) \ge 2$ admits a unique prime word decomposition under iterated $\text{flatMap}$ (written $w = \prod_{i=1}^{m} p_{i}^{e_{i}}$ with $p_{i} \in \mathcal{P}$, $e_{i} \in \mathbb{N}_{\ge 1}$, and $\text{len}(p_{1}) < \dots < \text{len}(p_{m})$), and for every non-zero rational $q = [(a, b)]_{\times} \in \mathbb{Q}^\times$ in lowest terms, the negative $p$-adic support $\operatorname{supp}_{\mathcal{P}}^{-}(q) \coloneq \{p \in \mathcal{P} \mid v_{p}(q) < 0\}$ is strictly finite.

*Proof:*

1. **Existence via Minimal Divisor Extraction:** Proceed by strong induction on $\text{len}(w) \ge 2$. By [[#^lem-2-2a|Lemma 2.2a]], $w$ admits a length-minimal prime divisor $p \in \mathcal{P}$ with $w = \text{flatMap}(u, p)$. If $u = \Xi$, then $w = p$; if $\text{len}(u) \ge 2$, then $\text{len}(u) < \text{len}(w)$ and the induction hypothesis factors $u$ into primes, yielding a prime decomposition for $w$.

2. **Euclid's Primality Lemma on $\Sigma^*$:** Suppose $p \in \mathcal{P}$ satisfies $p \mid_{\Sigma} \text{flatMap}(u, v)$ for $u, v \in \Sigma^* \setminus \{\varepsilon\}$, and assume $p \nmid_{\Sigma} u$. Because $\mathcal{Prime}(p)$ holds ([[#^def-2-2|Definition 2.2]]), $\gcd(\text{len}(p), \text{len}(u)) = 1$, so Bézout's identity in $\mathbb{Z}$ ([[#^thm-1-9|Theorem 1.9]]) provides $x, y \in \mathbb{Z}$ with $x \text{len}(p) + y \text{len}(u) = 1$. Multiplying by $\text{len}(v)$ gives $x \text{len}(p)\text{len}(v) + y \text{len}(\text{flatMap}(u, v)) = \text{len}(v)$; since $\text{len}(p) \mid \text{len}(\text{flatMap}(u, v))$ by [[#^thm-2-1|Theorem 2.1]], we obtain $\text{len}(p) \mid \text{len}(v)$ and thus $p \mid_{\Sigma} v$.

3. **Uniqueness and Finite Rational Support:** If $\prod_{i=1}^{m} p_{i}^{e_{i}} = \prod_{j=1}^{n} q_{j}^{f_{j}}$, Step 2 forces $p_{1} \mid_{\Sigma} q_{j}$ for some $j$, hence $p_{1} = q_{j}$ by [[#^def-2-2|Definition 2.2]], and cancellativity of `flatMap` ([[#^thm-1-5|Theorem 1.5]]) completes uniqueness by induction on $\text{len}(w)$. Writing $q \in \mathbb{Q}^\times$ as $\pm \prod_{p \in \mathcal{P}} \text{len}(p)^{v_{p}(q)}$ ($v_{p}(q) \in \mathbb{Z}$), negative valuations $v_{p}(q) < 0$ occur only at primes dividing the denominator magnitude $\lvert b \rvert \ge 1$, bounding $\lvert \operatorname{supp}_{\mathcal{P}}^{-}(q) \rvert \le \log_{2} \lvert b \rvert < \infty$ via [[#^thm-1-11|Theorem 1.11]].

---

## 2.2 Primorial Moduli, Pairwise Coprimality, and CRT Ring Isomorphism ^sec-2-2


<br>

##### Definition 2.4: Primorial Base Word and Scalar Magnitude ^def-2-4

*Parent Derivation:* [[#^def-1-3|Definition 1.3]], [[#^thm-1-6|Theorem 1.6]], [[#^def-2-3|Definition 2.3]].

For each index $k \in \mathbb{N}_{\ge 1}$, define the $k$-th primorial base word $P_{k} \in \Sigma^*$ recursively via substitution and denote its natural scalar magnitude by $N_{k} \coloneq \text{len}(P_{k})$:

$$
P_{1} \coloneq p_{1}, \qquad P_{k} \coloneq \text{flatMap}(P_{k-1}, p_{k}) \quad (k \ge 2)
$$

$$
N_{k} \coloneq \text{len}(P_{k}) = \prod_{i=1}^{k} \text{len}(p_{i})
$$


<br>

##### Theorem 2.3: Pairwise Coprimality of Prime Moduli ^thm-2-3

*Parent Derivation:* [[#^def-2-2|Definition 2.2]], [[#^thm-2-1|Theorem 2.1]], [[#^def-2-3|Definition 2.3]].

Distinct prime words in $\mathcal{P}$ have pairwise coprime lengths:

$$
\forall i, j \in \mathbb{N}_{\ge 1}, \quad i \neq j \implies \gcd(\text{len}(p_{i}), \text{len}(p_{j})) = 1
$$

*Proof:*

1. **Order Normalization:** Without loss of generality, assume $i < j$. By [[#^def-2-3|Definition 2.3]], $\text{len}(p_{i}) < \text{len}(p_{j})$.

2. **Common Divisor Projection:** Let $d \coloneq \gcd(\text{len}(p_{i}), \text{len}(p_{j})) \in \mathbb{N}_{\ge 1}$. Since $d \mid \text{len}(p_{i})$ and $d \mid \text{len}(p_{j})$, [[#^thm-2-1|Theorem 2.1]] implies $\Xi^{d} \mid_{\Sigma} p_{i}$ and $\Xi^{d} \mid_{\Sigma} p_{j}$.

3. **Primality Dichotomy:** Because $\mathcal{Prime}(p_{i})$ holds ([[#^def-2-2|Definition 2.2]]), $\Xi^{d} \in \{\Xi, p_{i}\}$, forcing $d = 1$ or $d = \text{len}(p_{i})$. If $d = \text{len}(p_{i})$, then $p_{i} \mid_{\Sigma} p_{j}$ with $2 \le \text{len}(p_{i}) < \text{len}(p_{j})$, contradicting $\mathcal{Prime}(p_{j})$. Therefore $d = 1$.


<br>

##### Definition 2.5: Canonical CRT Residue Evaluation Map ^def-2-5

*Parent Derivation:* [[#^def-1-6|Definition 1.6]], [[#^thm-1-9|Theorem 1.9]], [[#^def-2-4|Definition 2.4]].

For each $k \in \mathbb{N}_{\ge 1}$, define the canonical residue evaluation map $\Psi_{k}$ from the primorial quotient ring $\mathbb{Z}/N_{k}\mathbb{Z}$ to the direct product of prime residue fields $\prod_{i=1}^{k} (\mathbb{Z}/\text{len}(p_{i})\mathbb{Z})$ by:

$$
\Psi_{k}: \mathbb{Z} / N_{k}\mathbb{Z} \to \prod_{i=1}^{k} \left( \mathbb{Z} / \text{len}(p_{i})\mathbb{Z} \right)
$$

$$
\Psi_{k}(x \bmod N_{k}) \coloneq \left( x \bmod \text{len}(p_{1}), \, x \bmod \text{len}(p_{2}), \, \dots, \, x \bmod \text{len}(p_{k}) \right)
$$


<br>

##### Theorem 2.4: Chinese Remainder Theorem Ring Isomorphism ^thm-2-4

*Parent Derivation:* [[#^thm-1-9|Theorem 1.9]], [[#^def-2-4|Definition 2.4]], [[#^thm-2-3|Theorem 2.3]], [[#^def-2-5|Definition 2.5]].

For every $k \in \mathbb{N}_{\ge 1}$, the residue evaluation map $\Psi_{k}$ is a bijective isomorphism of commutative rings:

$$
\mathbb{Z} / N_{k}\mathbb{Z} \cong \prod_{i=1}^{k} \left( \mathbb{Z} / \text{len}(p_{i})\mathbb{Z} \right)
$$

*Intuition:* Because distinct prime moduli share no common factors, an integer modulo $N_{k}$ vanishes modulo every prime $p_{i}$ ($1 \le i \le k$) if and only if it is divisible by their product $N_{k}$, forcing the ring homomorphism $\Psi_{k}$ to be injective between finite sets of identical size $N_{k}$.

*Proof:*

1. **Ring Homomorphism Preservation:** Because $\text{len}(p_{i}) \mid N_{k}$ for every $i \in \{1, \dots, k\}$ ([[#^def-2-4|Definition 2.4]]), residue reduction modulo $\text{len}(p_{i})$ is well-defined on $\mathbb{Z}/N_{k}\mathbb{Z}$. By the ring laws of [[#^thm-1-9|Theorem 1.9]], $\Psi_{k}$ preserves addition, multiplication, and the multiplicative unit $(1 \bmod \text{len}(p_{i}))_{i=1}^{k}$ component-wise.

2. **Injectivity via Coprime Kernel Vanishing:** Suppose $\Psi_{k}(x \bmod N_{k}) = (0, 0, \dots, 0)$, so $\text{len}(p_{i}) \mid x$ for all $i \in \{1, \dots, k\}$. Because the prime moduli $\{\text{len}(p_{i})\}_{i=1}^{k}$ are pairwise coprime by [[#^thm-2-3|Theorem 2.3]], their least common multiple equals their product: $\operatorname{lcm}(\text{len}(p_{1}), \dots, \text{len}(p_{k})) = \prod_{i=1}^{k} \text{len}(p_{i}) = N_{k}$. Thus $N_{k} \mid x$, proving $\ker(\Psi_{k}) = \{0 \bmod N_{k}\}$ and establishing injectivity.

3. **Surjectivity via Finite Cardinality Equality:** Comparing the cardinalities of the finite domain and codomain gives:

$$
\lvert \mathbb{Z} / N_{k}\mathbb{Z} \rvert = N_{k} = \prod_{i=1}^{k} \text{len}(p_{i}) = \left\lvert \prod_{i=1}^{k} \left( \mathbb{Z} / \text{len}(p_{i})\mathbb{Z} \right) \right\rvert
$$

By the Pigeonhole Principle, an injective map between finite sets of identical cardinality is necessarily surjective, proving $\Psi_{k}$ is a ring isomorphism.

**Worked Example 3 (Stage $k = 2$ Primorial CRT Bijection):** At $k = 2$, $p_{1} = \Xi^{2}$ ($\text{len}(p_{1}) = 2$), $p_{2} = \Xi^{3}$ ($\text{len}(p_{2}) = 3$), and $N_{2} = 6$. The evaluation map $\Psi_{2}: \mathbb{Z}/6\mathbb{Z} \xrightarrow{\cong} \mathbb{Z}/2\mathbb{Z} \times \mathbb{Z}/3\mathbb{Z}$ establishes the exact one-to-one correspondence:

| Element $x \in \mathbb{Z}/6\mathbb{Z}$ | Binary Residue $x \bmod 2$ | Ternary Residue $x \bmod 3$ | Image $\Psi_{2}(x \bmod 6)$ |
| :--- | :--- | :--- | :--- |
| $0$ | $0$ | $0$ | $(0, 0)$ |
| $1$ | $1$ | $1$ | $(1, 1)$ |
| $2$ | $0$ | $2$ | $(0, 2)$ |
| $3$ | $1$ | $0$ | $(1, 0)$ |
| $4$ | $0$ | $1$ | $(0, 1)$ |
| $5$ | $1$ | $2$ | $(1, 2)$ |

---

## 2.3 Residue Probability Spaces and Complete Channel Independence ^sec-2-3


<br>

##### Definition 2.6: Finite Residue Probability Space ^def-2-6

*Parent Derivation:* [[#^def-1-6|Definition 1.6]], [[#^def-1-7|Definition 1.7]], [[#^def-2-4|Definition 2.4]].

For any primorial stage $k \in \mathbb{N}_{\ge 1}$, let $\Omega_{k} \coloneq \mathbb{Z}/N_{k}\mathbb{Z} \cong \{0, 1, \dots, N_{k} - 1\}$ equipped with the discrete power-set $\sigma$-algebra $\mathcal{F}_{k} \coloneq \mathcal{P}(\Omega_{k})$ and the normalized discrete Haar probability measure $\mathbb{P}_{k}: \mathcal{F}_{k} \to \mathbb{Q}_{\ge 0}$:

$$
\forall A \subseteq \Omega_{k}, \quad \mathbb{P}_{k}(A) \coloneq \frac{\lvert A \rvert}{\lvert \Omega_{k} \rvert} = \frac{\lvert A \rvert}{N_{k}}
$$


<br>

##### Definition 2.7: Coordinate Projection Random Variables ^def-2-7

*Parent Derivation:* [[#^def-2-5|Definition 2.5]], [[#^def-2-6|Definition 2.6]].

For each prime channel index $i \in \{1, \dots, k\}$, define the coordinate projection random variable $X_{i}: \Omega_{k} \to \mathbb{Z}/\text{len}(p_{i})\mathbb{Z}$ as the $i$-th component of $\Psi_{k}$:

$$
X_{i}(\omega) \coloneq \omega \bmod \text{len}(p_{i})
$$


<br>

##### Theorem 2.5: Marginal Uniformity of Prime Channels ^thm-2-5

*Parent Derivation:* [[#^thm-2-4|Theorem 2.4]], [[#^def-2-6|Definition 2.6]], [[#^def-2-7|Definition 2.7]].

Under the uniform residue measure $\mathbb{P}_{k}$, every prime channel $X_{i}$ is uniformly distributed over its residue alphabet:

$$
\forall i \in \{1, \dots, k\}, \quad \forall r_{i} \in \{0, 1, \dots, \text{len}(p_{i}) - 1\}, \quad \mathbb{P}_{k}(X_{i} = r_{i}) = \frac{1}{\text{len}(p_{i})}
$$

*Proof:*

1. **CRT Pushforward Measure:** By [[#^thm-2-4|Theorem 2.4]], $\Psi_{k}: \Omega_{k} \xrightarrow{\cong} \prod_{j=1}^{k} (\mathbb{Z}/\text{len}(p_{j})\mathbb{Z})$ is a bijection. Since [[#^def-2-6|Definition 2.6]] assigns uniform weight $1/N_{k}$ to each $\omega \in \Omega_{k}$, the pushforward measure $(\Psi_{k})_{*}\mathbb{P}_{k}$ assigns weight $1/N_{k}$ to every $k$-tuple $(r_{1}, \dots, r_{k})$.

2. **Marginal Fiber Counting:** The event $\{X_{i} = r_{i}\}$ ([[#^def-2-7|Definition 2.7]]) maps under $\Psi_{k}$ to the cylinder set fixing coordinate $i$ at $r_{i}$ while allowing all remaining $k - 1$ coordinates to range freely, giving exact cardinality $\prod_{j \neq i} \text{len}(p_{j}) = N_{k} / \text{len}(p_{i})$.

3. **Marginal Probability Evaluation:** Applying [[#^def-2-6|Definition 2.6]] yields $\mathbb{P}_{k}(X_{i} = r_{i}) = \frac{N_{k} / \text{len}(p_{i})}{N_{k}} = \frac{1}{\text{len}(p_{i})}$.


<br>

##### Theorem 2.6: Complete Mutual Independence of Prime Channels ^thm-2-6

*Parent Derivation:* [[#^thm-2-4|Theorem 2.4]], [[#^thm-2-5|Theorem 2.5]].

For any subset of distinct prime channel indices $\{i_{1}, i_{2}, \dots, i_{m}\} \subseteq \{1, \dots, k\}$ and any choice of residues $r_{i_{s}} \in \{0, \dots, \text{len}(p_{i_{s}}) - 1\}$, the coordinate projections factorize completely:

$$
\mathbb{P}_{k}\left( \bigcap_{s=1}^{m} \left\{X_{i_{s}} = r_{i_{s}}\right\} \right) = \prod_{s=1}^{m} \mathbb{P}_{k}(X_{i_{s}} = r_{i_{s}}) = \prod_{s=1}^{m} \frac{1}{\text{len}(p_{i_{s}})}
$$

In particular, for every pair of distinct channels $i \neq j$, $\mathbb{P}_{k}(X_{i} = r_{i}, X_{j} = r_{j}) = \mathbb{P}_{k}(X_{i} = r_{i}) \cdot \mathbb{P}_{k}(X_{j} = r_{j})$.

*Proof:*

1. **Joint Cylinder Cardinality:** Under the CRT bijection $\Psi_{k}$ of [[#^thm-2-4|Theorem 2.4]], constraining the $m$ distinct coordinates $\{i_{1}, \dots, i_{m}\}$ to values $(r_{i_{1}}, \dots, r_{i_{m}})$ leaves the complementary $k - m$ coordinates unconstrained, defining a pre-image fiber of exact size $\prod_{j \notin \{i_{1}, \dots, i_{m}\}} \text{len}(p_{j}) = N_{k} / \prod_{s=1}^{m} \text{len}(p_{i_{s}})$.

2. **Joint Probability Evaluation:** Dividing the fiber cardinality by $N_{k}$ via [[#^def-2-6|Definition 2.6]] gives $\mathbb{P}_{k}\left(\bigcap_{s=1}^{m} \left\{X_{i_{s}} = r_{i_{s}}\right\}\right) = \prod_{s=1}^{m} \text{len}(p_{i_{s}})^{-1}$.

3. **Factorization Closure:** Substituting $\mathbb{P}_{k}(X_{i_{s}} = r_{i_{s}}) = \text{len}(p_{i_{s}})^{-1}$ from [[#^thm-2-5|Theorem 2.5]] yields $\prod_{s=1}^{m} \mathbb{P}_{k}(X_{i_{s}} = r_{i_{s}})$, proving complete mutual statistical independence.

---

## 2.4 Information-Theoretic Orthogonality and Additive Channel Capacity ^sec-2-4


<br>

##### Definition 2.8: Shannon Channel Entropy and Mutual Information ^def-2-8

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^def-2-6|Definition 2.6]], [[#^def-2-7|Definition 2.7]].

Using the base-$2$ logarithm $\log_{2}$ established in [[#^thm-1-11|Theorem 1.11]], define the marginal Shannon entropy $H(X_{i})$ and pairwise mutual information $I(X_{i}; X_{j})$ in bits for discrete coordinate random variables $X_{i}, X_{j}$ on $(\Omega_{k}, \mathcal{F}_{k}, \mathbb{P}_{k})$ by:

$$
H(X_{i}) \coloneq -\sum_{r_{i}=0}^{\text{len}(p_{i})-1} \mathbb{P}_{k}(X_{i} = r_{i}) \log_{2} \mathbb{P}_{k}(X_{i} = r_{i})
$$

$$
I(X_{i}; X_{j}) \coloneq \sum_{r_{i}=0}^{\text{len}(p_{i})-1} \sum_{r_{j}=0}^{\text{len}(p_{j})-1} \mathbb{P}_{k}(X_{i} = r_{i}, X_{j} = r_{j}) \log_{2} \left( \frac{\mathbb{P}_{k}(X_{i} = r_{i}, X_{j} = r_{j})}{\mathbb{P}_{k}(X_{i} = r_{i}) \mathbb{P}_{k}(X_{j} = r_{j})} \right)
$$


<br>

##### Theorem 2.7: Strict Algebraic Orthogonality of Prime Channels ^thm-2-7

*Parent Derivation:* [[#^thm-2-5|Theorem 2.5]], [[#^thm-2-6|Theorem 2.6]], [[#^def-2-8|Definition 2.8]].

Any two distinct prime channels share identically zero Shannon mutual information:

$$
\forall i \neq j \in \{1, \dots, k\}, \quad I(X_{i}; X_{j}) = 0
$$

*Proof:*

1. **Likelihood Ratio Collapse:** By [[#^thm-2-6|Theorem 2.6]] ($m = 2$) and [[#^thm-2-5|Theorem 2.5]], every joint probability equals the product of its marginals, reducing the likelihood ratio inside [[#^def-2-8|Definition 2.8]] to unity:

$$
\frac{\mathbb{P}_{k}(X_{i} = r_{i}, X_{j} = r_{j})}{\mathbb{P}_{k}(X_{i} = r_{i}) \mathbb{P}_{k}(X_{j} = r_{j})} = \frac{\text{len}(p_{i})^{-1} \cdot \text{len}(p_{j})^{-1}}{\text{len}(p_{i})^{-1} \cdot \text{len}(p_{j})^{-1}} = 1
$$

2. **Zero Mutual Information:** Evaluating $\log_{2}(1) = 0$ across every term in the double sum of [[#^def-2-8|Definition 2.8]] yields $I(X_{i}; X_{j}) = 0$, proving that distinct prime moduli operate as strictly orthogonal, non-interfering information channels.


<br>

##### Theorem 2.8: Additive Total Channel Capacity ^thm-2-8

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^def-2-4|Definition 2.4]], [[#^thm-2-5|Theorem 2.5]], [[#^thm-2-6|Theorem 2.6]], [[#^def-2-8|Definition 2.8]].

The joint Shannon information capacity of the primorial residue system $\Omega_{k}$ is strictly additive across all prime channels:

$$
H(X_{1}, X_{2}, \dots, X_{k}) = \sum_{i=1}^{k} H(X_{i}) = \sum_{i=1}^{k} \log_{2} \text{len}(p_{i}) = \log_{2} N_{k}
$$

*Proof:*

1. **Single-Channel Marginal Entropy:** Substituting $\mathbb{P}_{k}(X_{i} = r_{i}) = \text{len}(p_{i})^{-1}$ ([[#^thm-2-5|Theorem 2.5]]) into [[#^def-2-8|Definition 2.8]] evaluates each channel's capacity:

$$
H(X_{i}) = -\sum_{r_{i}=0}^{\text{len}(p_{i})-1} \frac{1}{\text{len}(p_{i})} \log_{2} \left( \frac{1}{\text{len}(p_{i})} \right) = \text{len}(p_{i}) \left( \frac{\log_{2} \text{len}(p_{i})}{\text{len}(p_{i})} \right) = \log_{2} \text{len}(p_{i})
$$

2. **Joint Entropy Additivity:** Because $\{X_{1}, \dots, X_{k}\}$ are mutually independent ([[#^thm-2-6|Theorem 2.6]]) and $\Psi_{k}$ is a bijection ([[#^thm-2-4|Theorem 2.4]]), the joint entropy equals the sum of the marginal entropies: $H(X_{1}, \dots, X_{k}) = \sum_{i=1}^{k} H(X_{i}) = \sum_{i=1}^{k} \log_{2} \text{len}(p_{i})$.

3. **Primorial Logarithmic Contraction:** Applying logarithmic product identities ([[#^thm-1-11|Theorem 1.11]]) and [[#^def-2-4|Definition 2.4]] ($N_{k} = \prod_{i=1}^{k} \text{len}(p_{i})$) gives $\sum_{i=1}^{k} \log_{2} \text{len}(p_{i}) = \log_{2}\left(\prod_{i=1}^{k} \text{len}(p_{i})\right) = \log_{2} N_{k}$.

**Emergent Isomorphism Bridge 3 (Chinese Remainder Theorem and Shannon Channel Orthogonality):** In classical number theory, the Chinese Remainder Theorem is presented as an algebraic existence theorem for simultaneous congruences, while Shannon's entropy and mutual information are axiomatized separately in communication theory. Under [[#^def-0-1|Definition 0.1]], [[#^thm-2-4|Theorem 2.4]], [[#^thm-2-7|Theorem 2.7]], and [[#^thm-2-8|Theorem 2.8]] reveal that these two pillars are dual aspects of the same structure: pairwise coprimality of prime moduli ($\gcd(\text{len}(p_{i}), \text{len}(p_{j})) = 1$) is *equivalent* to zero Shannon mutual information ($I(X_{i}; X_{j}) = 0$), allowing an $N_{k}$-state integer message to be transmitted across $k$ independent prime channels with zero cross-talk and strictly additive capacity $\log_{2} N_{k}$ bits.

*Exit Handoff:* We have decomposed linear unary words into prime atoms and projected finite rings $\mathbb{Z}/N_{k}\mathbb{Z}$ onto statistically independent prime channels. However, modular arithmetic modulo $N_{k}$ wraps around at magnitude $N_{k}$—motivating unbounded quotient-residue tuples and finite algebraic automata in Section 3.

---

---

# Section 3: Finite Algebraic Automata — Mixed-Radix Tuples, Signed Tri-Strings, and Chiral Parity FST ^sec-3

*Entry Primer:* In Section 2, the Chinese Remainder Theorem ring isomorphism $\Psi_{k}$ decomposed the finite primorial quotient $\mathbb{Z}/N_{k}\mathbb{Z}$ into $k$ statistically independent prime channels with zero mutual information. However, arithmetic in $\mathbb{Z}/N_{k}\mathbb{Z}$ wraps around at magnitude $N_{k}$, unary strings lack negative exponential scaling, and prime candidates still require modular filtering. How do we compute across unbounded integers in $\mathbb{Z}$ and negative $p$-adic scales while keeping modular arithmetic inside parallel prime channels? In this section, we construct three finite algebraic machines: mixed-radix primorial tuples $\mathcal{Z}_{k}$, signed Tri-String floating-point registers $\mathcal{F}_{\mathbb{Z}}$, and the Chiral Prime Parity Finite-State Transducer $\mathcal{M}$.

## 3.1 Mixed-Radix Primorial Tuple State Space ^sec-3-1

To represent arbitrary positive and negative integers in $\mathbb{Z}$ while isolating modular arithmetic inside orthogonal prime channels, we pair an unbounded global primorial quotient scale $E$ with a canonical non-negative primorial residue $C$.


<br>

##### Definition 3.1: Mixed-Radix Primorial Tuple State Space ^def-3-1

*Parent Derivation:* [[#^def-1-6|Definition 1.6]], [[#^thm-1-9|Theorem 1.9]], [[#^def-2-4|Definition 2.4]].

For a fixed primorial stage $k \in \mathbb{N}_{\ge 1}$ with scalar magnitude $N_{k} = \text{len}(P_{k})$, define the mixed-radix primorial state space $\mathcal{Z}_{k}$ as the Cartesian product:

$$
\mathcal{Z}_{k} \coloneq \mathbb{Z} \times \{0, 1, \dots, N_{k} - 1\}
$$

An element $Z \in \mathcal{Z}_{k}$ is written as the ordered pair $[E, C]$, where $E \in \mathbb{Z}$ denotes the global primorial quotient magnitude and $C \in \{0, 1, \dots, N_{k} - 1\}$ denotes the canonical primorial residue.


<br>

##### Definition 3.2: Scalar Evaluation and Canonical Modular Projection ^def-3-2

*Parent Derivation:* [[#^thm-1-8|Theorem 1.8]], [[#^thm-1-9|Theorem 1.9]], [[#^def-3-1|Definition 3.1]].

Define the scalar evaluation map $\nu_{k}: \mathcal{Z}_{k} \to \mathbb{Z}$ and the canonical modular projection $\mathcal{M}_{k}: \mathbb{Z} \to \mathcal{Z}_{k}$ via Euclidean integer division:

$$
\nu_{k}([E, C]) \coloneq E \cdot N_{k} + C
$$

$$
\mathcal{M}_{k}(x) \coloneq \left[ \left\lfloor \frac{x}{N_{k}} \right\rfloor, \, x \bmod N_{k} \right]
$$

where $x \bmod N_{k} \in \{0, 1, \dots, N_{k} - 1\}$ denotes the unique non-negative Euclidean remainder satisfying $x = \lfloor x / N_{k} \rfloor \cdot N_{k} + (x \bmod N_{k})$.


<br>

##### Theorem 3.1: Canonical Bijective Inversion on Mixed-Radix Tuples ^thm-3-1

*Parent Derivation:* [[#^thm-1-9|Theorem 1.9]], [[#^def-3-1|Definition 3.1]], [[#^def-3-2|Definition 3.2]].

The evaluation map $\nu_{k}$ and projection map $\mathcal{M}_{k}$ are mutual two-sided inverses establishing a bijection between $\mathcal{Z}_{k}$ and $\mathbb{Z}$:

$$
\forall Z \in \mathcal{Z}_{k}, \quad \mathcal{M}_{k}(\nu_{k}(Z)) = Z
$$

$$
\forall x \in \mathbb{Z}, \quad \nu_{k}(\mathcal{M}_{k}(x)) = x
$$

*Proof:*

1. **Left Inversion on $\mathcal{Z}_{k}$:** Let $Z = [E, C] \in \mathcal{Z}_{k}$, so $E \in \mathbb{Z}$ and $0 \le C < N_{k}$ by [[#^def-3-1|Definition 3.1]]. Evaluating $x \coloneq \nu_{k}([E, C]) = E \cdot N_{k} + C$ via [[#^def-3-2|Definition 3.2]] and applying Euclidean integer division gives $\lfloor (E \cdot N_{k} + C) / N_{k} \rfloor = E + \lfloor C / N_{k} \rfloor = E$ and $(E \cdot N_{k} + C) \bmod N_{k} = C$, yielding $\mathcal{M}_{k}(\nu_{k}(Z)) = [E, C] = Z$.

2. **Right Inversion on $\mathbb{Z}$:** For any integer $x \in \mathbb{Z}$, the Euclidean division identity in [[#^def-3-2|Definition 3.2]] directly yields $\nu_{k}(\mathcal{M}_{k}(x)) = \lfloor x / N_{k} \rfloor \cdot N_{k} + (x \bmod N_{k}) = x$, proving bijectivity.

---

## 3.2 Unified Arithmetic Operators and Bounded Unit Borrows ^sec-3-2

Transporting the ring operations of $\mathbb{Z}$ across the bijection $\mathcal{M}_{k}$ induces closed-form algebraic operators on $\mathcal{Z}_{k}$ whose carries and borrows are strictly bounded.


<br>

##### Theorem 3.2: Unified Tuple Addition Operator ^thm-3-2

*Parent Derivation:* [[#^thm-1-9|Theorem 1.9]], [[#^def-3-1|Definition 3.1]], [[#^def-3-2|Definition 3.2]], [[#^thm-3-1|Theorem 3.1]].

For any $Z_{a} = [E_{a}, C_{a}]$ and $Z_{b} = [E_{b}, C_{b}]$ in $\mathcal{Z}_{k}$, define unified addition $\oplus: \mathcal{Z}_{k} \times \mathcal{Z}_{k} \to \mathcal{Z}_{k}$ by:

$$
[E_{a}, C_{a}] \oplus [E_{b}, C_{b}] \coloneq \left[ E_{a} + E_{b} + \left\lfloor \frac{C_{a} + C_{b}}{N_{k}} \right\rfloor, \, (C_{a} + C_{b}) \bmod N_{k} \right]
$$

Then $\nu_{k}(Z_{a} \oplus Z_{b}) = \nu_{k}(Z_{a}) + \nu_{k}(Z_{b})$, and the overflow carry $\lfloor (C_{a} + C_{b}) / N_{k} \rfloor$ lies strictly in $\{0, 1\}$.

*Proof:*

1. **Algebraic Expansion:** By [[#^def-3-2|Definition 3.2]] and ring distributivity in $\mathbb{Z}$ ([[#^thm-1-9|Theorem 1.9]]), $\nu_{k}(Z_{a}) + \nu_{k}(Z_{b}) = (E_{a} + E_{b}) N_{k} + (C_{a} + C_{b})$.

2. **Euclidean Remainder Decomposition:** Splitting $C_{a} + C_{b} = \lfloor (C_{a} + C_{b}) / N_{k} \rfloor N_{k} + ((C_{a} + C_{b}) \bmod N_{k})$ and regrouping multiples of $N_{k}$ yields $\nu_{k}(Z_{a}) + \nu_{k}(Z_{b}) = \nu_{k}(Z_{a} \oplus Z_{b})$.

3. **Unit Carry Bound:** Because $0 \le C_{a}, C_{b} \le N_{k} - 1$ ([[#^def-3-1|Definition 3.1]]), $0 \le C_{a} + C_{b} \le 2N_{k} - 2 < 2N_{k}$, restricting $\lfloor (C_{a} + C_{b}) / N_{k} \rfloor$ to $\{0, 1\}$.


<br>

##### Theorem 3.3: Unified Tuple Multiplication Operator ^thm-3-3

*Parent Derivation:* [[#^thm-1-9|Theorem 1.9]], [[#^def-3-2|Definition 3.2]], [[#^thm-3-1|Theorem 3.1]].

For any $Z_{a} = [E_{a}, C_{a}]$ and $Z_{b} = [E_{b}, C_{b}]$ in $\mathcal{Z}_{k}$, define unified multiplication $\otimes: \mathcal{Z}_{k} \times \mathcal{Z}_{k} \to \mathcal{Z}_{k}$ by:

$$
[E_{a}, C_{a}] \otimes [E_{b}, C_{b}] \coloneq \left[ E_{a} E_{b} N_{k} + E_{a} C_{b} + E_{b} C_{a} + \left\lfloor \frac{C_{a} C_{b}}{N_{k}} \right\rfloor, \, (C_{a} C_{b}) \bmod N_{k} \right]
$$

Then $\nu_{k}(Z_{a} \otimes Z_{b}) = \nu_{k}(Z_{a}) \cdot \nu_{k}(Z_{b})$.

*Proof:*

1. **Bilinear Expansion:** Expanding $\nu_{k}(Z_{a}) \cdot \nu_{k}(Z_{b}) = (E_{a} N_{k} + C_{a})(E_{b} N_{k} + C_{b})$ in $\mathbb{Z}$ ([[#^thm-1-9|Theorem 1.9]]) produces $E_{a} E_{b} N_{k}^{2} + (E_{a} C_{b} + E_{b} C_{a}) N_{k} + C_{a} C_{b}$.

2. **Residue Product Reduction:** Applying $C_{a} C_{b} = \lfloor (C_{a} C_{b}) / N_{k} \rfloor N_{k} + ((C_{a} C_{b}) \bmod N_{k})$ and factoring out $N_{k}$ yields $\nu_{k}(Z_{a}) \cdot \nu_{k}(Z_{b}) = \nu_{k}(Z_{a} \otimes Z_{b})$.


<br>

##### Theorem 3.4: Unified Tuple Subtraction and Strictly Bounded Unit Borrow ^thm-3-4

*Parent Derivation:* [[#^thm-1-9|Theorem 1.9]], [[#^def-3-1|Definition 3.1]], [[#^def-3-2|Definition 3.2]], [[#^thm-3-1|Theorem 3.1]].

For any $Z_{a} = [E_{a}, C_{a}]$ and $Z_{b} = [E_{b}, C_{b}]$ in $\mathcal{Z}_{k}$, define unified subtraction $\ominus: \mathcal{Z}_{k} \times \mathcal{Z}_{k} \to \mathcal{Z}_{k}$ by:

$$
[E_{a}, C_{a}] \ominus [E_{b}, C_{b}] \coloneq \left[ E_{a} - E_{b} + \left\lfloor \frac{C_{a} - C_{b}}{N_{k}} \right\rfloor, \, (C_{a} - C_{b}) \bmod N_{k} \right]
$$

Then $\nu_{k}(Z_{a} \ominus Z_{b}) = \nu_{k}(Z_{a}) - \nu_{k}(Z_{b})$, and the borrow term $\lfloor (C_{a} - C_{b}) / N_{k} \rfloor$ is strictly bounded within $\{0, -1\}$.

*Proof:*

1. **Difference Decomposition:** Writing $\nu_{k}(Z_{a}) - \nu_{k}(Z_{b}) = (E_{a} - E_{b}) N_{k} + (C_{a} - C_{b})$ and expanding $C_{a} - C_{b} = \lfloor (C_{a} - C_{b}) / N_{k} \rfloor N_{k} + ((C_{a} - C_{b}) \bmod N_{k})$ with $0 \le (C_{a} - C_{b}) \bmod N_{k} < N_{k}$ establishes $\nu_{k}(Z_{a} \ominus Z_{b}) = \nu_{k}(Z_{a}) - \nu_{k}(Z_{b})$.

2. **Unit Borrow Verification:** Because $0 \le C_{a}, C_{b} \le N_{k} - 1$ ([[#^def-3-1|Definition 3.1]]), the residue difference satisfies $-(N_{k} - 1) \le C_{a} - C_{b} \le N_{k} - 1$. When $C_{a} \ge C_{b}$, $0 \le C_{a} - C_{b} < N_{k}$ gives $\lfloor (C_{a} - C_{b}) / N_{k} \rfloor = 0$; when $C_{a} < C_{b}$, $-N_{k} < C_{a} - C_{b} < 0$ gives $\lfloor (C_{a} - C_{b}) / N_{k} \rfloor = -1$, bounding borrows strictly to $\{0, -1\}$.


<br>

##### Definition 3.3: Tuple Euclidean Division and Modulo Operators ^def-3-3

*Parent Derivation:* [[#^def-3-1|Definition 3.1]], [[#^def-3-2|Definition 3.2]].

For any $Z_{a}, Z_{b} \in \mathcal{Z}_{k}$ with $\nu_{k}(Z_{b}) > 0$, define Euclidean quotient $\oslash$ and remainder $\odot$ on $\mathcal{Z}_{k}$ via scalar evaluation and re-projection:

$$
Z_{a} \oslash Z_{b} \coloneq \mathcal{M}_{k}\left( \left\lfloor \frac{\nu_{k}(Z_{a})}{\nu_{k}(Z_{b})} \right\rfloor \right), \qquad Z_{a} \odot Z_{b} \coloneq \mathcal{M}_{k}\left( \nu_{k}(Z_{a}) \bmod \nu_{k}(Z_{b}) \right)
$$


<br>

##### Theorem 3.5: Euclidean Reconstruction Invariant on Primorial Tuples ^thm-3-5

*Parent Derivation:* [[#^thm-3-1|Theorem 3.1]], [[#^thm-3-2|Theorem 3.2]], [[#^thm-3-3|Theorem 3.3]], [[#^def-3-3|Definition 3.3]].

For all $Z_{a}, Z_{b} \in \mathcal{Z}_{k}$ with $\nu_{k}(Z_{b}) > 0$, tuple division and modulo satisfy the exact Euclidean invariant:

$$
Z_{a} = \left( Z_{b} \otimes (Z_{a} \oslash Z_{b}) \right) \oplus (Z_{a} \odot Z_{b})
$$

$$
0 \le \nu_{k}(Z_{a} \odot Z_{b}) < \nu_{k}(Z_{b})
$$

*Proof:*

1. **Scalar Euclidean Identity:** Let $q \coloneq \lfloor \nu_{k}(Z_{a}) / \nu_{k}(Z_{b}) \rfloor$ and $r \coloneq \nu_{k}(Z_{a}) \bmod \nu_{k}(Z_{b})$, so $\nu_{k}(Z_{a}) = \nu_{k}(Z_{b}) \cdot q + r$ with $0 \le r < \nu_{k}(Z_{b})$.

2. **Homomorphic Transport to $\mathcal{Z}_{k}$:** By [[#^thm-3-1|Theorem 3.1]], [[#^thm-3-2|Theorem 3.2]], and [[#^thm-3-3|Theorem 3.3]], $\mathcal{M}_{k}$ is a ring isomorphism from $\mathbb{Z}$ onto $(\mathcal{Z}_{k}, \oplus, \otimes)$. Applying $\mathcal{M}_{k}$ to both sides via [[#^def-3-3|Definition 3.3]] gives $Z_{a} = (Z_{b} \otimes \mathcal{M}_{k}(q)) \oplus \mathcal{M}_{k}(r) = (Z_{b} \otimes (Z_{a} \oslash Z_{b})) \oplus (Z_{a} \odot Z_{b})$ with $\nu_{k}(Z_{a} \odot Z_{b}) = r < \nu_{k}(Z_{b})$.

**Worked Example 4 (Signed Tuple Arithmetic in $\mathcal{Z}_{2}$):** Fix stage $k = 2$ with $N_{2} = 6$. By [[#^def-3-2|Definition 3.2]], $14$ projects to $\mathcal{M}_{2}(14) = [2, 2]$ ($2 \cdot 6 + 2 = 14$), while $-5$ projects to $\mathcal{M}_{2}(-5) = [-1, 1]$ ($-1 \cdot 6 + 1 = -5$). Applying [[#^thm-3-2|Theorem 3.2]] and [[#^thm-3-4|Theorem 3.4]] yields:

$$
[2, 2] \oplus [-1, 1] = \left[ 2 + (-1) + \left\lfloor \frac{2 + 1}{6} \right\rfloor, \, (2 + 1) \bmod 6 \right] = [1, 3] \quad \left(\nu_{2}([1, 3]) = 9 = 14 + (-5)\right)
$$

$$
[-1, 1] \ominus [2, 2] = \left[ -1 - 2 + \left\lfloor \frac{1 - 2}{6} \right\rfloor, \, (1 - 2) \bmod 6 \right] = [-4, 5] \quad \left(\nu_{2}([-4, 5]) = -19 = -5 - 14\right)
$$

Notice how the negative residue difference $1 - 2 = -1$ triggers the exact unit borrow $\lfloor -1 / 6 \rfloor = -1$ while maintaining a canonical non-negative residue $5 \in \{0, \dots, 5\}$.

---

## 3.3 Carry-Free Parallel Residue Execution Across Orthogonal Channels ^sec-3-3


<br>

##### Theorem 3.6: Component-Wise Carry-Free RNS Residue Execution ^thm-3-6

*Parent Derivation:* [[#^def-2-5|Definition 2.5]], [[#^thm-2-4|Theorem 2.4]], [[#^thm-2-7|Theorem 2.7]], [[#^thm-3-2|Theorem 3.2]], [[#^thm-3-3|Theorem 3.3]].

Let $\vec{r}_{a} = \Psi_{k}(C_{a})$ and $\vec{r}_{b} = \Psi_{k}(C_{b})$ be the residue coordinate vectors of $C_{a}, C_{b} \in \mathbb{Z}/N_{k}\mathbb{Z}$. The modular residue updates of $\oplus$ and $\otimes$ execute independently across all $k$ prime channels with zero inter-channel carries:

$$
\Psi_{k}\left( (C_{a} + C_{b}) \bmod N_{k} \right) = \left( (r_{a,i} + r_{b,i}) \bmod \text{len}(p_{i}) \right)_{i=1}^{k}
$$

$$
\Psi_{k}\left( (C_{a} \cdot C_{b}) \bmod N_{k} \right) = \left( (r_{a,i} \cdot r_{b,i}) \bmod \text{len}(p_{i}) \right)_{i=1}^{k}
$$

*Intuition:* Because $\Psi_{k}$ is a ring isomorphism onto a direct product of independent prime fields, updating the residue component $C$ under addition or multiplication decomposes into $k$ parallel, non-communicating modular lanes, isolating cross-scale interaction to the single global quotient overflow check into $E$.

*Proof:*

1. **Ring Isomorphism Decomposition:** By [[#^thm-2-4|Theorem 2.4]], $\Psi_{k}: \mathbb{Z}/N_{k}\mathbb{Z} \xrightarrow{\cong} \prod_{i=1}^{k} (\mathbb{Z}/\text{len}(p_{i})\mathbb{Z})$ is a ring isomorphism, so ring addition and multiplication in $\mathbb{Z}/N_{k}\mathbb{Z}$ map coordinate-wise to modular operations modulo $\text{len}(p_{i})$.

2. **Channel Isolation and Scope Boundary:** Because distinct prime channels satisfy $I(X_{i}; X_{j}) = 0$ ([[#^thm-2-7|Theorem 2.7]]), computing the updated residue vector $\Psi_{k}(C_{a} \star C_{b})$ for $\star \in \{+, \cdot\}$ requires zero carry propagation between channel $i$ and channel $j$. Computing the global quotient overflow carry $\lfloor (C_{a} \star C_{b}) / N_{k} \rfloor$ into the outer coordinate $E$ remains a separate global magnitude check over $\mathcal{Z}_{k}$.

**Emergent Isomorphism Bridge 4a (Mixed-Radix Residue Number System Hardware):** In computer arithmetic and fault-tolerant digital signal processing, **Residue Number Systems (RNS)** represent large integers by their remainders modulo pairwise coprime moduli to eliminate carry-propagation latency during addition and multiplication. [[#^thm-3-1|Theorem 3.1]] through [[#^thm-3-6|Theorem 3.6]] show that pairing a parallel RNS residue register $\Psi_{k}(C)$ with an unbounded integer quotient scale $E$ produces an exact, lossless ring representation of $\mathbb{Z}$ with unit-bounded carries $\{0, 1\}$ and borrows $\{0, -1\}$.

---

## 3.4 Signed Tri-String Floating-Point Monoid Arithmetic ^sec-3-4

To represent exponential scaling across both positive magnitudes and negative $p$-adic valuations without category confusion between syntactic strings and scalars, we generalize floating-point triples to signed integer exponents.


<br>

##### Definition 3.4: Unsigned and Signed Tri-String Floating-Point Spaces ^def-3-4

*Parent Derivation:* [[#^def-1-1|Definition 1.1]], [[#^def-1-4|Definition 1.4]], [[#^def-1-6|Definition 1.6]], [[#^def-1-7|Definition 1.7]].

Define the unsigned Tri-String floating-point space $\mathcal{F} \subset (\Sigma^*)^3$ and the signed-exponent Tri-String floating-point space $\mathcal{F}_{\mathbb{Z}} \subset \mathbb{Z} \times \Sigma^* \times \Sigma^*$ by:

$$
\mathcal{F} \coloneq \left\{ [\Xi^{e}, \Xi^{b}, \Xi^{m}] \;\middle\vert{}\; \Xi^{e}, \Xi^{b}, \Xi^{m} \in \Sigma^* \land \text{len}(\Xi^{b}) \ge 2 \right\}
$$

$$
\mathcal{F}_{\mathbb{Z}} \coloneq \left\{ [e, \Xi^{b}, \Xi^{m}] \;\middle\vert{}\; e \in \mathbb{Z}, \, \Xi^{b}, \Xi^{m} \in \Sigma^* \land \text{len}(\Xi^{b}) \ge 2 \right\}
$$

where $e \in \mathbb{Z}$ is the signed exponent, $\Xi^{b}$ is the base word, and $\Xi^{m}$ is the mantissa word. Unsigned triples embed canonically into $\mathcal{F}_{\mathbb{Z}}$ via $[\Xi^{e}, \Xi^{b}, \Xi^{m}] \mapsto [[(\Xi^{e}, \varepsilon)]_{+}, \Xi^{b}, \Xi^{m}]$.


<br>

##### Definition 3.5: Tri-String Scalar Valuation Homomorphism ^def-3-5

*Parent Derivation:* [[#^def-1-4|Definition 1.4]], [[#^thm-1-10|Theorem 1.10]], [[#^def-3-4|Definition 3.4]].

Define the rational scalar evaluation map $\text{Val}: \mathcal{F}_{\mathbb{Z}} \to \mathbb{Q}_{\ge 0}$ by:

$$
\text{Val}\left([e, \Xi^{b}, \Xi^{m}]\right) \coloneq \text{len}(\Xi^{m}) \cdot \left( \text{len}(\Xi^{b}) \right)^{e}
$$

Because $\text{len}(\Xi^{b}) \ge 2 \neq 0_{\mathbb{Z}}$, negative integer powers $(\text{len}(\Xi^{b}))^{-n}$ ($n \in \mathbb{N}_{\ge 1}$) are well-defined multiplicative inverses in $\mathbb{Q}$ by [[#^thm-1-10|Theorem 1.10]].


<br>

##### Theorem 3.7: Homomorphic Tri-String Multiplication Operator ^thm-3-7

*Parent Derivation:* [[#^thm-1-6|Theorem 1.6]], [[#^thm-1-9|Theorem 1.9]], [[#^thm-1-10|Theorem 1.10]], [[#^def-3-4|Definition 3.4]], [[#^def-3-5|Definition 3.5]].

For any two signed Tri-Strings $\mathcal{F}_{1} = [e_{1}, \Xi^{b}, \Xi^{m_{1}}]$ and $\mathcal{F}_{2} = [e_{2}, \Xi^{b}, \Xi^{m_{2}}]$ sharing an identical base word $\Xi^{b}$, define multiplication $\odot_{\mathcal{F}}$ by:

$$
\mathcal{F}_{1} \odot_{\mathcal{F}} \mathcal{F}_{2} \coloneq \left[ e_{1} +_{\mathbb{Z}} e_{2}, \, \Xi^{b}, \, \text{flatMap}(\Xi^{m_{1}}, \Xi^{m_{2}}) \right]
$$

Then $\text{Val}(\mathcal{F}_{1} \odot_{\mathcal{F}} \mathcal{F}_{2}) = \text{Val}(\mathcal{F}_{1}) \cdot \text{Val}(\mathcal{F}_{2})$.

*Proof:*

1. **Scalar Product Grouping:** Expanding $\text{Val}(\mathcal{F}_{1}) \cdot \text{Val}(\mathcal{F}_{2})$ in $\mathbb{Q}$ via [[#^def-3-5|Definition 3.5]] and [[#^thm-1-10|Theorem 1.10]] gives $\left(\text{len}(\Xi^{m_{1}}) \cdot \text{len}(\Xi^{m_{2}})\right) \cdot (\text{len}(\Xi^{b}))^{e_{1} +_{\mathbb{Z}} e_{2}}$.

2. **Monoid Substitution Mapping:** By [[#^thm-1-6|Theorem 1.6]], $\text{len}(\Xi^{m_{1}}) \cdot \text{len}(\Xi^{m_{2}}) = \text{len}(\text{flatMap}(\Xi^{m_{1}}, \Xi^{m_{2}}))$, which matches $\text{Val}([e_{1} +_{\mathbb{Z}} e_{2}, \Xi^{b}, \text{flatMap}(\Xi^{m_{1}}, \Xi^{m_{2}})])$ identically.

---

## 3.5 Dual Binary Sieve and the Chiral Prime Parity Transducer ^sec-3-5

Restricting the finite primorial ring $\Omega_{k}$ to stage $k = 2$ isolates the minimal non-trivial modular automaton combining binary parity ($p_{1} = \Xi^{2}$) and ternary rotation ($p_{2} = \Xi^{3}$).


<br>

##### Definition 3.6: Second Primorial Unit Group and Lowercase Digamma Parity Operator ^def-3-6

*Parent Derivation:* [[#^def-2-3|Definition 2.3]], [[#^def-2-4|Definition 2.4]], [[#^thm-2-4|Theorem 2.4]].

At stage $k = 2$, $N_{2} = \text{len}(p_{1}) \cdot \text{len}(p_{2}) = 2 \times 3 = 6$, yielding $\Omega_{2} = \mathbb{Z}/6\mathbb{Z} = \{0, 1, 2, 3, 4, 5\}$. Pruning multiples of $2$ ($\{0, 2, 4\} \bmod{6}$) and multiples of $3$ ($\{0, 3\} \bmod{6}$) isolates the multiplicative unit group:

$$
(\mathbb{Z}/6\mathbb{Z})^\times = \{1, 5\} \equiv \{+1, -1\} \pmod{6} \cong C_{2}
$$

Let $\mathcal{P}_{\ge 5} \coloneq \{p \in \mathcal{P} \mid \text{len}(p) \ge 5\}$. Define the lowercase digamma prime parity operator $\digamma: \mathcal{P}_{\ge 5} \to \{-1, +1\}$ by:

$$
\digamma(p) \coloneq \begin{cases} -1 & \text{if } \text{len}(p) \equiv 5 \equiv -1 \pmod{6} \\ +1 & \text{if } \text{len}(p) \equiv 1 \equiv +1 \pmod{6} \end{cases}
$$

*Notation Rationale:* The archaic Greek letter $\digamma$ (lowercase *digamma*, which carried the numerical value $6$ in ancient Greek numerals) is chosen deliberately to denote the binary parity switch on the modulo-$6$ multiplicative unit group $(\mathbb{Z}/6\mathbb{Z})^\times$.


<br>

##### Theorem 3.8: Algebraic Prime Gap Chirality Laws ^thm-3-8

*Parent Derivation:* [[#^def-2-3|Definition 2.3]], [[#^def-3-6|Definition 3.6]].

For any pair of primes $p, q \in \mathcal{P}_{\ge 5}$ with length separation $\Delta \coloneq \text{len}(q) - \text{len}(p)$, the parity operator $\digamma$ enforces strict chiral transitions:

1. **Twin Prime Chirality ($\Delta = 2$):** $\digamma(p) = -1$ and $\digamma(q) = +1$ unconditionally.

2. **Cousin Prime Chirality ($\Delta = 4$):** $\digamma(p) = +1$ and $\digamma(q) = -1$ unconditionally.

3. **Sexy Prime Chirality ($\Delta = 6$):** $\digamma(q) = \digamma(p)$ (strict parity preservation).

4. **Singular Boundary Exception:** The pair $(p_{2}, p_{3}) = (\Xi^{3}, \Xi^{5})$ originates outside $(\mathbb{Z}/6\mathbb{Z})^\times$ at $\text{len}(p_{2}) = 3 \equiv 3 \pmod{6}$ and enters the unit group at $\digamma(p_{3}) = -1$.

*Proof:*

1. **Twin Gap ($\Delta = 2$) Exclusion of $+1$:** If $\digamma(p) = +1$, then $\text{len}(p) = 6m + 1$ for $m \in \mathbb{N}_{\ge 1}$ (since $\text{len}(p) \ge 5$), so $\text{len}(q) = 6m + 3 = 3(2m + 1) \ge 9$, making $q$ a composite multiple of $3$. Hence $\digamma(p) = -1$ ($\text{len}(p) = 6m - 1$), forcing $\text{len}(q) = 6m + 1 \equiv +1 \pmod{6}$ and $\digamma(q) = +1$.

2. **Cousin Gap ($\Delta = 4$) Exclusion of $-1$:** If $\digamma(p) = -1$ ($\text{len}(p) = 6m - 1$ with $m \ge 1$), then $\text{len}(q) = 6m + 3 = 3(2m + 1) \ge 9$, which is composite. Hence $\digamma(p) = +1$ ($\text{len}(p) = 6m + 1$), forcing $\text{len}(q) = 6m + 5 \equiv -1 \pmod{6}$ and $\digamma(q) = -1$.

3. **Sexy Gap ($\Delta = 6$) Invariance and Boundary Exception:** Adding $6$ leaves residue classes modulo $6$ invariant ($\text{len}(p) + 6 \equiv \text{len}(p) \pmod{6}$), while $\text{len}(p_{2}) = 3 \notin (\mathbb{Z}/6\mathbb{Z})^\times$ lies on the ternary filter modulus itself.


<br>

##### Definition 3.7: Deterministic Chiral Prime Parity Finite-State Transducer ^def-3-7

*Parent Derivation:* [[#^def-3-6|Definition 3.6]], [[#^thm-3-8|Theorem 3.8]].

Define the Chiral Prime Parity Finite-State Transducer $\mathcal{M} \coloneq (\mathcal{S}, \Sigma_{\Delta}, \delta, \dagger)$, where $\mathcal{S} \coloneq \{S_{-1}, S_{+1}\}$ encodes the parity states $\digamma = -1$ and $\digamma = +1$, $\Sigma_{\Delta} \coloneq \{2, 4, 6\}$ is the input step alphabet, $\dagger \notin \mathcal{S}$ is the absorbing composite dead-end state (multiples of $3$), and $\delta: \mathcal{S} \times \Sigma_{\Delta} \to \mathcal{S} \cup \{\dagger\}$ is the transition function:

$$
\delta(S_{\sigma}, \Delta) \coloneq \begin{cases} S_{+1} & \text{if } S_{\sigma} = S_{-1} \land \Delta = 2 \\ \dagger & \text{if } S_{\sigma} = S_{+1} \land \Delta = 2 \\ \dagger & \text{if } S_{\sigma} = S_{-1} \land \Delta = 4 \\ S_{-1} & \text{if } S_{\sigma} = S_{+1} \land \Delta = 4 \\ S_{-1} & \text{if } S_{\sigma} = S_{-1} \land \Delta = 6 \\ S_{+1} & \text{if } S_{\sigma} = S_{+1} \land \Delta = 6 \end{cases}
$$

*Notation Rationale:* The dagger symbol $\dagger$ denotes an absorbing algebraic trap state: any word reaching $\dagger$ is divisible by $3$ and permanently exits the prime candidate space.


<br>

##### Theorem 3.9: Determinism and Admissible Residue Closure of the Gap Transducer ^thm-3-9

*Parent Derivation:* [[#^thm-3-8|Theorem 3.8]], [[#^def-3-7|Definition 3.7]].

The automaton $\mathcal{M}$ is deterministic and completely classifies admissible prime-constellation transitions in $(\mathbb{Z}/6\mathbb{Z})^\times$: any step sequence from $p \in \mathcal{P}_{\ge 5}$ reaching $\dagger$ produces a guaranteed composite multiple of $3$, whereas survival in $\mathcal{S}$ is a necessary condition for primality.

| Current State $s \in \mathcal{S}$ | $\Delta = 2$ (Twin) | $\Delta = 4$ (Cousin) | $\Delta = 6$ (Sexy) |
| :--- | :--- | :--- | :--- |
| $S_{-1}$ ($6m - 1$) | $S_{+1}$ | $\dagger$ | $S_{-1}$ |
| $S_{+1}$ ($6m + 1$) | $\dagger$ | $S_{-1}$ | $S_{+1}$ |

*Proof:*

1. **Deterministic Transition Uniqueness:** Every pair $(S_{\sigma}, \Delta) \in \{S_{-1}, S_{+1}\} \times \{2, 4, 6\}$ maps under [[#^def-3-7|Definition 3.7]] to a single deterministic target in $\{S_{-1}, S_{+1}, \dagger\}$.

2. **Admissible Residue Closure:** By [[#^thm-3-8|Theorem 3.8]], transitions into $\dagger$ yield integers of the form $3(2m + 1) \ge 9$, which are strictly composite, whereas transitions into $S_{\pm 1}$ preserve coprimality to $6$ (necessary for primality for lengths $\ge 5$, while full primality requires coprimality to all primes $p_{i}$ with $\text{len}(p_{i})^{2} \le \text{len}(w)$).

**Worked Example 5 (Chiral Prime Trajectory vs. Composite Trap in $\mathcal{M}$):** Starting at $p_{3} = \Xi^{5}$ ($\text{len}(p_{3}) = 5 \equiv -1 \pmod{6}$, state $S_{-1}$), stepping across the prime sequence $5 \to 7 \to 11 \to 13 \to 19$ traces the alternating chiral path:

$$
S_{-1} \;(\Xi^{5}) \xrightarrow{\Delta = 2} S_{+1} \;(\Xi^{7}) \xrightarrow{\Delta = 4} S_{-1} \;(\Xi^{11}) \xrightarrow{\Delta = 2} S_{+1} \;(\Xi^{13}) \xrightarrow{\Delta = 6} S_{+1} \;(\Xi^{19})
$$

By contrast, applying a twin step $\Delta = 2$ from $\Xi^{7} \in S_{+1}$ transitions into $\delta(S_{+1}, 2) = \dagger$, correctly predicting that $\Xi^{9}$ ($\text{len} = 9 = 3 \times 3$) is composite.

**Emergent Isomorphism Bridge 4b (Base-6 Wheel Factorization and Prime Constellations):** In computational number theory, **wheel factorization** eliminates multiples of small primes $p_{1}, \dots, p_{k}$ before trial division. [[#^def-3-6|Definition 3.6]] through [[#^thm-3-9|Theorem 3.9]] show that the stage-$2$ wheel $(\mathbb{Z}/6\mathbb{Z})^\times \cong C_{2}$ acts as a deterministic two-state parity transducer governing prime constellations: twin primes ($\Delta = 2$) can occur only in the orientation $(6m - 1, 6m + 1)$, cousin primes ($\Delta = 4$) only in $(6m + 1, 6m + 5)$, and prime triplets $(p, p+2, p+6)$ or $(p, p+4, p+6)$ correspond to the unique two-step survival paths $S_{-1} \xrightarrow{2} S_{+1} \xrightarrow{4} S_{-1}$ and $S_{+1} \xrightarrow{4} S_{-1} \xrightarrow{2} S_{+1}$ that avoid $\dagger$.

*Exit Handoff:* We have constructed lossless mixed-radix tuple registers $\mathcal{Z}_{k}$, signed floating-point Tri-Strings $\mathcal{F}_{\mathbb{Z}}$, and the deterministic chiral gap transducer $\mathcal{M}$. Yet every finite primorial stage $k \in \mathbb{N}_{\ge 1}$ truncates resolution at $N_{k}$—motivating the projective limit $k \to \infty$ and non-Archimedean continuum calculus in Section 4.

---

---

# Section 4: Profinite Stone Limits, Continuum Dualities, and Ultrametric Calculus ^sec-4

*Entry Primer:* Sections 2 and 3 analyzed finite primorial quotient rings $R_{k} \coloneq \mathbb{Z}/N_{k}\mathbb{Z}$ and mixed-radix tuple registers $\mathcal{Z}_{k}$ at fixed resolution depth $k \in \mathbb{N}_{\ge 1}$. However, truncating at any finite depth $k$ captures only finitely many prime moduli. What topological, measure-theoretic, and differential universe emerges when we take the projective limit $k \to \infty$ across all square-free primorial stages simultaneously? In this section, we construct the profinite limit ring $R_{\infty}$, prove its homeomorphism to the Cantor space $\mathbf{2}^{\mathbb{N}}$ and measure isomorphism to the Lebesgue unit interval $[0, 1]$, and build a non-Archimedean differential and Fisher-information calculus on its infinite prefix trie.

## 4.1 Master Profinite Stone-Haar Lemma and the Square-Free Limit Ring ^sec-4-1

Passing to the projective limit $k \to \infty$ requires a unified topological and measure-theoretic foundation governing countable inverse systems of finite discrete rings.


<br>

##### Definition 4.1: Countable Surjective Inverse System and Cylinder Basis ^def-4-1

*Parent Derivation:* [[#^def-1-6|Definition 1.6]], [[#^thm-1-9|Theorem 1.9]], [[#^def-2-6|Definition 2.6]].

A countable surjective inverse system of finite rings consists of a family of finite discrete commutative rings $\{A_{n}\}_{n=1}^{\infty}$ with $\lvert A_{n} \rvert \ge 2$ together with surjective ring homomorphisms $\pi_{n, m}: A_{m} \to A_{n}$ for all $n \le m$ satisfying $\pi_{n, n} = \text{id}_{A_{n}}$ and $\pi_{n, m} \circ \pi_{m, \ell} = \pi_{n, \ell}$ for $n \le m \le \ell$. Its projective (inverse) limit is the subring of coherent threads:

$$
A_{\infty} \coloneq \varprojlim_{n} A_{n} = \left\{ (a_{n})_{n=1}^{\infty} \in \prod_{n=1}^{\infty} A_{n} \;\middle\vert{}\; \forall n \le m, \, \pi_{n, m}(a_{m}) = a_{n} \right\}
$$

Equipped with the subspace topology inherited from the product of discrete spaces $\prod_{n=1}^{\infty} A_{n}$, the canonical projections $\pi_{n}: A_{\infty} \to A_{n}$ define basic cylinder sets at depth $n$ for every $a \in A_{n}$:

$$
B_{n}(a) \coloneq \pi_{n}^{-1}(\{a\}) = \left\{ x \in A_{\infty} \;\middle\vert{}\; \pi_{n}(x) = a \right\}
$$


<br>

##### Lemma 4.1: Master Profinite Stone-Haar Lemma ^lem-4-1

*Parent Derivation:* [[#^def-2-6|Definition 2.6]], [[#^def-4-1|Definition 4.1]].

For any countable surjective inverse system $\{A_{n}, \pi_{n, m}\}_{n \le m}$ of finite discrete rings, the projective limit $A_{\infty} = \varprojlim_{n} A_{n}$ is a compact, Hausdorff, totally disconnected topological ring (a Stone space) whose basic cylinders $B_{n}(a)$ are clopen, and $A_{\infty}$ admits a unique normalized translation-invariant Haar probability measure $\mu$ on its Borel $\sigma$-algebra $\mathcal{B}(A_{\infty})$ satisfying:

$$
\forall n \in \mathbb{N}_{\ge 1}, \quad \forall a \in A_{n}, \quad \mu(B_{n}(a)) = \frac{1}{\lvert A_{n} \rvert}
$$

*Intuition:* Because each finite ring $A_{n}$ is compact and discrete, Tychonoff's product theorem traps the coherent limit $A_{\infty}$ inside a compact, totally disconnected Cantor-like space whose cylinder sets are simultaneously open and closed, forcing any finite cylinder cover to be finite and guaranteeing a unique uniform Haar probability measure.

*Proof:*

1. **Compactness and Hausdorff Separation:** Each finite discrete ring $A_{n}$ is compact and Hausdorff ($T_{2}$), so $\prod_{n=1}^{\infty} A_{n}$ is compact and Hausdorff by Tychonoff's Theorem. Because every compatibility condition $\pi_{n, m}(a_{m}) = a_{n}$ defines a closed subset in the Hausdorff product space, $A_{\infty}$ is a closed subspace of a compact Hausdorff space and hence compact and Hausdorff.

2. **Total Disconnectedness via Clopen Basis:** Every cylinder $B_{n}(a) = \pi_{n}^{-1}(\{a\})$ is open by continuity of $\pi_{n}$ and closed because its complement $A_{\infty} \setminus B_{n}(a) = \bigcup_{b \in A_{n} \setminus \{a\}} B_{n}(b)$ is a finite union of open sets. Because cylinder sets form a basis for the topology and distinct points $x \neq y$ disagree at some coordinate $n$ ($x \in B_{n}(x_{n})$, $y \notin B_{n}(x_{n})$), connected components are singletons.

3. **Unique Normalized Haar Probability Measure:** By surjectivity of $\pi_{n, m}$, every fiber of $\pi_{n, m}$ in the finite group $(A_{m}, +)$ has identical cardinality $\lvert A_{m} \rvert / \lvert A_{n} \rvert$. Defining the pre-measure $\mu_{0}(B_{n}(a)) \coloneq \lvert A_{n} \rvert^{-1}$ is therefore finitely additive across partitions $B_{n}(a) = \bigsqcup_{\pi_{n, m}(b) = a} B_{m}(b)$ and invariant under translation $x \mapsto y + x$. Because every cylinder is clopen and $A_{\infty}$ is compact, any countable disjoint cover of a cylinder by cylinders is finite, making $\mu_{0}$ trivially $\sigma$-additive on the cylinder algebra and extending uniquely by Carathéodory's Extension Theorem to the Haar probability measure $\mu$.


<br>

##### Definition 4.2: Primorial Inverse System and Square-Free Limit Ring ^def-4-2

*Parent Derivation:* [[#^def-2-4|Definition 2.4]], [[#^def-2-5|Definition 2.5]], [[#^def-4-1|Definition 4.1]].

For each $k \in \mathbb{N}_{\ge 1}$, let $R_{k} \coloneq \mathbb{Z}/N_{k}\mathbb{Z}$ be the $k$-th primorial quotient ring. Because $N_{k} \mid N_{m}$ whenever $k \le m$ ([[#^def-2-4|Definition 2.4]]), define the canonical reduction homomorphisms $\pi_{k, m}: R_{m} \to R_{k}$ by $\pi_{k, m}(x \bmod N_{m}) \coloneq x \bmod N_{k}$. The profinite primorial limit ring is the projective limit:

$$
R_{\infty} \coloneq \varprojlim_{k} R_{k}
$$


<br>

##### Theorem 4.1: Infinite Direct Product Ring Isomorphism ^thm-4-1

*Parent Derivation:* [[#^thm-2-4|Theorem 2.4]], [[#^def-4-2|Definition 4.2]].

The profinite primorial limit ring $R_{\infty}$ is canonically isomorphic as a topological ring to the infinite direct product of all prime residue fields:

$$
R_{\infty} \cong \prod_{i=1}^{\infty} \left( \mathbb{Z} / \text{len}(p_{i})\mathbb{Z} \right) = \prod_{i=1}^{\infty} \mathbb{F}_{p_{i}}
$$

*Proof:*

1. **Finite-Stage CRT Commutativity:** By [[#^thm-2-4|Theorem 2.4]], $\Psi_{k}: R_{k} \xrightarrow{\cong} \prod_{i=1}^{k} \mathbb{F}_{p_{i}}$ is a ring isomorphism for every $k \in \mathbb{N}_{\ge 1}$. For $k \le m$, the reduction homomorphism $\pi_{k, m}: R_{m} \to R_{k}$ commutes with coordinate truncation $\operatorname{trunc}_{k, m}: \prod_{i=1}^{m} \mathbb{F}_{p_{i}} \to \prod_{i=1}^{k} \mathbb{F}_{p_{i}}$, satisfying $\Psi_{k} \circ \pi_{k, m} = \operatorname{trunc}_{k, m} \circ \Psi_{m}$.

2. **Projective Limit Equivalence:** Passing to the inverse limit across $k \to \infty$ induces a topological ring isomorphism $\Psi_{\infty}: R_{\infty} \xrightarrow{\cong} \prod_{i=1}^{\infty} \mathbb{F}_{p_{i}}$ identifying each element $x \in R_{\infty}$ uniquely with an infinite residue vector $(r_{1}, r_{2}, r_{3}, \dots)$ where $r_{i} \in \{0, 1, \dots, \text{len}(p_{i}) - 1\}$.


<br>

##### Remark 4.1: Category Guard — Square-Free Limit Ring vs. Profinite Integers ^rem-4-1

*Parent Derivation:* [[#^thm-4-1|Theorem 4.1]].

Because $R_{\infty} \cong \prod_{i=1}^{\infty} \mathbb{F}_{p_{i}}$ is constructed strictly over square-free primorial moduli $N_{k} = \prod_{i=1}^{k} \text{len}(p_{i})$, it is a von Neumann regular ring possessing non-trivial orthogonal idempotents ($e_{i}^{2} = e_{i}$) and zero divisors. It must not be conflated with the full profinite completion $\widehat{\mathbb{Z}} \coloneq \prod_{p} \mathbb{Z}_{p}$, which incorporates prime-power towers $p^{m}$ and has no non-trivial idempotents. The exact structural relationship $R_{\infty} \cong \widehat{\mathbb{Z}} / \operatorname{rad}(\widehat{\mathbb{Z}})$ will be established in Section 5 once vertical $p$-adic towers are constructed.

---

## 4.2 Cantor Space Homeomorphism and Continuum Cardinality ^sec-4-2


<br>

##### Theorem 4.2: Stone Space Characterization and Cantor Homeomorphism ^thm-4-2

*Parent Derivation:* [[#^def-2-3|Definition 2.3]], [[#^lem-4-1|Lemma 4.1]], [[#^thm-4-1|Theorem 4.1]].

The topological space $R_{\infty}$ is homeomorphic to the classical Cantor set $\mathbf{2}^{\mathbb{N}}$:

$$
R_{\infty} \cong \mathbf{2}^{\mathbb{N}}
$$

*Proof:*

1. **Stone Space Properties and Metrizability:** Applying [[#^lem-4-1|Lemma 4.1]] to [[#^def-4-2|Definition 4.2]] shows that $R_{\infty}$ is non-empty, compact, Hausdorff, and totally disconnected with a countable clopen basis $\{B_{k}(\vec{r}_{k})\}$, hence second-countable and metrizable by Urysohn's Metrization Theorem.

2. **Perfectness (Absence of Isolated Points):** Let $x = (r_{1}, r_{2}, \dots) \in R_{\infty}$ and let $U$ be any open neighborhood of $x$. Then $x \in B_{k}(\vec{r}_{k}) \subseteq U$ for some depth $k \in \mathbb{N}_{\ge 1}$. Because every prime satisfies $\text{len}(p_{k+1}) \ge 2$ ([[#^def-2-3|Definition 2.3]]), there exist at least two distinct choices for $r_{k+1}$, so $B_{k}(\vec{r}_{k}) \neq \{x\}$ and no point of $R_{\infty}$ is isolated.

3. **Brouwer's Characterization Theorem:** Every non-empty, compact, metrizable, totally disconnected, perfect space is homeomorphic to the Cantor space $\mathbf{2}^{\mathbb{N}}$, yielding $R_{\infty} \cong \mathbf{2}^{\mathbb{N}}$.


<br>

##### Theorem 4.3: Continuum Cardinality of the Limit Ring ^thm-4-3

*Parent Derivation:* [[#^def-2-3|Definition 2.3]], [[#^thm-4-1|Theorem 4.1]].

The set-theoretic cardinality of $R_{\infty}$ equals the cardinality of the continuum $\mathfrak{c}$:

$$
\lvert R_{\infty} \rvert = \prod_{i=1}^{\infty} \text{len}(p_{i}) = 2^{\aleph_{0}} = \mathfrak{c}
$$

*Proof:*

1. **Cardinal Sandwich Bounds:** By [[#^thm-4-1|Theorem 4.1]] and [[#^def-2-3|Definition 2.3]], $2 \le \text{len}(p_{i}) < \aleph_{0}$ for all $i \in \mathbb{N}_{\ge 1}$, yielding $2^{\aleph_{0}} = \prod_{i=1}^{\infty} 2 \le \lvert R_{\infty} \rvert \le \prod_{i=1}^{\infty} \aleph_{0} = \aleph_{0}^{\aleph_{0}}$.

2. **Cantor-Bernstein-Schröder Collapse:** Because $\aleph_{0}^{\aleph_{0}} \le (2^{\aleph_{0}})^{\aleph_{0}} = 2^{\aleph_{0} \cdot \aleph_{0}} = 2^{\aleph_{0}} = \mathfrak{c}$, the Cantor-Bernstein-Schröder theorem forces $\lvert R_{\infty} \rvert = 2^{\aleph_{0}} = \mathfrak{c}$.

---

## 4.3 Primorial Trie Topology, Ultrametric Valuation, and Cantor Duality ^sec-4-3


<br>

##### Definition 4.3: Primorial Trie Tree Topology ^def-4-3

*Parent Derivation:* [[#^def-1-1|Definition 1.1]], [[#^thm-4-1|Theorem 4.1]].

Define the primorial trie $\mathcal{T} \coloneq (V, E)$ as the directed rooted tree whose vertices are finite residue prefix vectors and whose edges append one prime channel coordinate:

$$
V \coloneq \{\varepsilon\} \cup \bigcup_{k=1}^{\infty} \left( \prod_{i=1}^{k} \mathbb{F}_{p_{i}} \right)
$$

$$
E \coloneq \left\{ \left(\vec{r}_{k}, \, \vec{r}_{k} \frown (r_{k+1})\right) \;\middle\vert{}\; \vec{r}_{k} \in V, \, r_{k+1} \in \mathbb{F}_{p_{k+1}} \right\}
$$

where $\frown$ denotes tuple concatenation. The infinite path boundary $\partial \mathcal{T}$ originating at the root $\varepsilon$ is canonically identified with $R_{\infty}$ via [[#^thm-4-1|Theorem 4.1]].


<br>

##### Definition 4.4: Ultrametric Valuation Distance ^def-4-4

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^def-2-4|Definition 2.4]], [[#^thm-4-1|Theorem 4.1]], [[#^def-4-3|Definition 4.3]].

For two distinct points $x = (r_{i})_{i=1}^{\infty}$ and $y = (s_{i})_{i=1}^{\infty}$ in $R_{\infty}$, define their first disagreement depth $n(x, y) \coloneq \min \{k \in \mathbb{N}_{\ge 1} \mid r_{k} \neq s_{k}\}$. Setting $N_{0} \coloneq 1$, define the valuation distance $d: R_{\infty} \times R_{\infty} \to \mathbb{R}_{\ge 0}$ ([[#^thm-1-11|Theorem 1.11]]) by:

$$
d(x, y) \coloneq \begin{cases} 0 & \text{if } x = y \\ \frac{1}{N_{n(x, y) - 1}} & \text{if } x \neq y \end{cases}
$$


<br>

##### Theorem 4.4: Strong Triangle Inequality and Ultrametric Structure ^thm-4-4

*Parent Derivation:* [[#^def-2-3|Definition 2.3]], [[#^thm-4-2|Theorem 4.2]], [[#^def-4-4|Definition 4.4]].

The distance function $d$ satisfies the strong triangle inequality and induces the product topology on $R_{\infty}$, making $(R_{\infty}, d)$ a complete ultrametric space:

$$
\forall x, y, z \in R_{\infty}, \quad d(x, z) \le \max\left(d(x, y), \, d(y, z)\right)
$$

*Proof:*

1. **Degenerate Cases:** If $x = z$, $d(x, z) = 0 \le \max(d(x, y), d(y, z))$; if $x = y$ or $y = z$, the inequality holds as an immediate equality.

2. **Prefix Agreement Lower Bound:** Assume $x, y, z$ are pairwise distinct with $n_{xy} \coloneq n(x, y)$ and $n_{yz} \coloneq n(y, z)$. For every index $i < \min(n_{xy}, n_{yz})$, $x_{i} = y_{i}$ and $y_{i} = z_{i}$ imply $x_{i} = z_{i}$, forcing $n(x, z) \ge \min(n_{xy}, n_{yz})$.

3. **Monotonic Valuation Inversion and Topological Completeness:** Because $N_{k}$ is strictly increasing with $k$ ([[#^def-2-3|Definition 2.3]]), the map $n \mapsto N_{n-1}^{-1}$ is strictly decreasing, giving:

$$
d(x, z) = \frac{1}{N_{n(x, z) - 1}} \le \frac{1}{N_{\min(n_{xy}, n_{yz}) - 1}} = \max\left( \frac{1}{N_{n_{xy} - 1}}, \, \frac{1}{N_{n_{yz} - 1}} \right) = \max\left(d(x, y), \, d(y, z)\right)
$$

Moreover, for every $x \in R_{\infty}$ and $k \ge 1$, the ultrametric ball $B_{d}(x, N_{k}^{-1}) \coloneq \{y \in R_{\infty} \mid d(x, y) \le N_{k}^{-1}\}$ coincides identically with the basic clopen cylinder $B_{k}(\pi_{k}(x))$ ([[#^def-4-1|Definition 4.1]]), so $d$ induces the product topology on $R_{\infty}$ and completeness of $(R_{\infty}, d)$ follows directly from compactness of $R_{\infty}$ ([[#^thm-4-2|Theorem 4.2]]).


<br>

##### Theorem 4.5: Arbitrary Cylinder Error Convergence ^thm-4-5

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^def-2-3|Definition 2.3]], [[#^def-4-2|Definition 4.2]], [[#^def-4-4|Definition 4.4]], [[#^thm-4-4|Theorem 4.4]].

For every tolerance $\epsilon > 0$, there exists a primorial depth $K \in \mathbb{N}_{\ge 1}$ such that every cylinder ball at depth $k \ge K$ has ultrametric diameter strictly below $\epsilon$:

$$
\forall \epsilon > 0, \quad \exists K \in \mathbb{N}_{\ge 1} \quad \text{s.t.} \quad \forall k \ge K, \quad \operatorname{diam}\left(B_{k}(\vec{r}_{k})\right) \le \frac{1}{N_{k}} < \epsilon
$$

*Proof:*

1. **Cylinder Diameter Bound:** For any $x, y \in B_{k}(\vec{r}_{k})$, agreement on coordinates $1 \le i \le k$ forces $n(x, y) \ge k + 1$, so $d(x, y) \le N_{k}^{-1}$ by [[#^def-4-4|Definition 4.4]].

2. **Exponential Primorial Growth:** Because $\text{len}(p_{i}) \ge 2$ for all $i \ge 1$ ([[#^def-2-3|Definition 2.3]]), $N_{k} = \prod_{i=1}^{k} \text{len}(p_{i}) \ge 2^{k}$, so choosing $K \coloneq \lfloor \log_{2}(1/\epsilon) \rfloor + 1$ ([[#^thm-1-11|Theorem 1.11]]) guarantees $\operatorname{diam}(B_{k}(\vec{r}_{k})) \le N_{k}^{-1} \le 2^{-K} < \epsilon$ for all $k \ge K$.


<br>

##### Theorem 4.6: Bidirectional Cantor Duality — Synthesis vs. Analysis ^thm-4-6

*Parent Derivation:* [[#^thm-4-2|Theorem 4.2]], [[#^thm-4-5|Theorem 4.5]].

Finite residue prefixes and infinite continuum points in $R_{\infty}$ are linked by two inverse operations:

1. **Bottom-Up Synthesis:** For any coherent prefix chain $\vec{r}_{k+1} = \vec{r}_{k} \frown (r_{k+1})$, the nested closed cylinder balls $B_{1}(\vec{r}_{1}) \supset B_{2}(\vec{r}_{2}) \supset \dots$ intersect in a unique limit point:

$$
\bigcap_{k=1}^{\infty} B_{k}(\vec{r}_{k}) = \{x_{\infty}\} \quad \text{where } x_{\infty} = (r_{1}, r_{2}, r_{3}, \dots) \in R_{\infty}
$$

2. **Top-Down Analytic Projection:** For any $x_{\infty} \in R_{\infty}$ and tolerance $\epsilon > 0$, choosing $K$ per [[#^thm-4-5|Theorem 4.5]] extracts the exact finite RNS trace $\pi_{K}(x_{\infty}) = (r_{1}, \dots, r_{K})$ localizing $x_{\infty}$ within diameter $< \epsilon$.

*Proof:*

1. **Cantor Intersection Closure:** Each cylinder $B_{k}(\vec{r}_{k})$ is non-empty and closed in the complete metric space $(R_{\infty}, d)$ ([[#^thm-4-2|Theorem 4.2]], [[#^thm-4-4|Theorem 4.4]]). Because $\lim_{k \to \infty} \operatorname{diam}(B_{k}(\vec{r}_{k})) = 0$ by [[#^thm-4-5|Theorem 4.5]], Cantor's Intersection Theorem guarantees a unique singleton intersection $\{x_{\infty}\}$ whose $k$-th projection is $\pi_{k}(x_{\infty}) = \vec{r}_{k}$.

**Worked Example 6 (Depth-2 Primorial Trie Ultrametric Distance):** Consider two coherent threads $x = (1, 2, 0, 0, \dots)$ and $y = (1, 0, 4, 0, \dots)$ in $R_{\infty} \cong \prod_{i=1}^{\infty} \mathbb{F}_{p_{i}}$. Both agree on the binary channel $i = 1$ ($r_{1} = s_{1} = 1 \in \mathbb{F}_{2}$) and diverge first at the ternary channel $i = 2$ ($r_{2} = 2 \neq 0 = s_{2} \in \mathbb{F}_{3}$). By [[#^def-4-4|Definition 4.4]], $n(x, y) = 2$ and $N_{1} = \text{len}(p_{1}) = 2$, yielding ultrametric separation $d(x, y) = 1 / N_{1} = 1/2$.

---

## 4.4 Unified Continuum Isomorphisms: Dedekind-Cantor Duality and Rohlin Measure ^sec-4-4


<br>

##### Theorem 4.7: Dedekind-Cantor Trie Duality on the Archimedean Continuum ^thm-4-7

*Parent Derivation:* [[#^def-1-7|Definition 1.7]], [[#^thm-1-10|Theorem 1.10]], [[#^def-1-8|Definition 1.8]], [[#^thm-1-11|Theorem 1.11]], [[#^thm-4-2|Theorem 4.2]], [[#^thm-4-6|Theorem 4.6]].

Every real number $x \in \mathbb{R} = \overline{\mathbb{Q}}_{\lvert \cdot \rvert_{\infty}}$ constructed in [[#^thm-1-11|Theorem 1.11]] arises both as the unique intersection of a descending nested rational interval path $\bigcap_{n=1}^{\infty} [a_{n}, b_{n}]_{\mathbb{Q}} = \{x\}$ with $\lim_{n \to \infty} (b_{n} - a_{n}) = 0$ and as the limit of an infinite binary bisection trace $(r_{1}, r_{2}, \dots) \in \mathbf{2}^{\mathbb{N}} \cong R_{\infty}$ generated by a Dedekind cut $(A, B)$ of $\mathbb{Q}$.

*Proof:*

1. **Cauchy Trie Descent:** Every Cauchy sequence in $(\mathbb{Q}, \lvert \cdot \rvert_{\infty})$ ([[#^def-1-8|Definition 1.8]]) admits a subsequence enclosed in nested rational intervals $I_{n} = [a_{n}, b_{n}] \cap \mathbb{Q}$ with $I_{n+1} \subset I_{n}$ and $b_{n} - a_{n} \to 0$, whose closures in the metric completion $\mathbb{R}$ ([[#^thm-1-11|Theorem 1.11]]) intersect in a unique point $\{x\}$.

2. **Dedekind Binary Trace:** Given a Dedekind cut $(A, B)$ bounded by rationals $a_{0} \in A$ and $b_{0} \in B$, recursive bisection at $m_{n} \coloneq (a_{n} + b_{n})/2$ assigns $r_{n} = 0$ (updating $[a_{n+1}, b_{n+1}] = [m_{n}, b_{n}]$) when $m_{n} \in A$ and $r_{n} = 1$ (updating $[a_{n+1}, b_{n+1}] = [a_{n}, m_{n}]$) when $m_{n} \in B$, mapping $(A, B)$ to an infinite path trace in $\mathbf{2}^{\mathbb{N}} \cong R_{\infty}$ ([[#^thm-4-2|Theorem 4.2]], [[#^thm-4-6|Theorem 4.6]]) of width $(b_{0} - a_{0}) 2^{-n} \to 0$.


<br>

##### Theorem 4.8: Rohlin's Measure-Theoretic Isomorphism to the Lebesgue Unit Interval ^thm-4-8

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^lem-4-1|Lemma 4.1]], [[#^thm-4-2|Theorem 4.2]], [[#^thm-4-5|Theorem 4.5]], [[#^thm-4-6|Theorem 4.6]].

Equip $(R_{\infty}, \mathcal{B}(R_{\infty}))$ with the normalized Haar probability measure $\mu$ of [[#^lem-4-1|Lemma 4.1]] ($\mu(B_{k}(\vec{r}_{k})) = N_{k}^{-1}$) and equip $([0, 1], \mathcal{B}_{[0, 1]})$ with the standard Lebesgue probability measure $\lambda$ on $[0, 1] \subset \mathbb{R}$ ([[#^thm-1-11|Theorem 1.11]]). While $R_{\infty}$ (totally disconnected) and $[0, 1]$ (connected) are non-homeomorphic topologically, they are isomorphic as standard Borel probability spaces:

$$
(R_{\infty}, \mathcal{B}(R_{\infty}), \mu) \cong ([0, 1], \mathcal{B}_{[0, 1]}, \lambda)
$$

*Intuition:* Although cutting the unit interval into nested prime-radix subintervals leaves gaps at rational endpoints, those endpoints form a countable set of measure zero, allowing the Cantor series $\sum_{i=1}^{\infty} r_{i} / N_{i}$ to match $(R_{\infty}, \mu)$ and $([0, 1], \lambda)$ measure-for-measure almost everywhere.

*Proof:*

1. **Standard Borel Structure:** Because $R_{\infty}$ is compact and metrizable ([[#^thm-4-2|Theorem 4.2]]), $(R_{\infty}, \mathcal{B}(R_{\infty}), \mu)$ is a standard Borel probability space, as is $([0, 1], \mathcal{B}_{[0, 1]}, \lambda)$.

2. **Atomlessness and Cantor Series Realization:** For every singleton $\{x_{\infty}\} \subset R_{\infty}$, [[#^thm-4-6|Theorem 4.6]] and [[#^lem-4-1|Lemma 4.1]] give $\mu(\{x_{\infty}\}) \le \lim_{k \to \infty} \mu(B_{k}(\pi_{k}(x_{\infty}))) = \lim_{k \to \infty} N_{k}^{-1} = 0$. Because both $\mu$ and $\lambda$ are atomless standard Borel probability measures, Rohlin's Isomorphism Theorem guarantees full-measure Borel subsets $R_{\infty} \setminus N_{1}$ and $[0, 1] \setminus N_{2}$ ($\mu(N_{1}) = \lambda(N_{2}) = 0$) and a bimeasurable bijection $\Theta: R_{\infty} \setminus N_{1} \to [0, 1] \setminus N_{2}$ satisfying $\Theta_{*}\mu = \lambda$, explicitly realized modulo countable endpoints via the Cantor series expansion $x_{\infty} \mapsto \sum_{i=1}^{\infty} r_{i} / N_{i}$.

---

## 4.5 Trie Path Geometry and Branch Rewrite KL-Divergence ^sec-4-5


<br>

##### Definition 4.5: Least Common Ancestor and Structural Trie Path Metric ^def-4-5

*Parent Derivation:* [[#^def-1-4|Definition 1.4]], [[#^def-4-3|Definition 4.3]].

Let $\alpha = (r_{1}, \dots, r_{m}) \in \prod_{i=1}^{m} \mathbb{F}_{p_{i}}$ and $\beta = (s_{1}, \dots, s_{n}) \in \prod_{i=1}^{n} \mathbb{F}_{p_{i}}$ be two finite path nodes in $V(\mathcal{T})$. Define their shared prefix depth $h(\alpha, \beta)$ and Least Common Ancestor $\text{LCA}(\alpha, \beta) \in V(\mathcal{T})$ by:

$$
h(\alpha, \beta) \coloneq \max \left\{ j \in \{0, 1, \dots, \min(m, n)\} \;\middle\vert{}\; \forall i \in \{1, \dots, j\}, \, r_{i} = s_{i} \right\}
$$

$$
\text{LCA}(\alpha, \beta) \coloneq \begin{cases} \varepsilon & \text{if } h(\alpha, \beta) = 0 \\ (r_{1}, \dots, r_{h(\alpha, \beta)}) & \text{if } h(\alpha, \beta) \ge 1 \end{cases}
$$

Define the discrete structural path derivative (tree geodesic distance) $\Delta_{\mathcal{T}}: V(\mathcal{T}) \times V(\mathcal{T}) \to \mathbb{N}$ by:

$$
\Delta_{\mathcal{T}}(\alpha, \beta) \coloneq (m - h(\alpha, \beta)) + (n - h(\alpha, \beta)) = m + n - 2h(\alpha, \beta)
$$


<br>

##### Theorem 4.9: Graph Geodesic Metric Axioms for the Path Derivative ^thm-4-9

*Parent Derivation:* [[#^def-4-5|Definition 4.5]].

The structural path operator $\Delta_{\mathcal{T}}$ defines a metric on $V(\mathcal{T})$ satisfying non-negativity, identity of indiscernibles, symmetry, and the triangle inequality:

$$
\forall \alpha, \beta, \gamma \in V(\mathcal{T}), \quad \Delta_{\mathcal{T}}(\alpha, \gamma) \le \Delta_{\mathcal{T}}(\alpha, \beta) + \Delta_{\mathcal{T}}(\beta, \gamma)
$$

*Proof:*

1. **Positive Definiteness and Symmetry:** Since $h(\alpha, \beta) \le \min(m, n)$, $\Delta_{\mathcal{T}}(\alpha, \beta) \ge 0$, with equality if and only if $m = n = h(\alpha, \beta)$ (meaning $\alpha = \beta$); symmetry follows from $h(\alpha, \beta) = h(\beta, \alpha)$.

2. **Triangle Inequality via Prefix Ultrametricity:** Let $\gamma$ have length $k$, and set $h_{1} \coloneq h(\alpha, \beta)$, $h_{2} \coloneq h(\beta, \gamma)$, and $h_{3} \coloneq h(\alpha, \gamma)$. Because agreement along $\min(h_{1}, h_{2})$ coordinates passes transitively through $\beta$, we have $h_{3} \ge \min(h_{1}, h_{2})$. Since $h_{1} \le n$ and $h_{2} \le n$, we obtain $n - h_{1} - h_{2} \ge -\min(h_{1}, h_{2}) \ge -h_{3}$, yielding:

$$
\Delta_{\mathcal{T}}(\alpha, \beta) + \Delta_{\mathcal{T}}(\beta, \gamma) = m + k + 2(n - h_{1} - h_{2}) \ge m + k - 2h_{3} = \Delta_{\mathcal{T}}(\alpha, \gamma)
$$


<br>

##### Definition 4.6: Branching Transition Measures and Path Rewrite KL-Divergence ^def-4-6

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^thm-2-5|Theorem 2.5]], [[#^def-2-8|Definition 2.8]], [[#^def-4-5|Definition 4.5]].

Let $\alpha, \beta \in V(\mathcal{T})$ diverge at depth $h \coloneq h(\alpha, \beta)$ with $K \coloneq \max(\text{len}(\alpha), \text{len}(\beta))$. For each divergent level $i \in \{h + 1, \dots, K\}$, define on $\mathbb{F}_{p_{i}}$ the uniform reference Haar distribution $P_{i}(r) \coloneq \text{len}(p_{i})^{-1}$ and the regularized branch measure localized at target residue $t_{i} \in \mathbb{F}_{p_{i}}$ with $\epsilon \in (0, 1)$:

$$
Q_{i, \epsilon}(r) \coloneq \begin{cases} 1 - \epsilon & \text{if } r = t_{i} \\ \frac{\epsilon}{\text{len}(p_{i}) - 1} & \text{if } r \neq t_{i} \end{cases}
$$

Using $\log_{2}$ from [[#^thm-1-11|Theorem 1.11]], define the branch rewrite Kullback-Leibler divergence across levels $h + 1$ to $K$ by:

$$
D_{\text{KL}}(P \parallel Q_{\epsilon}) \coloneq \sum_{i=h+1}^{K} \sum_{r \in \mathbb{F}_{p_{i}}} P_{i}(r) \log_{2} \left( \frac{P_{i}(r)}{Q_{i, \epsilon}(r)} \right)
$$


<br>

##### Theorem 4.10: Exact Branch KL-Divergence Asymptotic Limit ^thm-4-10

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^thm-2-8|Theorem 2.8]], [[#^def-4-6|Definition 4.6]].

Along shared ancestor levels ($i \le h$), $D_{\text{KL}}(P_{i} \parallel P_{i}) = 0$, while across divergent branches ($h + 1 \le i \le K$) the singular divergence isolates the negative channel entropy sum:

$$
\lim_{\epsilon \to 0^{+}} \left[ D_{\text{KL}}(P \parallel Q_{\epsilon}) - \sum_{i=h+1}^{K} \frac{\text{len}(p_{i}) - 1}{\text{len}(p_{i})} \log_{2} \left( \frac{\text{len}(p_{i}) - 1}{\epsilon} \right) \right] = -\sum_{i=h+1}^{K} \log_{2} \text{len}(p_{i})
$$

*Proof:*

1. **Single-Channel Algebraic Expansion:** Set $q_{i} \coloneq \text{len}(p_{i})$. Expanding the $i$-th summand in [[#^def-4-6|Definition 4.6]] across $r = t_{i}$ ($1$ term) and $r \neq t_{i}$ ($q_{i} - 1$ identical terms) yields:

$$
D_{\text{KL}}(P_{i} \parallel Q_{i, \epsilon}) = \frac{1}{q_{i}} \log_{2} \left( \frac{1}{q_{i}(1 - \epsilon)} \right) + \frac{q_{i} - 1}{q_{i}} \log_{2} \left( \frac{q_{i} - 1}{q_{i} \epsilon} \right) = \frac{q_{i} - 1}{q_{i}} \log_{2} \left( \frac{q_{i} - 1}{\epsilon} \right) - \log_{2} q_{i} - \frac{1}{q_{i}} \log_{2}(1 - \epsilon)
$$

2. **Asymptotic Singular Subtraction:** Summing over $i = h + 1$ to $K$, subtracting the leading singular terms $\sum_{i=h+1}^{K} \frac{q_{i} - 1}{q_{i}} \log_{2} \left(\frac{q_{i} - 1}{\epsilon}\right)$, and taking $\epsilon \to 0^{+}$ (where $\log_{2}(1 - \epsilon) \to 0$ by [[#^thm-1-11|Theorem 1.11]]) leaves $-\sum_{i=h+1}^{K} \log_{2} \text{len}(p_{i})$.

---

## 4.6 Non-Archimedean Trie Differentiation and Riemann-Haar Integration ^sec-4-6


<br>

##### Definition 4.7: Ultrametric Valuation Step and Cylinder Basis Functions ^def-4-7

*Parent Derivation:* [[#^def-4-2|Definition 4.2]], [[#^def-4-4|Definition 4.4]].

For each depth $k \in \mathbb{N}_{\ge 1}$, define the canonical valuation step $\delta_{k} \coloneq N_{k}^{-1} = \prod_{i=1}^{k} \text{len}(p_{i})^{-1}$. For every cylinder vertex $\vec{r}_{k} \in \prod_{i=1}^{k} \mathbb{F}_{p_{i}}$, define the characteristic indicator function $\phi_{\vec{r}_{k}}: R_{\infty} \to \{0, 1\}$ by:

$$
\phi_{\vec{r}_{k}}(x) \coloneq \mathbf{1}_{B_{k}(\vec{r}_{k})}(x) = \begin{cases} 1 & \text{if } \pi_{k}(x) = \vec{r}_{k} \\ 0 & \text{otherwise} \end{cases}
$$


<br>

##### Theorem 4.11: van der Put Basis Expansion and Non-Archimedean Trie Derivative ^thm-4-11

*Parent Derivation:* [[#^thm-4-2|Theorem 4.2]], [[#^thm-4-5|Theorem 4.5]], [[#^def-4-7|Definition 4.7]].

Because $R_{\infty}$ is totally disconnected ([[#^thm-4-2|Theorem 4.2]]), classical Archimedean secant limits are undefined; instead, every continuous function $f: R_{\infty} \to \mathbb{R}$ admits a unique uniformly convergent expansion in locally constant cylinder indicators (van der Put basis):

$$
f(x) = b_{\varepsilon} + \sum_{k=1}^{\infty} \sum_{\vec{r}_{k} \in \prod_{i=1}^{k} \mathbb{F}_{p_{i}}} b_{\vec{r}_{k}} \phi_{\vec{r}_{k}}(x)
$$

with $\lim_{k \to \infty} \max_{\vec{r}_{k}} \lvert b_{\vec{r}_{k}} \rvert = 0$, and with the convention $\pi_{0}(x) \coloneq \varepsilon$, the non-Archimedean trie derivative at depth $k \in \mathbb{N}_{\ge 1}$ is defined by the zero-padded cylinder difference quotient:

$$
D_{\mathcal{T}}^{(k)} f(x) \coloneq \frac{f(x) - f\left(\pi_{k-1}(x) \frown (0, 0, \dots)\right)}{\delta_{k}}
$$

*Intuition:* Because every continuous function on compact $R_{\infty}$ is uniformly continuous, approximating $f$ by its values at zero-padded finite trie prefixes produces a telescoping sum of locally constant cylinder indicators whose depth-$k$ step variations define a natural ultrametric difference quotient.

*Proof:*

1. **Telescoping Locally Constant Approximations:** Define $f_{0}(x) \coloneq f(0)$ (where $0 = (0, 0, \dots) \in R_{\infty}$) and, at each depth $k \ge 1$, the locally constant approximation $f_{k}(x) \coloneq f(\pi_{k}(x) \frown (0, 0, \dots))$. By uniform continuity of $f$ on compact $R_{\infty}$ ([[#^thm-4-2|Theorem 4.2]]) and $\operatorname{diam}(B_{k}) \le \delta_{k} \to 0$ ([[#^thm-4-5|Theorem 4.5]]), $\sup_{x \in R_{\infty}} \lvert f(x) - f_{k}(x) \rvert \to 0$.

2. **Coefficient Extraction and Derivative Quotient:** Setting $b_{\varepsilon} \coloneq f(0)$ and $b_{\vec{r}_{k}} \coloneq f(\vec{r}_{k} \frown (0, 0, \dots)) - f(\vec{r}_{k-1} \frown (0, 0, \dots))$ (where $\vec{r}_{k-1}$ truncates $\vec{r}_{k}$ and $b_{\vec{r}_{k}} = 0$ if $r_{k} = 0$) telescopes $f_{K}(x) = b_{\varepsilon} + \sum_{k=1}^{K} \sum_{\vec{r}_{k}} b_{\vec{r}_{k}} \phi_{\vec{r}_{k}}(x)$ uniquely, while dividing local variation above the zero-padded ancestor $\pi_{k-1}(x) \frown (0, 0, \dots) \in R_{\infty}$ by $\delta_{k}$ yields $D_{\mathcal{T}}^{(k)} f(x)$.


<br>

##### Definition 4.8: Normalized Haar Measure and Profinite Riemann-Haar Integral ^def-4-8

*Parent Derivation:* [[#^lem-4-1|Lemma 4.1]], [[#^def-4-2|Definition 4.2]], [[#^def-4-7|Definition 4.7]].

Let $\mu$ be the unique normalized Haar probability measure on $(R_{\infty}, \mathcal{B}(R_{\infty}))$ established by [[#^lem-4-1|Lemma 4.1]], satisfying $\mu(B_{k}(\vec{r}_{k})) = N_{k}^{-1} = \delta_{k}$. For any continuous function $f: R_{\infty} \to \mathbb{R}$, define the Riemann-Haar integral over $R_{\infty}$ as the limit of finite cylinder Riemann sums:

$$
\int_{R_{\infty}} f(x) \, d\mu(x) \coloneq \lim_{k \to \infty} \sum_{\vec{r}_{k} \in \prod_{i=1}^{k} \mathbb{F}_{p_{i}}} f\left(x_{\vec{r}_{k}}^*\right) \cdot \mu\left(B_{k}(\vec{r}_{k})\right) = \lim_{k \to \infty} \frac{1}{N_{k}} \sum_{\vec{r}_{k} \in \prod_{i=1}^{k} \mathbb{F}_{p_{i}}} f\left(x_{\vec{r}_{k}}^*\right)
$$

where $x_{\vec{r}_{k}}^* \in B_{k}(\vec{r}_{k}) \subset R_{\infty}$ is an arbitrary sample point chosen inside each cylinder.


<br>

##### Theorem 4.12: Uniform Convergence and Sample-Point Independence of the Haar Integral ^thm-4-12

*Parent Derivation:* [[#^thm-4-2|Theorem 4.2]], [[#^thm-4-5|Theorem 4.5]], [[#^def-4-8|Definition 4.8]].

For every continuous function $f \in C(R_{\infty}, \mathbb{R})$, the Riemann-Haar limit in [[#^def-4-8|Definition 4.8]] exists, is finite, and is independent of the choice of cylinder sample points $x_{\vec{r}_{k}}^*$.

*Proof:*

1. **Uniform Continuity Oscillation Bound:** Because $R_{\infty}$ is compact ([[#^thm-4-2|Theorem 4.2]]), $f$ is uniformly continuous: for every $\epsilon > 0$, there exists $\eta > 0$ such that $d(x, y) < \eta \implies \lvert f(x) - f(y) \rvert < \epsilon$.

2. **Cauchy Convergence and Sample Independence:** By [[#^thm-4-5|Theorem 4.5]], choose $K \in \mathbb{N}_{\ge 1}$ such that $\operatorname{diam}(B_{k}(\vec{r}_{k})) \le \delta_{k} < \eta$ for all $k \ge K$. For any two sample choices $x_{\vec{r}_{k}}^*, x_{\vec{r}_{k}}^{**} \in B_{k}(\vec{r}_{k})$ and any $m \ge k \ge K$, averaging $\lvert f(x_{\vec{r}_{k}}^*) - f(x_{\vec{r}_{k}}^{**}) \rvert < \epsilon$ over all $N_{k}$ cylinders bounds both the sample discrepancy and the Cauchy difference between levels $k$ and $m$ strictly below $\epsilon$.

---

## 4.7 The Tripartite Equivalence and Functional Derivative Cascade ^sec-4-7


<br>

##### Definition 4.9: Cylinder Surprise Entropy and Dual Fisher Curvature Metrics ^def-4-9

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^def-2-4|Definition 2.4]], [[#^thm-2-8|Theorem 2.8]], [[#^def-4-7|Definition 4.7]], [[#^def-4-8|Definition 4.8]].

At resolution depth $k \in \mathbb{N}_{\ge 1}$, denote the cumulative trace capacity by $T(k) \coloneq N_{k} = \prod_{i=1}^{k} \text{len}(p_{i})$ and cylinder Haar volume by $\mu_{k} \coloneq \mu(B_{k}(\vec{r}_{k})) = \delta_{k} = T(k)^{-1}$. Using $\log_{2}$ and $\ln$ from [[#^thm-1-11|Theorem 1.11]], define:

1. **Expected Surprise (Shannon Entropy):** $H_{k} \coloneq \mathbb{E}_{\mu}[-\log_{2} \mu(B_{k})] = -\log_{2} \mu_{k} = \log_{2} T(k)$.

2. **Parameter-Scale Fisher Information Metric ($g_{\theta\theta}$):** Parameterizing the unnormalized scale-cone family $q_{j}(\theta) \coloneq \theta^{-1}$ over the fixed $N_{k}$-state support $j \in \{1, \dots, N_{k}\}$ (with total mass $\sum_{j=1}^{N_{k}} q_{j}(\theta) = N_{k}/\theta$, normalized at $\theta = N_{k}$) via natural logarithms ($\ln$) and evaluating at continuous scale $\theta = T(k) = N_{k}$ gives the radial Fisher scale metric:

$$
g_{\theta\theta} \coloneq \left. \sum_{j=1}^{N_{k}} q_{j}(\theta) \left( \frac{\partial \ln q_{j}(\theta)}{\partial \theta} \right)^{2} \right\vert_{\theta = T(k)} = N_{k} \cdot T(k)^{-1} \cdot \left(-T(k)^{-1}\right)^{2} = T(k)^{-2}
$$

3. **Resolution-Coordinate Fisher Metric ($g^{(k)}$):** Under coordinate inversion $\theta = x^{-1}$ evaluated at valuation step $dx = \delta_{k} = \mu_{k}$, the Jacobian metric transformation $g_{xx} = g_{\theta\theta}(d\theta/dx)^{2} = \theta^{-2}(-x^{-2})^{2} = x^{-2}$ defines the dual metric tensor component $g^{(k)} \coloneq \delta_{k}^{-2} = T(k)^{2}$.


<br>

##### Theorem 4.13: Master Tripartite Equivalence and Functional Derivative Cascade ^thm-4-13

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^thm-2-8|Theorem 2.8]], [[#^def-4-8|Definition 4.8]], [[#^def-4-9|Definition 4.9]].

At every resolution depth $k \in \mathbb{N}_{\ge 1}$ on $R_{\infty}$, the Haar measure $\mu(B_{k})$, Shannon entropy $H_{k}$, and Fisher curvature tensors $g^{(k)}, g_{\theta\theta}$ satisfy the non-circular tripartite identity:

$$
\mu(B_{k}) = 2^{-H_{k}} = \frac{1}{\sqrt{g^{(k)}}} = \sqrt{g_{\theta\theta}} = \delta_{k}
$$

Moreover, under continuous scale variation $T \mapsto \mu \mapsto H \mapsto g^{(k)}$, the differential operators satisfy exact chain-rule closure:

$$
\frac{d\mu}{dT} = -\mu^{2}, \qquad \frac{dH}{d\mu} = -\frac{1}{\mu \ln 2}, \qquad \frac{dg^{(k)}}{dH} = 2 \ln 2 \cdot g^{(k)} \implies \frac{dg^{(k)}}{d\mu} = \frac{dg^{(k)}}{dH} \cdot \frac{dH}{d\mu} = -\frac{2}{\mu^{3}}
$$

*Intuition:* Cylinder volume $\mu(B_{k})$, Shannon surprise $H_{k}$, and statistical distinguishability $g^{(k)}$ are three algebraic encodings of the single state-space count $T(k) = N_{k}$, so varying $T(k)$ induces an exact logarithmic-power chain rule whose $\ln 2$ conversion factors cancel identically.

*Proof:*

1. **Tripartite Algebraic Closure:** From [[#^def-4-9|Definition 4.9]], $H_{k} = \log_{2} T(k) \implies T(k) = 2^{H_{k}}$ ([[#^thm-1-11|Theorem 1.11]]). Substituting $T(k) = 2^{H_{k}}$ into $\mu(B_{k}) = T(k)^{-1}$, $g^{(k)} = T(k)^{2}$, and $g_{\theta\theta} = T(k)^{-2}$ yields $\mu(B_{k}) = 2^{-H_{k}}$, $g^{(k)} = 2^{2H_{k}} = \mu(B_{k})^{-2}$, and $g_{\theta\theta} = 2^{-2H_{k}} = \mu(B_{k})^{2}$.

2. **Differential Cascade Derivation:** Differentiating $\mu(T) = T^{-1}$ gives $\frac{d\mu}{dT} = -T^{-2} = -\mu^{2}$. Differentiating $H(\mu) = -\frac{\ln \mu}{\ln 2}$ gives $\frac{dH}{d\mu} = -\frac{1}{\mu \ln 2}$. Differentiating $g^{(k)}(H) = 2^{2H} = e^{2H \ln 2}$ gives $\frac{dg^{(k)}}{dH} = 2 \ln 2 \cdot g^{(k)}$.

3. **Chain-Rule Verification:** Multiplying the intermediate operators yields $\frac{dg^{(k)}}{dH} \cdot \frac{dH}{d\mu} = (2 \ln 2 \cdot \mu^{-2}) \left(-\frac{1}{\mu \ln 2}\right) = -2\mu^{-3} = \frac{d}{d\mu}(\mu^{-2})$, confirming exact algebraic and differential closure.

**Emergent Isomorphism Bridge 5 (Stone-Cantor Topology, Non-Archimedean Analysis, and Information Geometry):** Classical mathematics treats the Cantor ternary set $\mathbf{2}^{\mathbb{N}}$, Lebesgue measure on $[0, 1]$, Mahler–van der Put $p$-adic analysis, and Amari's Fisher information metric on statistical manifolds as distinct subjects. Under [[#^def-0-1|Definition 0.1]], [[#^thm-4-2|Theorem 4.2]], [[#^thm-4-8|Theorem 4.8]], [[#^thm-4-11|Theorem 4.11]], and [[#^thm-4-13|Theorem 4.13]] reveal that all four structures emerge simultaneously on the infinite primorial trie $\mathcal{T}$: topologically $R_{\infty}$ is the Cantor space $\mathbf{2}^{\mathbb{N}}$; measure-theoretically $(R_{\infty}, \mu)$ is the Lebesgue interval $([0, 1], \lambda)$; analytically continuous functions expand in van der Put cylinder indicators; and geometrically the inverse square of cylinder resolution $\delta_{k}^{-2}$ is the exact Fisher information curvature $g^{(k)}$.

*Exit Handoff:* We have constructed the profinite limit ring $R_{\infty}$, its Cantor and Rohlin continuum dualities, and its non-Archimedean differential and Fisher-curvature calculus. However, because $R_{\infty} \cong \prod_{i=1}^{\infty} \mathbb{F}_{p_{i}}$ is built strictly from square-free primorial moduli $N_{k}$, it discards vertical prime-power towers $p^{m}$ ($m \ge 2$)—motivating the emergence of $\pi$ and $e$, local $p$-adic completions $\mathbb{Q}_{p}$, and the global restricted adele ring $\mathbb{A}_{\mathbb{Q}}$ in Section 5.

---

---

# Section 5: Emergent Transcendentals ($\pi, e$) and Global Adelic Self-Duality ^sec-5

*Entry Primer:* In Section 4, taking the projective limit across square-free primorial rings $R_{k} = \mathbb{Z}/N_{k}\mathbb{Z}$ produced the Cantor-Stone space $R_{\infty}$ and its non-Archimedean trie calculus. However, square-free moduli omit vertical prime-power towers $p^{m}$ ($m \ge 2$), and our global architecture has not yet revealed how the fundamental transcendental constants $\pi$ and $e$ emerge from prime statistics or how the Archimedean continuum $\mathbb{R}$ unifies with every prime completion into a single self-dual arithmetic space. In this section, we extract $\pi$ from two-dimensional prime non-collision density, extract $e$ from one-dimensional primorial entropy density, construct vertical $p$-adic towers $\mathbb{Q}_{p}$, and fuse all completions into the Pontryagin self-dual restricted adele ring $\mathbb{A}_{\mathbb{Q}}$.

## 5.1 Two-Dimensional Toroidal Non-Collision and the Circle Constant $\pi$ ^sec-5-1

In Section 2, single-coordinate projections on $\Omega_{k} = \mathbb{Z}/N_{k}\mathbb{Z}$ were proven statistically independent with zero mutual information. Extending the primorial state space to two-dimensional coordinate pairs $(U, V)$ isolates the geometric non-collision density that governs the Euclidean circle constant $\pi$.


<br>

##### Definition 5.1: Bivariate Toroidal State Space and Prime Collision Events ^def-5-1

*Parent Derivation:* [[#^def-2-4|Definition 2.4]], [[#^def-2-6|Definition 2.6]].

For any primorial stage $k \in \mathbb{N}_{\ge 1}$, define the bivariate toroidal state space $\Omega_{k}^{2} \coloneq \Omega_{k} \times \Omega_{k} = (\mathbb{Z}/N_{k}\mathbb{Z})^{2}$ of cardinality $N_{k}^{2}$ equipped with the uniform product counting measure $\mathbb{P}_{k}(A) \coloneq \lvert A \rvert / N_{k}^{2}$. For each prime channel $i \in \{1, \dots, k\}$, define the joint collision event $C_{i}$ and non-collision event $E_{i}$ by:

$$
C_{i} \coloneq \left\{ (u, v) \in \Omega_{k}^{2} \;\middle\vert{}\; u \equiv 0 \pmod{\text{len}(p_{i})} \land v \equiv 0 \pmod{\text{len}(p_{i})} \right\}
$$

$$
E_{i} \coloneq \Omega_{k}^{2} \setminus C_{i}
$$


<br>

##### Theorem 5.1: Exact Two-Dimensional Non-Collision Density ^thm-5-1

*Parent Derivation:* [[#^thm-2-6|Theorem 2.6]], [[#^thm-2-7|Theorem 2.7]], [[#^def-5-1|Definition 5.1]].

The probability $\rho_{k}$ that a uniformly sampled pair $(U, V) \in \Omega_{k}^{2}$ avoids simultaneous divisibility across all $k$ prime channels factorizes with zero cross-channel error:

$$
\rho_{k} \coloneq \mathbb{P}_{k}\left( \bigcap_{i=1}^{k} E_{i} \right) = \prod_{i=1}^{k} \left( 1 - \frac{1}{\text{len}(p_{i})^{2}} \right)
$$

*Proof:*

1. **Single-Channel Collision Probability:** By [[#^thm-2-6|Theorem 2.6]] and [[#^def-5-1|Definition 5.1]], $U \bmod \text{len}(p_{i})$ and $V \bmod \text{len}(p_{i})$ are independent uniform random variables on $\mathbb{Z}/\text{len}(p_{i})\mathbb{Z}$, yielding $\mathbb{P}_{k}(C_{i}) = \text{len}(p_{i})^{-1} \cdot \text{len}(p_{i})^{-1} = \text{len}(p_{i})^{-2}$ and $\mathbb{P}_{k}(E_{i}) = 1 - \text{len}(p_{i})^{-2}$.

2. **Mutual Independence Across Prime Gears:** Because distinct prime channels satisfy $I(X_{i}; X_{j}) = 0$ ([[#^thm-2-7|Theorem 2.7]]), the bivariate events $\{E_{1}, \dots, E_{k}\}$ are mutually independent under $\mathbb{P}_{k}$, so $\mathbb{P}_{k}\left(\bigcap_{i=1}^{k} E_{i}\right) = \prod_{i=1}^{k} \mathbb{P}_{k}(E_{i}) = \prod_{i=1}^{k} (1 - \text{len}(p_{i})^{-2})$.


<br>

##### Lemma 5.2a: Non-Circular Archimedean Fourier Evaluation of $\zeta(2)$ ^lem-5-2a

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]].

Defining $\pi > 0$ analytically and independently of prime numbers via the power-series exponential of [[#^thm-1-11|Theorem 1.11]] as the minimal positive root of $\sin(x) \coloneq (e^{ix} - e^{-ix})/(2i) = 0$ on $\mathbb{R}_{> 0}$, the Riemann zeta series at $s = 2$ evaluates identically to:

$$
\zeta(2) \coloneq \sum_{n=1}^{\infty} \frac{1}{n^{2}} = \frac{\pi^{2}}{6}
$$

*Proof:*

1. **Fourier Expansion of the Archimedean Parabola:** Consider the continuous periodic extension of $f(x) \coloneq x^{2}$ on $[-\pi, \pi]$. By orthogonality of $\{\cos(nx)\}_{n=0}^{\infty}$ on $[-\pi, \pi]$, its Fourier cosine coefficients evaluate via integration by parts to:

$$
a_{0} = \frac{1}{\pi} \int_{-\pi}^{\pi} x^{2} \, dx = \frac{2\pi^{2}}{3}, \qquad a_{n} = \frac{1}{\pi} \int_{-\pi}^{\pi} x^{2} \cos(nx) \, dx = \frac{4(-1)^{n}}{n^{2}} \quad (n \ge 1)
$$

2. **Boundary Evaluation at $x = \pi$:** Because $f$ is piecewise smooth and continuous at $x = \pi$, Dirichlet's Fourier convergence theorem yields $\pi^{2} = f(\pi) = \frac{a_{0}}{2} + \sum_{n=1}^{\infty} a_{n} \cos(n\pi) = \frac{\pi^{2}}{3} + 4 \sum_{n=1}^{\infty} \frac{1}{n^{2}}$, and solving for the series gives $\zeta(2) = \pi^{2} / 6$ without invoking primes.


<br>

##### Theorem 5.2: Radical Inversion Identity for $\pi$ ^thm-5-2

*Parent Derivation:* [[#^thm-2-2b|Theorem 2.2b]], [[#^thm-5-1|Theorem 5.1]], [[#^lem-5-2a|Lemma 5.2a]].

In the projective limit $k \to \infty$, the inverse non-collision density recovers the Euclidean circle constant $\pi$:

$$
\pi = \lim_{k \to \infty} \sqrt{ \frac{6}{\prod_{i=1}^{k} \left( 1 - \text{len}(p_{i})^{-2} \right)} }
$$

*Proof:*

1. **Euler Product Factorization:** By unique prime word factorization in $(\Sigma^*, \cdot, \text{flatMap})$ ([[#^thm-2-2b|Theorem 2.2b]]) and absolute convergence of $\sum_{n=1}^{\infty} n^{-2}$, expanding each geometric factor $(1 - \text{len}(p_{i})^{-2})^{-1} = \sum_{m=0}^{\infty} \text{len}(p_{i})^{-2m}$ yields $\lim_{k \to \infty} \rho_{k}^{-1} = \prod_{i=1}^{\infty} (1 - \text{len}(p_{i})^{-2})^{-1} = \sum_{n=1}^{\infty} n^{-2} = \zeta(2)$.

2. **Radical Extraction:** Substituting $\zeta(2) = \pi^{2} / 6$ from [[#^lem-5-2a|Lemma 5.2a]] into $\lim_{k \to \infty} \rho_{k} = 6 / \pi^{2}$ gives $\pi^{2} = \lim_{k \to \infty} (6 / \rho_{k})$, and taking positive square roots via continuity of $t \mapsto \sqrt{t}$ on $\mathbb{R}_{> 0}$ establishes the limit.


<br>

##### Theorem 5.3: Second Primorial Demultiplexing and Catalan-Mihăilescu Cancellation ^thm-5-3

*Parent Derivation:* [[#^def-2-3|Definition 2.3]], [[#^def-2-4|Definition 2.4]], [[#^def-3-6|Definition 3.6]], [[#^thm-5-2|Theorem 5.2]].

Identifying the numerator $6$ as the second primorial magnitude $N_{2} = \text{len}(p_{1}) \cdot \text{len}(p_{2}) = 2 \times 3$ and applying the consecutive prime-power identities $\text{len}(p_{1})^{2} - 1 = 3 = \text{len}(p_{2})$ and $\text{len}(p_{2})^{2} - 1 = 8 = \text{len}(p_{1})^{3}$ collapses the base kernel to $\text{len}(p_{2})^{2} = 9$, isolating the canonical representation:

$$
\pi = \frac{3}{\sqrt{ \prod_{p \in \mathcal{P}_{\ge 5}} \left( 1 - \frac{1}{\text{len}(p)^{2}} \right) }}
$$

*Intuition:* Evaluating the two-dimensional non-collision density across the first two primes $2$ and $3$ yields $\rho_{2} = (3/4)(8/9) = 2/3$, which cancels the binary factor $2$ out of the numerator $N_{2} = 6$ and leaves the exact square $\text{len}(p_{2})^{2} = 9$ under the radical.

*Proof:*

1. **Telescoping Base Non-Collision Density:** Evaluating [[#^thm-5-1|Theorem 5.1]] at $k = 2$ with $\text{len}(p_{1}) = 2$ and $\text{len}(p_{2}) = 3$ ([[#^def-2-3|Definition 2.3]]) gives:

$$
\rho_{2} = \left( \frac{\text{len}(p_{1})^{2} - 1}{\text{len}(p_{1})^{2}} \right) \left( \frac{\text{len}(p_{2})^{2} - 1}{\text{len}(p_{2})^{2}} \right) = \left( \frac{\text{len}(p_{2})}{\text{len}(p_{1})^{2}} \right) \left( \frac{\text{len}(p_{1})^{3}}{\text{len}(p_{2})^{2}} \right) = \frac{\text{len}(p_{1})}{\text{len}(p_{2})} = \frac{2}{3}
$$

2. **Annihilation of $p_{1}$ and Kernel Extraction:** Dividing $N_{2} = \text{len}(p_{1}) \cdot \text{len}(p_{2}) = 6$ ([[#^def-2-4|Definition 2.4]]) by $\rho_{2} = \text{len}(p_{1}) / \text{len}(p_{2})$ cancels $\text{len}(p_{1})$ identically to yield $N_{2} / \rho_{2} = \text{len}(p_{2})^{2} = 9$, so substituting into [[#^thm-5-2|Theorem 5.2]] and extracting $\sqrt{9} = 3$ isolates the higher prime product over $\mathcal{P}_{\ge 5}$ ([[#^def-3-6|Definition 3.6]]).

---

## 5.2 Longitudinal Information Density and Euler's Number $e$ ^sec-5-2

Whereas $\pi$ governs two-dimensional transverse coprime visibility across pairs of prime channels, Euler's number $e \coloneq \exp(1)$ emerges as the one-dimensional longitudinal growth base relating maximal prime word length to primorial Shannon capacity.


<br>

##### Definition 5.2: Chebyshev First Function and Specific Natural Entropy Density ^def-5-2

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^def-2-4|Definition 2.4]], [[#^thm-2-8|Theorem 2.8]].

For any real bound $x \in \mathbb{R}_{\ge 2}$, define Chebyshev's first function $\theta(x) \coloneq \sum_{p \in \mathcal{P}, \, \text{len}(p) \le x} \ln \text{len}(p)$ using $\ln$ from [[#^thm-1-11|Theorem 1.11]]. At primorial stage $k \in \mathbb{N}_{\ge 1}$, converting the total channel entropy of [[#^thm-2-8|Theorem 2.8]] from bits to natural units (nats) gives $H_{\text{nat}}(\Omega_{k}) = H(X_{1}, \dots, X_{k}) \ln 2 = \ln N_{k} = \theta(\text{len}(p_{k}))$, and we define the specific entropy density per unit length of the maximal active prime rotor by:

$$
\sigma_{k} \coloneq \frac{H_{\text{nat}}(\Omega_{k})}{\text{len}(p_{k})} = \frac{\theta(\text{len}(p_{k}))}{\text{len}(p_{k})}
$$


<br>

##### Lemma 5.4a: Non-Circular Asymptotic Density of Chebyshev's Function ^lem-5-4a

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^thm-2-2b|Theorem 2.2b]], [[#^def-5-2|Definition 5.2]].

In the large-scale limit $x \to \infty$, Chebyshev's first function satisfies the Prime Number Theorem asymptotic $\lim_{x \to \infty} \theta(x) / x = 1$.

*Proof:*

1. **Legendre Factorial Decomposition into von Mangoldt Sums:** Define the von Mangoldt function $\Lambda(n) \coloneq \ln \text{len}(p)$ if $n = \text{len}(p)^{m}$ ($m \in \mathbb{N}_{\ge 1}$) and $0$ otherwise, together with Chebyshev's second function $\psi_{\text{Ch}}(x) \coloneq \sum_{n \le x} \Lambda(n)$. By unique prime factorization ([[#^thm-2-2b|Theorem 2.2b]]), Legendre's valuation formula for $n!$ gives $\ln(n!) = \sum_{m=1}^{n} \psi_{\text{Ch}}(n/m)$.

2. **Higher-Power Tail Suppression:** Expanding $\psi_{\text{Ch}}(x) = \sum_{m=1}^{\lfloor \log_{2} x \rfloor} \theta(x^{1/m})$ and bounding $\theta(x^{1/m}) \le x^{1/2} \ln(x^{1/2})$ for $m \ge 2$ yields $\psi_{\text{Ch}}(x) - \theta(x) = \mathcal{O}(\sqrt{x} \ln^{2} x)$, so $\lim_{x \to \infty} \theta(x)/x = \lim_{x \to \infty} \psi_{\text{Ch}}(x)/x$.

3. **Tauberian Pole Residue at $s = 1$:** Because the Dirichlet series $\sum_{n=1}^{\infty} \Lambda(n) n^{-s} = -\zeta'(s) / \zeta(s)$ has a simple pole at $s = 1$ with residue $1$ and no zeros on $\operatorname{Re}(s) = 1$, the Wiener-Ikehara Tauberian theorem establishes $\lim_{x \to \infty} \psi_{\text{Ch}}(x) / x = 1$, whence $\lim_{x \to \infty} \theta(x) / x = 1$.


<br>

##### Theorem 5.4: Asymptotic Primorial Root Identity for $e$ and Holographic Duality ^thm-5-4

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^def-2-3|Definition 2.3]], [[#^def-5-2|Definition 5.2]], [[#^lem-5-4a|Lemma 5.4a]], [[#^thm-5-3|Theorem 5.3]].

The $\text{len}(p_{k})$-th root of the primorial state-space magnitude $N_{k}$ converges to Euler's number $e$, establishing an asymptotic information density of exactly $1$ nat per unit length of the maximal prime channel:

$$
e = \lim_{k \to \infty} \left( N_{k} \right)^{\frac{1}{\text{len}(p_{k})}}
$$

*Proof:*

1. **Logarithmic Reduction to Specific Entropy:** For each $k \in \mathbb{N}_{\ge 1}$, taking principal natural logarithms of $L_{k} \coloneq (N_{k})^{1/\text{len}(p_{k})} \in \mathbb{R}_{> 0}$ via [[#^def-5-2|Definition 5.2]] and [[#^thm-1-11|Theorem 1.11]] gives $\ln L_{k} = \frac{\ln N_{k}}{\text{len}(p_{k})} = \frac{\theta(\text{len}(p_{k}))}{\text{len}(p_{k})} = \sigma_{k}$.

2. **Exponential Continuity Lift:** Because $\lim_{k \to \infty} \text{len}(p_{k}) = \infty$ by [[#^def-2-3|Definition 2.3]], [[#^lem-5-4a|Lemma 5.4a]] yields $\lim_{k \to \infty} \ln L_{k} = 1$, and continuity of $\exp: \mathbb{R} \to \mathbb{R}_{> 0}$ ([[#^thm-1-11|Theorem 1.11]]) gives $\lim_{k \to \infty} L_{k} = \exp(1) = e$.

3. **Longitudinal-Transverse Constant Duality:** Together with [[#^thm-5-3|Theorem 5.3]], $e$ governs one-dimensional radial state-space expansion along the prime axis ($\mu(B_{k}) = N_{k}^{-1} \sim e^{-\text{len}(p_{k})}$), whereas $\pi$ governs two-dimensional transverse rotational normalization across coprime pairs.

---

## 5.3 Local $p$-adic Towers and the Restricted Adele Ring $\mathbb{A}_{\mathbb{Q}}$ ^sec-5-3

To unify the Archimedean continuum $\mathbb{R}$ ([[#^thm-1-11|Theorem 1.11]]) with every non-Archimedean prime completion into a single locally compact ring, we project rational prime-power valuations onto vertical prime towers and restrict their infinite direct product.


<br>

##### Lemma 5.5a: Localized Prime-Power Valuations and Finite Denominator Support ^lem-5-5a

*Parent Derivation:* [[#^def-1-7|Definition 1.7]], [[#^thm-1-10|Theorem 1.10]], [[#^thm-1-11|Theorem 1.11]], [[#^thm-2-2b|Theorem 2.2b]].

For every prime word $P \in \mathcal{P}$ of scalar length $p \coloneq \text{len}(P)$, the unique prime word decomposition of [[#^thm-2-2b|Theorem 2.2b]] induces an additive discrete valuation $v_{p}: \mathbb{Q}^\times \to \mathbb{Z}$ satisfying $v_{p}(q_{1} \cdot_{\mathbb{Q}} q_{2}) = v_{p}(q_{1}) + v_{p}(q_{2})$ and $v_{p}(q_{1} +_{\mathbb{Q}} q_{2}) \ge \min(v_{p}(q_{1}), v_{p}(q_{2}))$, such that every $q \in \mathbb{Q}^\times$ admits the unique global prime-power expansion $q = \pm \prod_{p \in \mathcal{P}} p^{v_{p}(q)}$ with finite negative support $\operatorname{supp}_{\mathcal{P}}^{-}(q) = \{p \in \mathcal{P} \mid v_{p}(q) < 0\}$.

*Proof:*

1. **Extension of Prime Multiplicity to $\mathbb{Q}^\times$:** For any non-zero integer $a \in \mathbb{Z} \setminus \{0_{\mathbb{Z}}\}$ with magnitude $\lvert a \rvert \in \mathbb{N}_{\ge 1}$, define $v_{p}(a) \in \mathbb{N}$ as the exact exponent of $P$ in the unique prime word factorization of $\Xi^{\lvert a \rvert}$ ([[#^thm-2-2b|Theorem 2.2b]]). Setting $v_{p}([(a, b)]_{\times}) \coloneq v_{p}(a) - v_{p}(b) \in \mathbb{Z}$ is independent of fraction representatives by [[#^def-1-7|Definition 1.7]] and [[#^thm-1-10|Theorem 1.10]].

2. **Valuation Homomorphism and Finite Support:** Multiplicativity and the ultrametric sum inequality inherit directly from unique factorization on $\mathbb{N}_{\ge 1}$, while finiteness of $\operatorname{supp}_{\mathcal{P}}^{-}(q)$ follows from [[#^thm-2-2b|Theorem 2.2b]].


<br>

##### Definition 5.3: Vertical Prime-Power Towers and Compact $p$-adic Integer Rings ^def-5-3

*Parent Derivation:* [[#^def-1-3|Definition 1.3]], [[#^thm-1-6|Theorem 1.6]], [[#^def-2-2|Definition 2.2]], [[#^lem-4-1|Lemma 4.1]].

Fix a prime word $P \in \mathcal{P}$ of scalar prime length $p \coloneq \text{len}(P)$. Define the vertical prime-power words recursively by $P^{(1)} \coloneq P$ and $P^{(n)} \coloneq \text{flatMap}(P^{(n-1)}, P)$ for $n \in \mathbb{N}_{\ge 2}$, so $\text{len}(P^{(n)}) = p^{n}$ by [[#^thm-1-6|Theorem 1.6]]. The ring of $p$-adic integers is the projective limit:

$$
\mathbb{Z}_{p} \coloneq \varprojlim_{n} \left( \mathbb{Z} / \text{len}(P^{(n)})\mathbb{Z} \right) = \varprojlim_{n} \left( \mathbb{Z} / p^{n}\mathbb{Z} \right)
$$

By [[#^lem-4-1|Lemma 4.1]], $\mathbb{Z}_{p}$ is a compact, Hausdorff, totally disconnected topological ring carrying a unique normalized Haar probability measure $\mu_{p}$ satisfying $\mu_{p}(p^{m}\mathbb{Z}_{p}) = p^{-m}$ for all $m \in \mathbb{N}$.


<br>

##### Definition 5.4: Non-Archimedean Local Fields and Localized Signed Tri-Strings ^def-5-4

*Parent Derivation:* [[#^def-1-7|Definition 1.7]], [[#^thm-1-10|Theorem 1.10]], [[#^def-3-4|Definition 3.4]], [[#^lem-5-5a|Lemma 5.5a]], [[#^def-5-3|Definition 5.3]].

For each prime $p \in \mathcal{P}$, define the $p$-adic absolute value on $\mathbb{Q}$ via [[#^lem-5-5a|Lemma 5.5a]] by $\lvert q \rvert_{p} \coloneq p^{-v_{p}(q)}$ ($\lvert 0 \rvert_{p} \coloneq 0$) and form the metric completion $\mathbb{Q}_{p} \coloneq \overline{\mathbb{Q}}_{\lvert \cdot \rvert_{p}} = \mathbb{Z}_{p}[p^{-1}] = \operatorname{Frac}(\mathbb{Z}_{p})$. Under [[#^def-3-4|Definition 3.4]], every element $x_{p} \in \mathbb{Q}_{p}$ is represented as a localized signed Tri-String $[-e, P, u]$ ($e \in \mathbb{N}$, $u \in \mathbb{Z}_{p}$) corresponding to $p^{-e} u$, with $\mathbb{Z}_{p} = \{x_{p} \in \mathbb{Q}_{p} \mid \lvert x_{p} \rvert_{p} \le 1\}$ open and compact in $\mathbb{Q}_{p}$ and unit shell $\mathbb{Z}_{p}^\times \coloneq \mathbb{Z}_{p} \setminus p\mathbb{Z}_{p}$.


<br>

##### Remark 5.1: Category Guard — Rejection of the Unrestricted Product ^rem-5-1

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^def-5-3|Definition 5.3]], [[#^def-5-4|Definition 5.4]].

The naive unrestricted Cartesian product $\Pi \coloneq \mathbb{R} \times \prod_{p \in \mathcal{P}} \mathbb{Q}_{p}$ equipped with the product topology is topologically invalid as an adelic arithmetic space: every basic open neighborhood of $0$ contains infinitely many full factors $\mathbb{Q}_{p}$, none of which is compact ($\mu_{p}(\mathbb{Q}_{p}) = \infty$), so $\Pi$ is not locally compact and the diagonal image of $\mathbb{Q}$ fails to be discrete.


<br>

##### Definition 5.5: The Restricted Adele Ring ^def-5-5

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^lem-4-1|Lemma 4.1]], [[#^def-5-4|Definition 5.4]], [[#^rem-5-1|Remark 5.1]].

Define the finite adele ring $\mathbb{A}_{\mathbb{Q}, \text{fin}}$ and the global restricted adele ring $\mathbb{A}_{\mathbb{Q}}$ as the restricted direct product with respect to the compact open subrings $\mathbb{Z}_{p} \subset \mathbb{Q}_{p}$:

$$
\mathbb{A}_{\mathbb{Q}, \text{fin}} \coloneq {\prod_{p \in \mathcal{P}}}' (\mathbb{Q}_{p}, \mathbb{Z}_{p}) \coloneq \left\{ (x_{p})_{p \in \mathcal{P}} \in \prod_{p \in \mathcal{P}} \mathbb{Q}_{p} \;\middle\vert{}\; x_{p} \in \mathbb{Z}_{p} \text{ for all but finitely many } p \in \mathcal{P} \right\}
$$

$$
\mathbb{A}_{\mathbb{Q}} \coloneq \mathbb{R} \times \mathbb{A}_{\mathbb{Q}, \text{fin}} = \mathbb{R} \times {\prod_{p \in \mathcal{P}}}' (\mathbb{Q}_{p}, \mathbb{Z}_{p})
$$

Equip $\mathbb{A}_{\mathbb{Q}}$ with the inductive limit topology over cylinder subrings $\mathbb{A}_{\mathbb{Q}}(S) \coloneq \mathbb{R} \times \prod_{p \in S} \mathbb{Q}_{p} \times \prod_{p \notin S} \mathbb{Z}_{p}$ indexed by finite sets $S \subset \mathcal{P}$. By Tychonoff's Theorem ([[#^lem-4-1|Lemma 4.1]]), each $\prod_{p \notin S} \mathbb{Z}_{p}$ is compact, making $\mathbb{A}_{\mathbb{Q}}$ a locally compact Hausdorff topological ring under componentwise addition and multiplication.

*Notation Rationale:* The blackboard bold $\mathbb{A}_{\mathbb{Q}}$ stands for the *adele* ring (from French *idèle additif*), assembling Archimedean and $p$-adic completions into a single locally compact phase space.


<br>

##### Theorem 5.5: Discreteness of the Rational Diagonal Embedding ^thm-5-5

*Parent Derivation:* [[#^lem-5-5a|Lemma 5.5a]], [[#^def-5-5|Definition 5.5]].

The diagonal embedding $\Delta: \mathbb{Q} \to \mathbb{A}_{\mathbb{Q}}$ defined by $\Delta(q) \coloneq (q, q, q, \dots)$ maps $\mathbb{Q}$ into $\mathbb{A}_{\mathbb{Q}}$ as a discrete additive subgroup.

*Proof:*

1. **Restricted Product Membership:** For every $q \in \mathbb{Q}^\times$, [[#^lem-5-5a|Lemma 5.5a]] guarantees that $v_{p}(q) < 0$ holds only on the finite set $\operatorname{supp}_{\mathcal{P}}^{-}(q)$, so $q \in \mathbb{Z}_{p}$ for all $p \notin \operatorname{supp}_{\mathcal{P}}^{-}(q)$ and hence $\Delta(q) \in \mathbb{A}_{\mathbb{Q}}$ by [[#^def-5-5|Definition 5.5]].

2. **Isolated Identity Neighborhood:** Define the open neighborhood $U \coloneq (-1, 1) \times \prod_{p \in \mathcal{P}} \mathbb{Z}_{p} \subset \mathbb{A}_{\mathbb{Q}}$. If $\Delta(q) \in U \cap \Delta(\mathbb{Q})$, then $q \in \mathbb{Z}_{p}$ for all $p \in \mathcal{P}$ implies $v_{p}(q) \ge 0$ everywhere, forcing $q \in \mathbb{Z}$, while $\lvert q \rvert_{\infty} < 1$ forces $q = 0$, proving $U \cap \Delta(\mathbb{Q}) = \{0\}$ and discreteness of $\Delta(\mathbb{Q})$.


<br>

##### Theorem 5.6: Cocompactness of the Adelic Quotient and Fundamental Domain ^thm-5-6

*Parent Derivation:* [[#^thm-2-4|Theorem 2.4]], [[#^def-5-5|Definition 5.5]], [[#^thm-5-5|Theorem 5.5]].

The quotient topological group $\mathbb{A}_{\mathbb{Q}} / \Delta(\mathbb{Q})$ is compact, admitting the strict fundamental domain $D \coloneq [0, 1) \times \prod_{p \in \mathcal{P}} \mathbb{Z}_{p}$ such that $\mathbb{A}_{\mathbb{Q}} = \bigsqcup_{q \in \mathbb{Q}} (\Delta(q) + D)$.

*Intuition:* Just as subtracting an integer shifts any real number into $[0, 1)$, subtracting a rational number built via the Chinese Remainder Theorem simultaneously cancels the fractional parts of all finitely many non-integral $p$-adic coordinates, trapping the remainder inside the compact cylinder $[0, 1) \times \prod_{p \in \mathcal{P}} \mathbb{Z}_{p}$.

*Proof:*

1. **Principal Part Elimination via Strong Approximation:** Let $x = (x_{\infty}, (x_{p})_{p \in \mathcal{P}}) \in \mathbb{A}_{\mathbb{Q}}$. The singular set $S \coloneq \{p \in \mathcal{P} \mid x_{p} \notin \mathbb{Z}_{p}\}$ is finite ([[#^def-5-5|Definition 5.5]]), and each $x_{p}$ ($p \in S$) has a finite principal part $r_{p} = \sum_{j=-M_{p}}^{-1} a_{j, p} p^{j} \in \mathbb{Z}[p^{-1}]$. By the Chinese Remainder Theorem on coprime prime-power denominators (generalizing [[#^thm-2-4|Theorem 2.4]]), there exists $q_{1} \in \mathbb{Q}$ with $v_{p}(q_{1} - r_{p}) \ge 0$ for all $p \in S$ and $v_{\ell}(q_{1}) \ge 0$ for all $\ell \notin S$, giving $x - \Delta(q_{1}) \in \mathbb{R} \times \prod_{p \in \mathcal{P}} \mathbb{Z}_{p}$.

2. **Archimedean Unit Interval Reduction:** Setting $n \coloneq \lfloor x_{\infty} - q_{1} \rfloor \in \mathbb{Z}$ and $q \coloneq q_{1} + n \in \mathbb{Q}$ preserves $x_{p} - q \in \mathbb{Z}_{p}$ for all $p \in \mathcal{P}$ while shifting $x_{\infty} - q \in [0, 1)$, so $x - \Delta(q) \in D$. By [[#^thm-5-5|Theorem 5.5]], distinct translates $\Delta(q) + D$ are disjoint, and continuity of $\mathbb{A}_{\mathbb{Q}} \to \mathbb{A}_{\mathbb{Q}} / \Delta(\mathbb{Q})$ maps the compact closure $\overline{D} = [0, 1] \times \prod_{p \in \mathcal{P}} \mathbb{Z}_{p}$ onto $\mathbb{A}_{\mathbb{Q}} / \Delta(\mathbb{Q})$, proving compactness.


<br>

##### Theorem 5.7: Radical Exact Sequence Resolving Category Guard 4.1 ^thm-5-7

*Parent Derivation:* [[#^thm-4-1|Theorem 4.1]], [[#^rem-4-1|Remark 4.1]], [[#^def-5-3|Definition 5.3]], [[#^def-5-5|Definition 5.5]].

Let $\widehat{\mathbb{Z}} \coloneq \prod_{p \in \mathcal{P}} \mathbb{Z}_{p}$ be the maximal compact subring of $\mathbb{A}_{\mathbb{Q}, \text{fin}}$. The square-free limit ring $R_{\infty}$ of [[#^thm-4-1|Theorem 4.1]] is the maximal semisimple quotient of $\widehat{\mathbb{Z}}$ modulo its Jacobson radical $\operatorname{rad}(\widehat{\mathbb{Z}}) = \prod_{p \in \mathcal{P}} p\mathbb{Z}_{p}$, fitting into the canonical short exact sequence:

$$
0 \longrightarrow \prod_{p \in \mathcal{P}} p\mathbb{Z}_{p} \longrightarrow \widehat{\mathbb{Z}} \overset{\pi_{\text{rad}}}{\longrightarrow} R_{\infty} \longrightarrow 0
$$

*Proof:*

1. **Componentwise Residue Projection:** For each prime $p \in \mathcal{P}$, the unique maximal ideal of $\mathbb{Z}_{p}$ is $p\mathbb{Z}_{p}$ with quotient field $\mathbb{Z}_{p} / p\mathbb{Z}_{p} \cong \mathbb{F}_{p}$ ([[#^def-5-3|Definition 5.3]]). Taking the direct product of the canonical quotient maps $\mathbb{Z}_{p} \to \mathbb{F}_{p}$ across all $p \in \mathcal{P}$ defines a surjective ring homomorphism $\pi_{\text{rad}}: \widehat{\mathbb{Z}} \to \prod_{p \in \mathcal{P}} \mathbb{F}_{p} \cong R_{\infty}$ ([[#^thm-4-1|Theorem 4.1]]) whose kernel is $\prod_{p \in \mathcal{P}} p\mathbb{Z}_{p} = \operatorname{rad}(\widehat{\mathbb{Z}})$, resolving [[#^rem-4-1|Remark 4.1]].

---

## 5.4 Global Product Haar Measure, Artin Product Formula, and Tamagawa Volume ^sec-5-4


<br>

##### Definition 5.6: Global Adelic Product Haar Measure ^def-5-6

*Parent Derivation:* [[#^lem-4-1|Lemma 4.1]], [[#^def-5-3|Definition 5.3]], [[#^def-5-5|Definition 5.5]].

Equip $(\mathbb{A}_{\mathbb{Q}}, +)$ with the product Radon Haar measure $d\mu_{\mathbb{A}}$ formed from the standard Lebesgue measure $dx$ on $\mathbb{R}$ and the normalized local Haar measures $d\mu_{p}$ ($\mu_{p}(\mathbb{Z}_{p}) = 1$ from [[#^def-5-3|Definition 5.3]]):

$$
d\mu_{\mathbb{A}} \coloneq dx \times \prod_{p \in \mathcal{P}} d\mu_{p}
$$

On every basic open cylinder $U = U_{\infty} \times \prod_{p \in S} U_{p} \times \prod_{p \notin S} \mathbb{Z}_{p}$ ($S \subset \mathcal{P}$ finite), $\mu_{\mathbb{A}}(U) = \lambda(U_{\infty}) \prod_{p \in S} \mu_{p}(U_{p}) \cdot \prod_{p \notin S} 1 < \infty$ converges unconditionally.


<br>

##### Theorem 5.8: Artin Global Product Formula ^thm-5-8

*Parent Derivation:* [[#^lem-5-5a|Lemma 5.5a]], [[#^def-5-4|Definition 5.4]].

For every non-zero rational number $q \in \mathbb{Q}^\times$, the product of its Archimedean and non-Archimedean absolute values across all places $v \le \infty$ equals unity:

$$
\prod_{v \le \infty} \lvert q \rvert_{v} = \lvert q \rvert_{\infty} \cdot \prod_{p \in \mathcal{P}} \lvert q \rvert_{p} = 1
$$

*Proof:*

1. **Prime Valuation Expansion:** By [[#^lem-5-5a|Lemma 5.5a]], write $q = \pm \prod_{p \in \mathcal{P}} p^{v_{p}(q)}$ where $S_{q} \coloneq \{p \in \mathcal{P} \mid v_{p}(q) \neq 0\}$ is finite. Then $\lvert q \rvert_{\infty} = \prod_{p \in S_{q}} p^{v_{p}(q)}$, while [[#^def-5-4|Definition 5.4]] gives $\lvert q \rvert_{p} = p^{-v_{p}(q)}$ for $p \in S_{q}$ and $\lvert q \rvert_{p} = 1$ for $p \notin S_{q}$.

2. **Global Valuation Cancellation:** Multiplying across all places reduces to a finite product over $S_{q}$: $\prod_{v \le \infty} \lvert q \rvert_{v} = \prod_{p \in S_{q}} (p^{v_{p}(q)} \cdot p^{-v_{p}(q)}) = \prod_{p \in S_{q}} 1 = 1$.


<br>

##### Theorem 5.9: Tamagawa Quotient Volume and Rational Scale Invariance ^thm-5-9

*Parent Derivation:* [[#^thm-5-6|Theorem 5.6]], [[#^def-5-6|Definition 5.6]], [[#^thm-5-8|Theorem 5.8]].

The quotient space $\mathbb{A}_{\mathbb{Q}} / \Delta(\mathbb{Q})$ has normalized Tamagawa volume equal to $1$, and the global Haar measure $d\mu_{\mathbb{A}}$ is strictly invariant under multiplication by non-zero rationals $\gamma \in \mathbb{Q}^\times$:

$$
\operatorname{vol}\left(\mathbb{A}_{\mathbb{Q}} / \Delta(\mathbb{Q})\right) = 1, \qquad d\mu_{\mathbb{A}}(\gamma x) = d\mu_{\mathbb{A}}(x) \quad (\forall \gamma \in \mathbb{Q}^\times)
$$

*Proof:*

1. **Fundamental Domain Volume Evaluation:** Evaluating [[#^def-5-6|Definition 5.6]] on the fundamental domain $D = [0, 1) \times \prod_{p \in \mathcal{P}} \mathbb{Z}_{p}$ of [[#^thm-5-6|Theorem 5.6]] yields $\operatorname{vol}(\mathbb{A}_{\mathbb{Q}} / \Delta(\mathbb{Q})) = \mu_{\mathbb{A}}(D) = \lambda([0, 1)) \prod_{p \in \mathcal{P}} \mu_{p}(\mathbb{Z}_{p}) = 1 \cdot \prod_{p \in \mathcal{P}} 1 = 1$.

2. **Global Multiplicative Scale Invariance:** Under scaling $x \mapsto \gamma x$ ($\gamma \in \mathbb{Q}^\times$), local Haar measures transform as $d(\gamma x_{\infty}) = \lvert \gamma \rvert_{\infty} \, dx_{\infty}$ and $d\mu_{p}(\gamma x_{p}) = \lvert \gamma \rvert_{p} \, d\mu_{p}(x_{p})$ ([[#^def-5-3|Definition 5.3]]). Factoring out the scalar modulus and applying [[#^thm-5-8|Theorem 5.8]] gives $d\mu_{\mathbb{A}}(\gamma x) = \left(\prod_{v \le \infty} \lvert \gamma \rvert_{v}\right) d\mu_{\mathbb{A}}(x) = 1 \cdot d\mu_{\mathbb{A}}(x) = d\mu_{\mathbb{A}}(x)$.

---

## 5.5 Global Additive Character $\psi$ and Pontryagin Self-Duality ^sec-5-5

Synthesizing the transverse rotational period $\pi$ ([[#^thm-5-2|Theorem 5.2]]) and the longitudinal exponential scale $e$ ([[#^thm-5-4|Theorem 5.4]]) produces the canonical unitary character on $(\mathbb{A}_{\mathbb{Q}}, +)$.


<br>

##### Definition 5.7: Local and Global Adelic Additive Characters ^def-5-7

*Parent Derivation:* [[#^thm-5-2|Theorem 5.2]], [[#^thm-5-4|Theorem 5.4]], [[#^def-5-4|Definition 5.4]], [[#^def-5-5|Definition 5.5]].

Every $x_{p} \in \mathbb{Q}_{p}$ decomposes uniquely as $x_{p} = [x_{p}]_{p} + \{x_{p}\}_{p}$ with integral part $[x_{p}]_{p} \in \mathbb{Z}_{p}$ and fractional part $\{x_{p}\}_{p} = \sum_{j=-M}^{-1} a_{j} p^{j} \in \mathbb{Z}[p^{-1}] \cap [0, 1)$. Define the local characters $\psi_{\infty}: \mathbb{R} \to S^{1}$ and $\psi_{p}: \mathbb{Q}_{p} \to S^{1}$ by $\psi_{\infty}(x_{\infty}) \coloneq e^{-2\pi i x_{\infty}}$ and $\psi_{p}(x_{p}) \coloneq e^{2\pi i \{x_{p}\}_{p}}$ (with kernel $\ker(\psi_{p}) = \mathbb{Z}_{p}$). Define the global additive character $\psi: \mathbb{A}_{\mathbb{Q}} \to S^{1} \subset \mathbb{C}^\times$ by:

$$
\psi(x) \coloneq \psi_{\infty}(x_{\infty}) \prod_{p \in \mathcal{P}} \psi_{p}(x_{p}) = \exp\left( 2\pi i \left( -x_{\infty} + \sum_{p \in \mathcal{P}} \{x_{p}\}_{p} \right) \right)
$$

Because $\{x_{p}\}_{p} = 0$ for all but finitely many $p \in \mathcal{P}$ ([[#^def-5-5|Definition 5.5]]), the sum is finite and $\psi$ is continuous.


<br>

##### Theorem 5.10: Adelic Rational Reciprocity ^thm-5-10

*Parent Derivation:* [[#^lem-5-5a|Lemma 5.5a]], [[#^thm-5-5|Theorem 5.5]], [[#^def-5-7|Definition 5.7]].

The global additive character $\psi$ vanishes identically (evaluates to $1$) on the discrete rational subfield $\Delta(\mathbb{Q})$:

$$
\forall q \in \mathbb{Q}, \quad \psi(\Delta(q)) = 1
$$

*Proof:*

1. **Partial Fraction Decomposition of Rationals:** For $q = a/b \in \mathbb{Q}^\times$, [[#^lem-5-5a|Lemma 5.5a]] and partial fraction decomposition over the finite prime-power factors of $b$ express $q = z + \sum_{p \mid b} \frac{c_{p}}{p^{v_{p}(b)}}$ with $z \in \mathbb{Z}$ and $c_{p} \in \{0, \dots, p^{v_{p}(b)} - 1\}$.

2. **Global Phase Cancellation:** Because $q - \frac{c_{p}}{p^{v_{p}(b)}} \in \mathbb{Z}_{p}$ at each $p \mid b$ and $q \in \mathbb{Z}_{\ell}$ for $\ell \nmid b$, the local fractional parts are $\{q\}_{p} = c_{p} / p^{v_{p}(b)}$, summing to $\sum_{p \in \mathcal{P}} \{q\}_{p} = q - z$. Substituting into [[#^def-5-7|Definition 5.7]] gives $\psi(\Delta(q)) = \exp(2\pi i (-q + (q - z))) = e^{-2\pi i z} = 1$.


<br>

##### Theorem 5.11: Pontryagin Autoduality of $\mathbb{A}_{\mathbb{Q}}$ and Exact Rational Annihilator $\mathbb{Q}^\perp = \mathbb{Q}$ ^thm-5-11

*Parent Derivation:* [[#^thm-5-6|Theorem 5.6]], [[#^thm-5-9|Theorem 5.9]], [[#^def-5-7|Definition 5.7]], [[#^thm-5-10|Theorem 5.10]].

The pairing $(x, y) \mapsto \psi(x \cdot y)$ induces a topological isomorphism $\Phi: \mathbb{A}_{\mathbb{Q}} \xrightarrow{\cong} \widehat{\mathbb{A}}_{\mathbb{Q}} \coloneq \operatorname{Hom}_{\text{cont}}(\mathbb{A}_{\mathbb{Q}}, S^{1})$ onto the Pontryagin dual group, under which the rational subfield $\Delta(\mathbb{Q})$ is its own exact annihilator:

$$
\mathbb{Q}^\perp \coloneq \left\{ y \in \mathbb{A}_{\mathbb{Q}} \;\middle\vert{}\; \forall q \in \mathbb{Q}, \, \psi(q y) = 1 \right\} = \Delta(\mathbb{Q})
$$

*Proof:*

1. **Injectivity and Autoduality of $\Phi$:** If $\psi(x \cdot y) = 1$ for all $x \in \mathbb{A}_{\mathbb{Q}}$, testing on single-place vectors $(x_{\infty}, 0, \dots)$ and $(0, \dots, x_{p}, \dots, 0)$ forces $y_{\infty} = 0$ and $y_{p} = 0$ for all $p$, proving injectivity. Because $\mathbb{R} \cong \widehat{\mathbb{R}}$ and each $\mathbb{Q}_{p} \cong \widehat{\mathbb{Q}}_{p}$ is self-dual with conductor $\mathbb{Z}_{p}$ ([[#^def-5-7|Definition 5.7]]), every continuous character on the restricted product factors uniquely into $\psi_{y}(x) = \psi(xy)$ for a unique $y \in \mathbb{A}_{\mathbb{Q}}$, establishing $\mathbb{A}_{\mathbb{Q}} \cong \widehat{\mathbb{A}}_{\mathbb{Q}}$.

2. **Rational Annihilator Inclusion ($\Delta(\mathbb{Q}) \subseteq \mathbb{Q}^\perp$):** Because $\mathbb{Q}$ is closed under multiplication, $q, \gamma \in \mathbb{Q} \implies q\gamma \in \mathbb{Q} \implies \psi(\Delta(q\gamma)) = 1$ by [[#^thm-5-10|Theorem 5.10]], so $\Delta(\mathbb{Q}) \subseteq \mathbb{Q}^\perp$.

3. **Covolume Index Collapse ($\mathbb{Q}^\perp = \Delta(\mathbb{Q})$):** By Pontryagin duality for locally compact abelian groups, $\widehat{\mathbb{A}_{\mathbb{Q}} / \Delta(\mathbb{Q})} \cong \mathbb{Q}^\perp$. Since $\mathbb{A}_{\mathbb{Q}} / \Delta(\mathbb{Q})$ is compact of Tamagawa volume $1$ ([[#^thm-5-6|Theorem 5.6]], [[#^thm-5-9|Theorem 5.9]]), $\mathbb{Q}^\perp$ is a discrete subgroup containing $\Delta(\mathbb{Q})$ with equal covolume $\operatorname{vol}(\mathbb{A}_{\mathbb{Q}} / \mathbb{Q}^\perp) = 1$, forcing $[\mathbb{Q}^\perp : \Delta(\mathbb{Q})] = 1 / 1 = 1$ and $\mathbb{Q}^\perp = \Delta(\mathbb{Q})$.

**Worked Example 7 (Adelic Rational Reciprocity at $q = 5/6$):** Consider $q = 5/6 \in \mathbb{Q}^\times$, whose partial fraction decomposition is $\frac{5}{6} = 0 + \frac{1}{2} + \frac{1}{3}$. At $p = 2$, $\{5/6\}_{2} = 1/2$; at $p = 3$, $\{5/6\}_{3} = 1/3$; and for all $p \ge 5$, $5/6 \in \mathbb{Z}_{p}$ gives $\{5/6\}_{p} = 0$. Evaluating [[#^def-5-7|Definition 5.7]] on $\Delta(5/6)$ yields:

$$
\psi\left(\Delta\left(\frac{5}{6}\right)\right) = \exp\left( 2\pi i \left( -\frac{5}{6} + \frac{1}{2} + \frac{1}{3} \right) \right) = \exp(0) = 1
$$

confirming exact global phase cancellation across Archimedean and $p$-adic places.

**Emergent Isomorphism Bridge 6 (Orthogonal Prime Constants $\pi, e$ and Chevalley-Weil Adeles):** In classical analysis and algebraic number theory, $\pi$ and $e$ are introduced through Euclidean geometry and differential equations, while Hensel's $p$-adic fields $\mathbb{Q}_{p}$ and Chevalley's restricted adele ring $\mathbb{A}_{\mathbb{Q}}$ are built to unify local and global class field theory. Under [[#^def-0-1|Definition 0.1]], [[#^thm-5-3|Theorem 5.3]], [[#^thm-5-4|Theorem 5.4]], [[#^thm-5-8|Theorem 5.8]], and [[#^thm-5-11|Theorem 5.11]] reveal that $\pi$ and $e$ are dual asymptotic invariants of the prime lattice ($\pi$ measuring two-dimensional coprime non-collision density and $e$ measuring one-dimensional primorial information density), while $\mathbb{A}_{\mathbb{Q}}$ is the unique locally compact phase space in which rational scaling conserves total volume ($\prod_{v \le \infty} \lvert q \rvert_{v} = 1$) and $\Delta(\mathbb{Q})$ is its own exact Fourier dual ($\mathbb{Q}^\perp = \Delta(\mathbb{Q})$).

*Exit Handoff:* We have extracted the transcendentals $\pi$ and $e$ from prime statistics, constructed vertical $p$-adic towers $\mathbb{Q}_{p}$, and proved Pontryagin autoduality and Artin scale conservation on the restricted adele ring $\mathbb{A}_{\mathbb{Q}}$. Equipped with a self-dual locally compact ring and global additive character $\psi$, we are now ready in Section 6 to execute adelic Poisson summation, derive Tate's functional equation for the completed Riemann zeta function, and establish Weil's spectral positivity criterion.

---

---

# Section 6: Adelic Poisson Summation, Tate's Functional Equation, and Weil Positivity ^sec-6

*Entry Primer:* In Section 5, we fused the Archimedean continuum $\mathbb{R}$ and every local $p$-adic completion $\mathbb{Q}_{p}$ into the restricted adele ring $\mathbb{A}_{\mathbb{Q}}$, proving that the rational diagonal $\Delta(\mathbb{Q})$ is discrete and cocompact with normalized Tamagawa volume $1$ and exact Pontryagin self-annihilator $\mathbb{Q}^\perp = \Delta(\mathbb{Q})$. What global symmetry governs the distribution of prime words when we execute harmonic analysis on this self-dual phase space? In this final formal section, we prove adelic Poisson summation, construct a Fourier-invariant Gaussian-ball test kernel ($\widehat{f} = f$), derive Tate's functional equation $\Lambda(1 - s) = \Lambda(s)$ for the completed Riemann zeta function, and establish Weil's spectral positivity criterion for the Riemann Hypothesis.

## 6.1 Adelic Fourier Analysis and Poisson Summation ^sec-6-1

Combining compact torus Fourier analysis on $\mathbb{A}_{\mathbb{Q}}/\Delta(\mathbb{Q})$ with Pontryagin autoduality yields the global adelic Poisson summation formula.


<br>

##### Definition 6.1: Adelic Schwartz-Bruhat Space and Global Fourier Transform ^def-6-1

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^def-5-3|Definition 5.3]], [[#^def-5-5|Definition 5.5]], [[#^def-5-6|Definition 5.6]], [[#^def-5-7|Definition 5.7]].

Define the adelic Schwartz-Bruhat space $\mathcal{S}(\mathbb{A}_{\mathbb{Q}})$ as the space of finite linear combinations of factorizable test functions:

$$
f(x) = f_{\infty}(x_{\infty}) \prod_{p \in \mathcal{P}} f_{p}(x_{p})
$$

where $f_{\infty} \in \mathcal{S}(\mathbb{R})$ is a smooth rapidly decreasing Schwartz function on $\mathbb{R}$ ([[#^thm-1-11|Theorem 1.11]]), $f_{p}: \mathbb{Q}_{p} \to \mathbb{C}$ is locally constant with compact support for every $p \in \mathcal{P}$, and $f_{p} = \mathbf{1}_{\mathbb{Z}_{p}}$ for all but finitely many $p \in \mathcal{P}$ ([[#^def-5-3|Definition 5.3]], [[#^def-5-5|Definition 5.5]]). Using the global product Haar measure $dx = d\mu_{\mathbb{A}}(x)$ of [[#^def-5-6|Definition 5.6]] and global additive character $\psi$ of [[#^def-5-7|Definition 5.7]], define the global Fourier transform $\widehat{f}: \mathbb{A}_{\mathbb{Q}} \to \mathbb{C}$ by:

$$
\widehat{f}(\xi) \coloneq \int_{\mathbb{A}_{\mathbb{Q}}} f(x) \psi(\xi \cdot x) \, dx
$$


<br>

##### Theorem 6.1: Unweighted Adelic Poisson Summation Formula ^thm-6-1

*Parent Derivation:* [[#^thm-5-6|Theorem 5.6]], [[#^thm-5-9|Theorem 5.9]], [[#^thm-5-10|Theorem 5.10]], [[#^thm-5-11|Theorem 5.11]], [[#^def-6-1|Definition 6.1]].

For every Schwartz-Bruhat function $f \in \mathcal{S}(\mathbb{A}_{\mathbb{Q}})$, the lattice sums of $f$ and its Fourier transform $\widehat{f}$ over the rational subfield $\mathbb{Q}$ coincide identically:

$$
\sum_{\gamma \in \mathbb{Q}} f(\Delta(\gamma)) = \sum_{\gamma \in \mathbb{Q}} \widehat{f}(\Delta(\gamma))
$$

*Intuition:* Averaging $f$ over all rational translates produces a continuous periodic function on the compact quotient torus $T = \mathbb{A}_{\mathbb{Q}}/\Delta(\mathbb{Q})$. Because $\Delta(\mathbb{Q})$ is its own Pontryagin dual ($\mathbb{Q}^\perp = \Delta(\mathbb{Q})$) and $T$ has volume $1$, the Fourier coefficients of the periodized function unfold across the fundamental domain $D$ to equal $\widehat{f}(\Delta(-\gamma))$, so evaluating at $0$ equates the two rational sums.

*Proof:*

1. **Periodization on the Compact Quotient Torus:** Let $T \coloneq \mathbb{A}_{\mathbb{Q}} / \Delta(\mathbb{Q})$ denote the compact quotient group of [[#^thm-5-6|Theorem 5.6]] with normalized Haar measure $d\mu_{T}$ of total volume $1$ ([[#^thm-5-9|Theorem 5.9]]). Define the periodization $F(x) \coloneq \sum_{\gamma \in \mathbb{Q}} f(x + \Delta(\gamma))$, which converges absolutely and uniformly on compact subsets of $\mathbb{A}_{\mathbb{Q}}$ and satisfies $F(x + \Delta(q)) = F(x)$ for all $q \in \mathbb{Q}$, descending to a continuous function $F \in C(T)$.

2. **Pontryagin Character Basis Identification:** By [[#^thm-5-11|Theorem 5.11]], the Pontryagin dual group $\widehat{T}$ is canonically isomorphic to $\mathbb{Q}^\perp = \Delta(\mathbb{Q})$, so the characters $\{\chi_{\gamma}(x) \coloneq \psi(\Delta(\gamma) \cdot x)\}_{\gamma \in \mathbb{Q}}$ form a complete orthonormal basis for $L^{2}(T, d\mu_{T})$.

3. **Fourier Coefficient Unfolding over the Fundamental Domain:** Expanding $F(x) = \sum_{\gamma \in \mathbb{Q}} c_{\gamma} \psi(\Delta(\gamma) \cdot x)$ on $T$ and integrating over the fundamental domain $D$ of [[#^thm-5-6|Theorem 5.6]] using $\psi(\Delta(-\gamma q)) = 1$ ([[#^thm-5-10|Theorem 5.10]]) unfolds the periodized sum across all of $\mathbb{A}_{\mathbb{Q}}$:

$$
c_{\gamma} = \int_{D} \sum_{q \in \mathbb{Q}} f(x + \Delta(q)) \psi(\Delta(-\gamma) \cdot (x + \Delta(q))) \, dx = \int_{\mathbb{A}_{\mathbb{Q}}} f(u) \psi(\Delta(-\gamma) \cdot u) \, du = \widehat{f}(\Delta(-\gamma))
$$

4. **Evaluation at the Identity:** Evaluating the Fourier expansion at $x = 0 \in \mathbb{A}_{\mathbb{Q}}$ (where $\psi(0) = 1$) and re-indexing $-\gamma \mapsto \gamma$ across $\mathbb{Q}$ yields $\sum_{\gamma \in \mathbb{Q}} f(\Delta(\gamma)) = F(0) = \sum_{\gamma \in \mathbb{Q}} \widehat{f}(\Delta(-\gamma)) = \sum_{\gamma \in \mathbb{Q}} \widehat{f}(\Delta(\gamma))$.

---

## 6.2 Self-Dual Test Kernel and Idele Zeta Factorization ^sec-6-2


<br>

##### Definition 6.2: Standard Self-Dual Schwartz-Bruhat Kernel ^def-6-2

*Parent Derivation:* [[#^thm-5-2|Theorem 5.2]], [[#^def-5-3|Definition 5.3]], [[#^def-6-1|Definition 6.1]].

Define the canonical test kernel $f \in \mathcal{S}(\mathbb{A}_{\mathbb{Q}})$ as the restricted product of the normalized Archimedean Gaussian (using $\pi$ from [[#^thm-5-2|Theorem 5.2]]) and the non-Archimedean unit-ball indicator functions ([[#^def-5-3|Definition 5.3]]):

$$
f(x) \coloneq f_{\infty}(x_{\infty}) \prod_{p \in \mathcal{P}} f_{p}(x_{p}) \coloneq e^{-\pi x_{\infty}^{2}} \prod_{p \in \mathcal{P}} \mathbf{1}_{\mathbb{Z}_{p}}(x_{p})
$$


<br>

##### Theorem 6.2: Local and Global Fourier Self-Duality of the Standard Kernel ^thm-6-2

*Parent Derivation:* [[#^thm-5-2|Theorem 5.2]], [[#^def-5-3|Definition 5.3]], [[#^def-5-7|Definition 5.7]], [[#^def-6-2|Definition 6.2]].

The standard kernel $f$ of [[#^def-6-2|Definition 6.2]] is invariant under the global adelic Fourier transform and normalized to unity at the origin:

$$
\widehat{f} = f, \qquad f(0) = \widehat{f}(0) = 1
$$

*Proof:*

1. **Archimedean Gaussian Self-Duality:** Completing the square in the exponent $-\pi x^{2} - 2\pi i x y_{\infty} = -\pi(x + i y_{\infty})^{2} - \pi y_{\infty}^{2}$ and shifting the horizontal contour $\mathbb{R} + i y_{\infty} \to \mathbb{R}$ via Cauchy's theorem (where $\int_{-\infty}^{\infty} e^{-\pi u^{2}} \, du = 1$ by [[#^thm-5-2|Theorem 5.2]]) gives:

$$
\widehat{f}_{\infty}(y_{\infty}) = \int_{-\infty}^{\infty} e^{-\pi x^{2}} e^{-2\pi i x y_{\infty}} \, dx = e^{-\pi y_{\infty}^{2}} \int_{-\infty}^{\infty} e^{-\pi(x + i y_{\infty})^{2}} \, dx = e^{-\pi y_{\infty}^{2}} = f_{\infty}(y_{\infty})
$$

2. **Non-Archimedean Characteristic Self-Duality:** Fix $p \in \mathcal{P}$ and evaluate $\widehat{f}_{p}(y_{p}) = \int_{\mathbb{Z}_{p}} \psi_{p}(x y_{p}) \, dx_{p}$ via [[#^def-5-7|Definition 5.7]]. If $y_{p} \in \mathbb{Z}_{p}$, then $x y_{p} \in \mathbb{Z}_{p}$ for all $x \in \mathbb{Z}_{p}$, so $\psi_{p}(x y_{p}) = 1$ and $\widehat{f}_{p}(y_{p}) = \mu_{p}(\mathbb{Z}_{p}) = 1$ ([[#^def-5-3|Definition 5.3]]); if $y_{p} \notin \mathbb{Z}_{p}$, then $x \mapsto \psi_{p}(x y_{p})$ is a non-trivial character on the compact group $\mathbb{Z}_{p}$ whose integral vanishes identically, giving $\widehat{f}_{p}(y_{p}) = \mathbf{1}_{\mathbb{Z}_{p}}(y_{p}) = f_{p}(y_{p})$.

3. **Global Product Closure:** Multiplying across all places yields $\widehat{f}(y) = \widehat{f}_{\infty}(y_{\infty}) \prod_{p \in \mathcal{P}} \widehat{f}_{p}(y_{p}) = f(y)$, with $f(0) = \widehat{f}(0) = e^{0} \prod_{p \in \mathcal{P}} 1 = 1$.


<br>

##### Definition 6.3: The Idele Group, Idele Norm, and Multiplicative Haar Measure ^def-6-3

*Parent Derivation:* [[#^def-5-3|Definition 5.3]], [[#^def-5-4|Definition 5.4]], [[#^def-5-5|Definition 5.5]], [[#^thm-5-8|Theorem 5.8]].

Define the idele group $\mathbb{I}_{\mathbb{Q}} \coloneq \mathbb{A}_{\mathbb{Q}}^\times$ as the multiplicative group of invertible adeles equipped with the idele norm $\lVert \cdot \rVert: \mathbb{I}_{\mathbb{Q}} \to \mathbb{R}_{> 0}$ and normalized multiplicative Haar measure $d^\times x$:

$$
\mathbb{I}_{\mathbb{Q}} \coloneq \mathbb{R}^\times \times {\prod_{p \in \mathcal{P}}}' (\mathbb{Q}_{p}^\times, \mathbb{Z}_{p}^\times), \qquad \lVert x \rVert \coloneq \lvert x_{\infty} \rvert_{\infty} \prod_{p \in \mathcal{P}} \lvert x_{p} \rvert_{p}
$$

$$
d^\times x \coloneq \frac{dx_{\infty}}{\lvert x_{\infty} \rvert_{\infty}} \times \prod_{p \in \mathcal{P}} \frac{1}{1 - p^{-1}} \frac{dx_{p}}{\lvert x_{p} \rvert_{p}}
$$

By [[#^def-5-3|Definition 5.3]], $\mu_{p}(\mathbb{Z}_{p}^\times) = \mu_{p}(\mathbb{Z}_{p}) - \mu_{p}(p\mathbb{Z}_{p}) = 1 - p^{-1}$, so $\int_{\mathbb{Z}_{p}^\times} d^\times x_{p} = 1$ for every $p \in \mathcal{P}$. Defining the norm-one idele kernel $\mathbb{I}_{\mathbb{Q}}^{1} \coloneq \{x \in \mathbb{I}_{\mathbb{Q}} \mid \lVert x \rVert = 1\}$ and noting that $\Delta(\mathbb{Q}^\times) \cap \mathbb{I}_{\mathbb{Q}}^{1} = \{\Delta(\pm 1)\}$ by [[#^thm-5-8|Theorem 5.8]], embedding $t \in (0, \infty)$ as $(t, 1, 1, \dots) \in \mathbb{I}_{\mathbb{Q}}$ yields the sign-deduplicated polar decomposition:

$$
\mathbb{I}_{\mathbb{Q}} \cong \Delta(\mathbb{Q}^\times) \times (0, \infty) \times \prod_{p \in \mathcal{P}} \mathbb{Z}_{p}^\times
$$

*Notation Rationale:* The blackboard bold $\mathbb{I}_{\mathbb{Q}}$ denotes the *idele* group (from Chevalley's *élément idéal*), isolating the multiplicative units of $\mathbb{A}_{\mathbb{Q}}$ under the inductive limit unit topology.


<br>

##### Corollary 6.1: Idele-Scaled Adelic Poisson Summation Formula ^cor-6-1

*Parent Derivation:* [[#^thm-5-9|Theorem 5.9]], [[#^thm-6-1|Theorem 6.1]], [[#^def-6-3|Definition 6.3]].

For every $f \in \mathcal{S}(\mathbb{A}_{\mathbb{Q}})$ and every idele $y \in \mathbb{I}_{\mathbb{Q}}$, dilating the summation lattice by $y$ satisfies:

$$
\sum_{\gamma \in \mathbb{Q}} f(\Delta(\gamma) \cdot y) = \frac{1}{\lVert y \rVert} \sum_{\gamma \in \mathbb{Q}} \widehat{f}\left( \frac{\Delta(\gamma)}{y} \right)
$$

*Proof:*

1. **Dilation Fourier Transform:** Fix $y \in \mathbb{I}_{\mathbb{Q}}$ and define $g(x) \coloneq f(x \cdot y) \in \mathcal{S}(\mathbb{A}_{\mathbb{Q}})$. Substituting $u = x \cdot y$ in [[#^def-6-1|Definition 6.1]], where the additive Haar measure transforms by $dx = \lVert y \rVert^{-1} \, du$ ([[#^thm-5-9|Theorem 5.9]], [[#^def-6-3|Definition 6.3]]), gives $\widehat{g}(\xi) = \int_{\mathbb{A}_{\mathbb{Q}}} f(u) \psi(\xi y^{-1} \cdot u) \lVert y \rVert^{-1} \, du = \lVert y \rVert^{-1} \widehat{f}(\xi / y)$.

2. **Unweighted Poisson Application:** Applying [[#^thm-6-1|Theorem 6.1]] to $g$ immediately yields $\sum_{\gamma \in \mathbb{Q}} f(\Delta(\gamma) \cdot y) = \sum_{\gamma \in \mathbb{Q}} g(\Delta(\gamma)) = \sum_{\gamma \in \mathbb{Q}} \widehat{g}(\Delta(\gamma)) = \lVert y \rVert^{-1} \sum_{\gamma \in \mathbb{Q}} \widehat{f}(\Delta(\gamma) / y)$.


<br>

##### Theorem 6.3: Local-to-Global Euler Factorization of the Completed Zeta Integral ^thm-6-3

*Parent Derivation:* [[#^lem-5-5a|Lemma 5.5a]], [[#^def-6-2|Definition 6.2]], [[#^def-6-3|Definition 6.3]].

For $s \in \mathbb{C}$ with $\operatorname{Re}(s) > 1$, the global Tate zeta integral $\mathcal{Z}(f, s) \coloneq \int_{\mathbb{I}_{\mathbb{Q}}} f(x) \lVert x \rVert^{s} \, d^\times x$ over the standard kernel $f$ of [[#^def-6-2|Definition 6.2]] converges absolutely and factorizes into the completed Riemann zeta function $\Lambda(s)$:

$$
\mathcal{Z}(f, s) = \pi^{-s/2} \Gamma\left(\frac{s}{2}\right) \zeta(s) \eqqcolon \Lambda(s)
$$

*Proof:*

1. **Product Integral Decomposition:** By [[#^def-6-2|Definition 6.2]] and [[#^def-6-3|Definition 6.3]], $\mathcal{Z}(f, s)$ splits into local integrals $I_{\infty}(s) \prod_{p \in \mathcal{P}} I_{p}(s)$.

2. **Archimedean Gamma Evaluation:** Substituting $u = \pi x^{2}$ ($dx / x = \frac{1}{2} du / u$) in the real factor gives:

$$
I_{\infty}(s) = 2 \int_{0}^{\infty} e^{-\pi x^{2}} x^{s} \, \frac{dx}{x} = \pi^{-s/2} \int_{0}^{\infty} e^{-u} u^{\frac{s}{2} - 1} \, du = \pi^{-s/2} \Gamma\left(\frac{s}{2}\right)
$$

3. **Non-Archimedean Geometric Shell Evaluation:** Partitioning $\mathbb{Z}_{p} \setminus \{0\} = \bigsqcup_{m=0}^{\infty} p^{m} \mathbb{Z}_{p}^\times$ where $\lvert x_{p} \rvert_{p} = p^{-m}$ and $\int_{\mathbb{Z}_{p}^\times} d^\times x_{p} = 1$ ([[#^def-6-3|Definition 6.3]]) yields for $\operatorname{Re}(s) > 1$:

$$
I_{p}(s) = \sum_{m=0}^{\infty} \int_{p^{m} \mathbb{Z}_{p}^\times} (p^{-m})^{s} \, d^\times x_{p} = \sum_{m=0}^{\infty} \left(p^{-s}\right)^{m} = \frac{1}{1 - p^{-s}}
$$

4. **Euler Product Synthesis:** Multiplying across all primes via unique prime factorization ([[#^lem-5-5a|Lemma 5.5a]]) gives $\prod_{p \in \mathcal{P}} (1 - p^{-s})^{-1} = \sum_{n=1}^{\infty} n^{-s} = \zeta(s)$, establishing $\mathcal{Z}(f, s) = \pi^{-s/2} \Gamma(s/2) \zeta(s) = \Lambda(s)$.

---

## 6.3 Tate's Functional Equation $\Lambda(1 - s) = \Lambda(s)$ ^sec-6-3


<br>

##### Theorem 6.4: Analytic Continuation and Tate's Functional Equation ^thm-6-4

*Parent Derivation:* [[#^thm-6-2|Theorem 6.2]], [[#^cor-6-1|Corollary 6.1]], [[#^thm-6-3|Theorem 6.3]].

The completed zeta function $\Lambda(s)$ admits a meromorphic continuation to all of $\mathbb{C}$ with simple poles solely at $s = 1$ and $s = 0$ (with residue sum $\frac{1}{s(s - 1)}$) and satisfies the exact reflection symmetry:

$$
\Lambda(1 - s) = \Lambda(s)
$$

*Intuition:* Splitting the scale ray $(0, \infty)$ at $t = 1$ separates large scales ($t \ge 1$, where the Gaussian kernel decays super-exponentially) from small scales ($t \in (0, 1]$, where lattice points crowd together). Applying idele-scaled Poisson summation on $(0, 1]$ flips $t \mapsto t^{-1} \ge 1$ via Fourier self-duality ($\widehat{f} = f$), leaving behind the boundary poles $\frac{1}{s-1} - \frac{1}{s} = \frac{1}{s(s-1)}$ and a manifestly $s \leftrightarrow 1 - s$ symmetric integral.

*Proof:*

1. **Idele Quotient Folding and Ray Splitting:** Folding the integral of [[#^thm-6-3|Theorem 6.3]] over the discrete subgroup $\Delta(\mathbb{Q}^\times)$ using the polar decomposition $\mathbb{I}_{\mathbb{Q}} \cong \Delta(\mathbb{Q}^\times) \times (0, \infty) \times \prod_{p \in \mathcal{P}} \mathbb{Z}_{p}^\times$ of [[#^def-6-3|Definition 6.3]] (where $f$ is invariant under $\prod_{p \in \mathcal{P}} \mathbb{Z}_{p}^\times$ of total measure $1$) and splitting $(0, \infty) = (0, 1] \cup [1, \infty)$ gives for $\operatorname{Re}(s) > 1$:

$$
\Lambda(s) = \int_{1}^{\infty} \left( \sum_{\gamma \in \mathbb{Q}^\times} f(\Delta(\gamma) \cdot t) \right) t^{s} \, \frac{dt}{t} + \int_{0}^{1} \left( \sum_{\gamma \in \mathbb{Q}^\times} f(\Delta(\gamma) \cdot t) \right) t^{s} \, \frac{dt}{t}
$$

2. **Poisson Inversion and Polar Singularity Extraction on $(0, 1]$:** Applying [[#^cor-6-1|Corollary 6.1]] at $y = (t, 1, 1, \dots)$ ($\lVert y \rVert = t$) and isolating $\gamma = 0$ gives $\sum_{\gamma \in \mathbb{Q}^\times} f(\Delta(\gamma) \cdot t) = t^{-1} \sum_{\gamma \in \mathbb{Q}^\times} \widehat{f}(\Delta(\gamma) / t) + t^{-1} \widehat{f}(0) - f(0)$. Integrating the boundary terms over $t \in (0, 1]$ with $f(0) = \widehat{f}(0) = 1$ ([[#^thm-6-2|Theorem 6.2]]) produces:

$$
\widehat{f}(0) \int_{0}^{1} t^{s - 2} \, dt - f(0) \int_{0}^{1} t^{s - 1} \, dt = \frac{1}{s - 1} - \frac{1}{s} = \frac{1}{s(s - 1)}
$$

3. **Variable Inversion $\tau = t^{-1}$ and Master Integral Representation:** Substituting $\tau = t^{-1}$ ($dt/t = -d\tau/\tau$) maps $\int_{0}^{1} \sum_{\gamma \in \mathbb{Q}^\times} \widehat{f}(\Delta(\gamma) / t) t^{s - 1} \, \frac{dt}{t}$ to $\int_{1}^{\infty} \sum_{\gamma \in \mathbb{Q}^\times} \widehat{f}(\Delta(\gamma) \cdot \tau) \tau^{1 - s} \, \frac{d\tau}{\tau}$. Invoking $\widehat{f} = f$ ([[#^thm-6-2|Theorem 6.2]]) yields the master representation:

$$
\Lambda(s) = \int_{1}^{\infty} \left( \sum_{\gamma \in \mathbb{Q}^\times} f(\Delta(\gamma) \cdot t) \right) \left( t^{s} + t^{1 - s} \right) \frac{dt}{t} + \frac{1}{s(s - 1)}
$$

4. **Entire Convergence and Reflection Invariance:** For $t \ge 1$, $\gamma t \in \mathbb{Z}_{p}$ for all $p \in \mathcal{P}$ forces $\gamma = n \in \mathbb{Z} \setminus \{0\}$, so $\sum_{\gamma \in \mathbb{Q}^\times} f(\Delta(\gamma) \cdot t) = 2 \sum_{n=1}^{\infty} e^{-\pi n^{2} t^{2}} = \mathcal{O}(e^{-\pi t^{2}})$ decays super-polynomially, defining an entire function of $s \in \mathbb{C}$. Replacing $s \mapsto 1 - s$ preserves both $t^{s} + t^{1 - s}$ and $(1 - s)(-s) = s(s - 1)$, proving $\Lambda(1 - s) = \Lambda(s)$.

---

## 6.4 The Weil-Guinand Explicit Distribution Formula ^sec-6-4


<br>

##### Definition 6.4: Holomorphic Spectral Symmetrization Kernel ^def-6-4

*Parent Derivation:* [[#^thm-1-11|Theorem 1.11]], [[#^thm-6-4|Theorem 6.4]].

Let $h: \mathbb{C} \to \mathbb{C}$ be holomorphic in the strip $\lvert \operatorname{Im}(r) \rvert \le \frac{1}{2} + \delta$ ($\delta > 0$), even ($h(-r) = h(r)$), Schwarz-symmetric ($h(\bar{r}) = \overline{h(r)}$), and rapidly decaying ($\lvert h(r) \rvert = \mathcal{O}((1 + \lvert \operatorname{Re}(r) \rvert)^{-2 - \epsilon})$ for some $\epsilon > 0$). Using $\exp$ from [[#^thm-1-11|Theorem 1.11]], define its even real-valued Fourier dual $g: \mathbb{R} \to \mathbb{R}$ and its $s$-plane lift $\Phi: \mathbb{C} \to \mathbb{C}$ via $r = -i(s - \frac{1}{2})$ by:

$$
g(u) \coloneq \frac{1}{2\pi} \int_{-\infty}^{\infty} h(r) e^{-i r u} \, dr, \qquad \Phi(s) \coloneq h\left(-i\left(s - \frac{1}{2}\right)\right) = \int_{-\infty}^{\infty} g(u) \exp\left(\left(s - \frac{1}{2}\right) u\right) \, du
$$

Because $h$ is even, $\Phi(1 - s) = h(i(s - \frac{1}{2})) = h(-i(s - \frac{1}{2})) = \Phi(s)$; because $h(\bar{r}) = \overline{h(r)}$ and $h(-r) = h(r)$, $g(u) \in \mathbb{R}$ for all $u \in \mathbb{R}$.


<br>

##### Theorem 6.5: Weil-Guinand Explicit Distribution Formula ^thm-6-5

*Parent Derivation:* [[#^lem-5-5a|Lemma 5.5a]], [[#^thm-6-4|Theorem 6.4]], [[#^def-6-4|Definition 6.4]].

Let $Z_{\Lambda} \coloneq \{\rho = \beta_{\rho} + i\gamma_{\rho} \in \mathbb{C} \mid \Lambda(\rho) = 0\}$ denote the multiset of non-trivial zeros of $\Lambda(s)$ counted with multiplicity $m_{\rho}$, parameterized spectrally by $r_{\rho} \coloneq -i(\rho - \frac{1}{2}) = \gamma_{\rho} - i(\beta_{\rho} - \frac{1}{2})$. For every test pair $(h, g)$ of [[#^def-6-4|Definition 6.4]], the spectral zero sum balances the polar, Archimedean, and non-Archimedean prime-power distributions identically:

$$
\sum_{\rho \in Z_{\Lambda}} h(r_{\rho}) = 2 h\left(\frac{i}{2}\right) - g(0) \ln \pi + \frac{1}{2\pi} \int_{-\infty}^{\infty} \operatorname{Re}\left[ \frac{\Gamma'}{\Gamma}\left(\frac{1}{4} + \frac{ir}{2}\right) \right] h(r) \, dr - \sum_{p \in \mathcal{P}} \sum_{m=1}^{\infty} \frac{\ln \text{len}(p)}{\text{len}(p)^{m/2}} \left[ g(m \ln \text{len}(p)) + g(-m \ln \text{len}(p)) \right]
$$

*Intuition:* Integrating the logarithmic derivative $\frac{\Lambda'}{\Lambda}(s)\Phi(s)$ around a rectangle enclosing the critical strip collects residues from the zeta zeros $\rho \in Z_{\Lambda}$ and the boundary poles at $s = 0, 1$. Folding the left edge $\operatorname{Re}(s) = 1 - c$ onto the right edge $\operatorname{Re}(s) = c$ via Tate's functional equation decomposes the boundary integral into the Archimedean digamma factor and a Fourier-localized sum over all prime powers $p^{m}$.

*Proof:*

1. **Cauchy Residue Evaluation Around the Critical Strip:** Fix $c \coloneq 1 + \frac{\delta}{2} > 1$ and integrate $\frac{1}{2\pi i} \frac{\Lambda'}{\Lambda}(s) \Phi(s)$ counterclockwise around the rectangle $R_{T}$ with vertices $c \pm iT$ and $(1 - c) \pm iT$. By [[#^thm-6-4|Theorem 6.4]], $\Lambda(s)$ has simple poles at $s = 1$ and $s = 0$ (each contributing residue $-1 \cdot \Phi(1) = -1 \cdot \Phi(0) = -h(i/2)$) and zeros at $\rho \in Z_{\Lambda}$ with $\Phi(\rho) = h(r_{\rho})$, so taking $T \to \infty$ (where horizontal segments vanish by rapid decay of $h$) yields $\sum_{\rho \in Z_{\Lambda}} h(r_{\rho}) - 2h(i/2)$.

2. **Contour Folding via Functional Inversion:** Differentiating $\ln \Lambda(s) = \ln \Lambda(1 - s)$ ([[#^thm-6-4|Theorem 6.4]]) gives $\frac{\Lambda'}{\Lambda}(1 - s) = -\frac{\Lambda'}{\Lambda}(s)$. Substituting $s = 1 - w$ on the left vertical line $\operatorname{Re}(s) = 1 - c$ maps it identically onto the right vertical line $\operatorname{Re}(w) = c$, doubling the vertical integral to $\frac{1}{\pi i} \int_{(c)} \frac{\Lambda'}{\Lambda}(s) \Phi(s) \, ds$.

3. **Bromwich-Dirac Localization of Prime Powers:** Expanding $\frac{\Lambda'}{\Lambda}(s) = -\frac{1}{2}\ln \pi + \frac{1}{2}\frac{\Gamma'}{\Gamma}\left(\frac{s}{2}\right) + \frac{\zeta'}{\zeta}(s)$ on $\operatorname{Re}(s) = c > 1$, where $\frac{\zeta'}{\zeta}(s) = -\sum_{p \in \mathcal{P}} \sum_{m=1}^{\infty} (\ln \text{len}(p)) \text{len}(p)^{-ms}$ ([[#^lem-5-5a|Lemma 5.5a]]), and applying Fourier inversion $\frac{1}{2\pi} \int_{-\infty}^{\infty} e^{it(u - m \ln \text{len}(p))} \, dt = \delta(u - m \ln \text{len}(p))$ evaluates each prime-power Bromwich term to:

$$
-\ln \text{len}(p) \left( \frac{1}{\pi i} \int_{(c)} \text{len}(p)^{-ms} \Phi(s) \, ds \right) = -\frac{2 \ln \text{len}(p)}{\text{len}(p)^{m/2}} g(m \ln \text{len}(p)) = -\frac{\ln \text{len}(p)}{\text{len}(p)^{m/2}} \left[ g(m \ln \text{len}(p)) + g(-m \ln \text{len}(p)) \right]
$$

4. **Archimedean Critical-Line Shift and Odd-Even Annihilation:** Because $\frac{\Gamma'}{\Gamma}\left(\frac{s}{2}\right)$ is holomorphic on $\operatorname{Re}(s) > 0$, shifting the remaining vertical integral to $s = \frac{1}{2} + ir$ ($r \in \mathbb{R}$) yields $-\frac{\ln \pi}{2\pi} \int_{-\infty}^{\infty} h(r) \, dr = -g(0) \ln \pi$ plus $\frac{1}{2\pi} \int_{-\infty}^{\infty} \frac{\Gamma'}{\Gamma}\left(\frac{1}{4} + \frac{ir}{2}\right) h(r) \, dr$. Because $\overline{\Gamma(z)} = \Gamma(\bar{z})$ makes $\operatorname{Im}\left[\frac{\Gamma'}{\Gamma}\left(\frac{1}{4} + \frac{ir}{2}\right)\right]$ odd in $r$ while $h(r)$ is even, the imaginary part integrates to zero, leaving the stated formula.

---

## 6.5 The Weil Positivity Criterion and Adelic Self-Adjointness ^sec-6-5


<br>

##### Definition 6.5: Exponentially Weighted Schwartz Test Algebra and Weil Functional ^def-6-5

*Parent Derivation:* [[#^def-6-4|Definition 6.4]], [[#^thm-6-5|Theorem 6.5]].

Define the exponentially weighted Schwartz test space $\mathcal{V} \coloneq \mathcal{S}_{\text{exp}}(\mathbb{R})$ as the involutive convolution algebra of smooth functions with exponential strip decay:

$$
\mathcal{S}_{\text{exp}}(\mathbb{R}) \coloneq \left\{ g_{0} \in \mathcal{S}(\mathbb{R}) \;\middle\vert{}\; \exists \delta > 0, \; \forall m \in \mathbb{N}, \; \sup_{u \in \mathbb{R}} e^{\left(\frac{1}{2} + \delta\right)\lvert u \rvert} \lvert g_{0}^{(m)}(u) \rvert < \infty \right\}
$$

equipped with spatial involution $g_{0}^*(u) \coloneq \overline{g_{0}(-u)}$ and auto-correlation convolution:

$$
g(u) \coloneq (g_{0} * g_{0}^*)(u) \coloneq \int_{-\infty}^{\infty} g_{0}(v) \overline{g_{0}(v - u)} \, dv \in \mathcal{S}_{\text{exp}}(\mathbb{R})
$$

By the Paley-Wiener-Schwartz theorem, $h_{0}(z) \coloneq \int_{-\infty}^{\infty} g_{0}(u) e^{i z u} \, du$ is holomorphic and rapidly decaying across the strip $\lvert \operatorname{Im}(z) \rvert \le \frac{1}{2} + \delta$, so $h(z) \coloneq \int_{-\infty}^{\infty} g(u) e^{i z u} \, du = h_{0}(z) \overline{h_{0}(\bar{z})}$ satisfies every hypothesis of [[#^def-6-4|Definition 6.4]] and obeys $h(r) = \lvert h_{0}(r) \rvert^{2} \ge 0$ for all $r \in \mathbb{R}$. Define the Weil distribution functional $W: \mathcal{S}_{\text{exp}}(\mathbb{R}) \to \mathbb{C}$ by the spectral-adelic pairing of [[#^thm-6-5|Theorem 6.5]]: $W(g) \coloneq \sum_{\rho \in Z_{\Lambda}} h(r_{\rho})$.


<br>

##### Theorem 6.6: Bidirectional Weil Positivity Equivalence for the Riemann Hypothesis ^thm-6-6

*Parent Derivation:* [[#^thm-6-4|Theorem 6.4]], [[#^thm-6-5|Theorem 6.5]], [[#^def-6-5|Definition 6.5]].

The Riemann Hypothesis ($\forall \rho \in Z_{\Lambda}, \, \operatorname{Re}(\rho) = \frac{1}{2}$) holds if and only if the explicit distribution functional $W$ is positive-semidefinite on all exponentially weighted Schwartz auto-correlations:

$$
\left( \forall \rho \in Z_{\Lambda}, \, \operatorname{Re}(\rho) = \frac{1}{2} \right) \iff \forall g_{0} \in \mathcal{S}_{\text{exp}}(\mathbb{R}), \quad W(g_{0} * g_{0}^*) \ge 0
$$

*Intuition:* Every auto-correlation test transform $h(z) = h_{0}(z)\overline{h_{0}(\bar{z})}$ is non-negative along the real spectral axis $r \in \mathbb{R}$ ($\operatorname{Re}(\rho) = \frac{1}{2}$), so on-line zeros force $W(g_{0} * g_{0}^*) \ge 0$. Conversely, any off-line zero $\rho_{0}$ comes with a mirror partner $1 - \bar{\rho}_{0}$ at $r_{3} = \bar{r}_{0}$, allowing a sharply tuned Gaussian wave packet to assign an exponentially dominant negative weight to the pair $(r_{0}, r_{3})$ and drive $W(g_{0} * g_{0}^*) < 0$.

*Proof:*

1. **Forward Necessity ($\text{RH} \implies W(g_{0} * g_{0}^*) \ge 0$):** Assume $\beta_{\rho} = \operatorname{Re}(\rho) = \frac{1}{2}$ for every $\rho \in Z_{\Lambda}$. Then $r_{\rho} = \gamma_{\rho} - i(\beta_{\rho} - \frac{1}{2}) = \gamma_{\rho} \in \mathbb{R}$ for all $\rho$, so [[#^def-6-5|Definition 6.5]] gives $h(r_{\rho}) = \lvert h_{0}(\gamma_{\rho}) \rvert^{2} \ge 0$ term-by-term, yielding $W(g_{0} * g_{0}^*) = \sum_{\rho \in Z_{\Lambda}} \lvert h_{0}(\gamma_{\rho}) \rvert^{2} \ge 0$.

2. **Contrapositive Setup ($\neg\text{RH}$ Maximal Off-Line Zero Quartet):** Conversely, suppose $\neg\text{RH}$ holds, so $\delta \coloneq \sup_{\rho \in Z_{\Lambda}} \lvert \operatorname{Re}(\rho) - \frac{1}{2} \rvert \in (0, \frac{1}{2}]$. Because all non-trivial zeros satisfy $0 < \operatorname{Re}(\rho) < 1$ and only finitely many zeros share any ordinate height (or lie near a supremum strip), choose $\rho_{0} = \beta_{0} + i\gamma_{0} \in Z_{\Lambda}$ attaining $\lvert \beta_{0} - \frac{1}{2} \rvert = \delta$; by [[#^thm-6-4|Theorem 6.4]] ($\Lambda(s) = \Lambda(1 - s)$) and Schwarz reflection ($\Lambda(\bar{s}) = \overline{\Lambda(s)}$), replacing $\rho_{0}$ by $1 - \bar{\rho}_{0}$ if needed gives $\beta_{0} = \frac{1}{2} + \delta$, producing the conjugate spectral pair $r_{0} \coloneq \gamma_{0} - i\delta$ and $r_{3} \coloneq \gamma_{0} + i\delta = \bar{r}_{0}$.

3. **Localized Schwartz-Gaussian Probing Packet:** Fix $c \in \mathbb{R}$ with $0 < \lvert c \rvert < \delta$ and bandwidth $\epsilon > 0$, and define the entire Gaussian-polynomial probing transform $h_{0}(z) \coloneq (z - \gamma_{0} + ic) \exp\left(-\frac{(z - \gamma_{0})^{2}}{2\epsilon^{2}}\right)$ (whose inverse Fourier transform $g_{0}$ decays super-exponentially and hence lies in $\mathcal{S}_{\text{exp}}(\mathbb{R})$ by [[#^def-6-5|Definition 6.5]]). Evaluating at $r_{0} = \gamma_{0} - i\delta$ and $r_{3} = \gamma_{0} + i\delta$ gives $h_{0}(r_{0}) = i(c - \delta) \exp(\delta^{2} / (2\epsilon^{2}))$ and $h_{0}(r_{3}) = i(c + \delta) \exp(\delta^{2} / (2\epsilon^{2}))$, so their combined spectral contribution is strictly negative:

$$
h(r_{0}) + h(r_{3}) = h_{0}(r_{0}) \overline{h_{0}(r_{3})} + h_{0}(r_{3}) \overline{h_{0}(r_{0})} = 2(c^{2} - \delta^{2}) \exp\left(\frac{\delta^{2}}{\epsilon^{2}}\right) < 0
$$

4. **Asymptotic Negative Explosion ($\epsilon \to 0^{+}$):** Along the real line $r \in \mathbb{R}$, $0 \le h(r) = [(r - \gamma_{0})^{2} + c^{2}] \exp(-(r - \gamma_{0})^{2}/\epsilon^{2}) \le \epsilon^{2} e^{-1} + c^{2} = \mathcal{O}(1)$ with Gaussian tail decay away from $\gamma_{0}$, so the zero-density bound $N(T) = \mathcal{O}(T \ln T)$ bounds the entire on-line sum by $\mathcal{O}(1)$. By maximality of $\delta$, every secondary off-line zero $\rho' = \frac{1}{2} \pm \delta' + i\gamma'$ satisfies $\delta' \le \delta$ (with $\gamma' \neq \gamma_{0}$ whenever $\delta' = \delta$, including any conjugate mirror at $-\gamma_{0}$ when $\gamma_{0} \neq 0$), so its real exponent $(\delta'^{2} - (\gamma' - \gamma_{0})^{2})/\epsilon^{2}$ is strictly less than $\delta^{2}/\epsilon^{2}$ and exponentially dominated as $\epsilon \to 0^{+}$. Hence $\lim_{\epsilon \to 0^{+}} W(g_{0} * g_{0}^*) = -\infty$, yielding $W(g_{0} * g_{0}^*) < 0$ for sufficiently small $\epsilon > 0$ and proving the equivalence.

**Emergent Isomorphism Bridge 7 (Tate's Thesis and Weil's Spectral Positivity Criterion):** In classical analytic number theory, Bernhard Riemann (1859) established the functional equation of $\zeta(s)$ via Jacobi theta-function modularity on $\mathbb{R}$, John Tate (1950) generalized it via Fourier analysis on the idele group $\mathbb{I}_{\mathbb{Q}}$, and André Weil (1952) reformulated the Riemann Hypothesis as reflection positivity of an explicit distribution functional. Under [[#^def-0-1|Definition 0.1]], [[#^thm-6-2|Theorem 6.2]], [[#^thm-6-4|Theorem 6.4]], [[#^thm-6-5|Theorem 6.5]], and [[#^thm-6-6|Theorem 6.6]] close the entire six-stratum constructive arc: the Gaussian-ball product kernel $f(x) = e^{-\pi x_{\infty}^{2}} \prod_{p} \mathbf{1}_{\mathbb{Z}_{p}}(x_{p})$ acts as the self-dual ground state ($\widehat{f} = f$) of the adelic phase space $\mathbb{A}_{\mathbb{Q}}$ built from $\Sigma = \{\Xi\}$, turning Riemann's symmetry $\Lambda(1 - s) = \Lambda(s)$ into global Fourier self-duality and translating the critical-line hypothesis $\operatorname{Re}(\rho) = \frac{1}{2}$ into positivity of auto-correlation expectation values $W(g_{0} * g_{0}^*) \ge 0$.

*Exit Handoff:* We have completed the six-stratum constructive derivation from the singleton alphabet $\Sigma = \{\Xi\}$ to Tate's functional equation and Weil's spectral positivity criterion. To enable immediate cross-referencing across computer science, information theory, theoretical physics, and pure mathematics, Appendix A synthesizes all emergent structures in a unified Rosetta Stone and anchor index.

---

---

# Appendix A: Cross-Disciplinary Rosetta Stone and Unified Notation Index ^app-a

*Entry Primer:* Throughout Sections 1 through 6, every algebraic ring, topological space, measure, and transcendental constant was constructed strictly forward from the singleton alphabet $\Sigma = \{\Xi\}$ ([[#^postulate-0-1|Postulate 0.1]], [[#^axiom-1-1|Axiom 1.1]]) and re-contextualized via post-proof Emergent Isomorphism Bridges ([[#^def-0-1|Definition 0.1]]). To provide immediate cross-referencing across disciplines, this appendix formalizes the three canonical disciplinary projections of the treatise, presents a unified Rosetta Stone spanning all six strata, indexes every symbol in ascending causal order, and verifies global deductive closure.

## A.1 Cross-Disciplinary Projection Functors and Rosetta Stone ^app-a-1

Because every construct in $\mathcal{G} = (\mathcal{V}, \mathcal{E})$ ([[#^def-0-2|Definition 0.2]]) is built from finitary discrete operations and projective limits, each node simultaneously admits an algorithmic interpretation in computer science, a state-space or entropic interpretation in physics and information theory, and a structural interpretation in classical pure mathematics.


<br>

##### Definition A.1: Cross-Disciplinary Projection Triplet ^def-a-1

*Parent Derivation:* [[#^def-0-1|Definition 0.1]], [[#^def-0-2|Definition 0.2]], [[#^def-0-3|Definition 0.3]], [[#^thm-0-1|Theorem 0.1]].

Let $\mathcal{X} \in \mathcal{V}$ be any constructive structure established across the Six-Stratum Hierarchy $(S_{1}, \dots, S_{6})$ of [[#^def-0-3|Definition 0.3]]. Define its **Cross-Disciplinary Projection Triplet** as the ordered assignment:

$$
\Pi(\mathcal{X}) \coloneq \left( \Pi_{\text{CS}}(\mathcal{X}), \, \Pi_{\text{Phys}}(\mathcal{X}), \, \Pi_{\text{Math}}(\mathcal{X}) \right)
$$

where $\Pi_{\text{CS}}(\mathcal{X})$ identifies the corresponding data structure, rewrite machine, or hardware automaton in computer science; $\Pi_{\text{Phys}}(\mathcal{X})$ identifies the corresponding state-counting measure, channel capacity, metric tensor, or conservation law in information theory and physics; and $\Pi_{\text{Math}}(\mathcal{X})$ identifies the corresponding classical object in algebra, topology, or analytic number theory.

Evaluating $\Pi(\mathcal{X})$ across all fourteen foundational milestones of Sections 1 through 6 yields the following unified Rosetta Stone:

| Stratum | Constructive Object | Computer Science & Automata ($\Pi_{\text{CS}}$) | Information Theory & Physics ($\Pi_{\text{Phys}}$) | Classical Mathematics ($\Pi_{\text{Math}}$) | Canonical Node |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $S_{1}$ | $(\Sigma^*, \cdot, \varepsilon)$ | Free monoid & singly-linked unary tally list | Linear microstate accumulation ($N$ states) | Additive commutative monoid $(\mathbb{N}, +, 0)$ | [[#^thm-1-1\|Theorem 1.1]] |
| $S_{1}$ | $\text{flatMap}: \Sigma^* \times \Sigma^* \to \Sigma^*$ | Monadic `bind` & uniform string homomorphism | Coarse-grained block substitution scaling | Commutative semiring $(\mathbb{N}, +, \times, 0, 1)$ | [[#^thm-1-2\|Theorem 1.2]] |
| $S_{1}$ | $(w \cdot B, q) \to_{B} (w, q \cdot \Xi)$ | Strongly normalizing term-rewriting system (TRS) | Monotonic energy dissipation $\mu(w, q) = \text{len}(w)$ | Euclidean division with remainder ($w = qB + r$) | [[#^thm-1-8\|Theorem 1.8]] |
| $S_{1}$ | $\mathbb{Z}, \mathbb{Q}, \mathbb{R} = \overline{\mathbb{Q}}_{\lvert \cdot \rvert_{\infty}}$ | Exact rational arithmetic & Cauchy stream limits | Continuous real parameter & logarithmic scale | Grothendieck ring, fraction field & Cauchy reals | [[#^thm-1-11\|Theorem 1.11]] |
| $S_{2}$ | $\mathcal{P} = \{p_{1}, p_{2}, \dots\}$ | Irreducible multiplicative string atoms | Prime degrees of freedom / independent rotors | Prime numbers & Fundamental Theorem of Arithmetic | [[#^thm-2-2b\|Theorem 2.2b]] |
| $S_{2}$ | $\Psi_{k}: \mathbb{Z}/N_{k}\mathbb{Z} \xrightarrow{\cong} \prod_{i=1}^{k} \mathbb{F}_{p_{i}}$ | Carry-free Residue Number System (RNS) encoding | Orthogonal channels ($I(X_{i}; X_{j}) = 0$, $H = \log_{2} N_{k}$) | Chinese Remainder Theorem ring isomorphism | [[#^thm-2-4\|Theorem 2.4]] |
| $S_{3}$ | $\mathcal{Z}_{k} = \mathbb{Z} \times \{0, \dots, N_{k} - 1\}$ | Bounded-carry mixed-radix register ($c \in \{0, 1\}$) | Decoupled local phase & global scale coordinate | Exact bijective ring transport of $\mathbb{Z}$ | [[#^thm-3-1\|Theorem 3.1]] |
| $S_{3}$ | $\mathcal{F}_{\mathbb{Z}} \subset \mathbb{Z} \times \Sigma^* \times \Sigma^*$ | Signed-exponent floating-point monoid triple | Multi-scale exponential & $p$-adic valuation | Homomorphic rational scaling ($\text{Val}: \mathcal{F}_{\mathbb{Z}} \to \mathbb{Q}_{\ge 0}$) | [[#^thm-3-7\|Theorem 3.7]] |
| $S_{3}$ | $\mathcal{M} = (\mathcal{S}, \Sigma_{\Delta}, \delta, \dagger)$ | Deterministic finite-state transducer (FST) | Chiral $\mathbb{Z}/2\mathbb{Z}$ parity selection rules | Modulo-$6$ wheel sieve $(\mathbb{Z}/6\mathbb{Z})^\times \cong C_{2}$ | [[#^thm-3-9\|Theorem 3.9]] |
| $S_{4}$ | $R_{\infty} = \varprojlim_{k} (\mathbb{Z}/N_{k}\mathbb{Z})$ | Infinite prefix trie boundary $\partial \mathcal{T}$ | Cylinder Haar measure $\mu(B_{k}) = N_{k}^{-1}$ | Stone-Cantor space $\mathbf{2}^{\mathbb{N}}$ & Rohlin $[0, 1]$ | [[#^thm-4-2\|Theorem 4.2]] |
| $S_{4}$ | $\mu(B_{k}) = 2^{-H_{k}} = (g^{(k)})^{-1/2}$ | Exponential trie address resolution $\delta_{k} = N_{k}^{-1}$ | Tripartite entropy-Fisher curvature identity | van der Put ultrametric calculus & Fisher metric | [[#^thm-4-13\|Theorem 4.13]] |
| $S_{5}$ | $\rho_{k} \to 6/\pi^{2}$ & $N_{k}^{1/\text{len}(p_{k})} \to e$ | 2D collision avoidance & 1D trie branching rate | Transverse rotational vs. longitudinal bit density | Emergent constants $\pi$ and $e$ from prime laws | [[#^thm-5-4\|Theorem 5.4]] |
| $S_{5}$ | $\mathbb{A}_{\mathbb{Q}} = \mathbb{R} \times \prod'_{p} (\mathbb{Q}_{p}, \mathbb{Z}_{p})$ | Coherent Archimedean + $p$-adic Tri-String vector | Scale-invariant phase space ($\prod_{v \le \infty} \lvert q \rvert_{v} = 1$) | Restricted adele ring & Pontryagin $\mathbb{Q}^\perp = \Delta(\mathbb{Q})$ | [[#^thm-5-11\|Theorem 5.11]] |
| $S_{6}$ | $\widehat{f} = f$ & $W(g_{0} * g_{0}^*) \ge 0$ | Self-dual Gaussian-ball spectral filter | Vacuum eigenstate & reflection positivity | Tate's $\Lambda(1 - s) = \Lambda(s)$ & Weil RH criterion | [[#^thm-6-6\|Theorem 6.6]] |

---

## A.2 Unified Symbol and Operator Index ^app-a-2


<br>

##### Definition A.2: Canonical Symbol Registry ^def-a-2

*Parent Derivation:* [[#^def-0-2|Definition 0.2]], [[#^def-a-1|Definition A.1]].

The **Canonical Symbol Registry** indexes every primitive, algebraic operator, topological space, measure, and spectral functional introduced across epochs $t_{0}$ through $t_{6}$ in strict order of first constructive appearance:

| Symbol | Signature / Domain | Operational & Mathematical Meaning | Defining Node |
| :--- | :--- | :--- | :--- |
| $\Sigma, \Xi$ | $\Sigma \coloneq \{\Xi\}$ | Singleton alphabet and indivisible unary tally token | [[#^axiom-1-1\|Axiom 1.1]] |
| $\Sigma^*, \varepsilon, S$ | Initial algebra over $(\varepsilon, S)$ | Free monoid of finite tally words, empty word, and unary successor | [[#^def-1-1\|Definition 1.1]] |
| $\cdot$ | $\Sigma^* \times \Sigma^* \to \Sigma^*$ | Recursive word concatenation (commutative monoid addition) | [[#^def-1-2\|Definition 1.2]] |
| $\text{flatMap}$ | $\Sigma^* \times \Sigma^* \to \Sigma^*$ | Uniform token substitution endomorphism (semiring multiplication) | [[#^def-1-3\|Definition 1.3]] |
| $\text{len}, \Xi^{n}$ | $\Sigma^* \to \mathbb{N}$ | Bijective tally length projection and canonical word of length $n$ | [[#^def-1-4\|Definition 1.4]] |
| $\to_{B}$ | $(\Sigma^* \times \Sigma^*) \times (\Sigma^* \times \Sigma^*)$ | Terminating Euclidean prefix-subtraction rewrite relation | [[#^def-1-5\|Definition 1.5]] |
| $\mathbb{Z}, \sim_{+}$ | $(\Sigma^* \times \Sigma^*) / \sim_{+}$ | Grothendieck difference ring of integers with $+_{\mathbb{Z}}, \times_{\mathbb{Z}}$ | [[#^def-1-6\|Definition 1.6]] |
| $\mathbb{Q}, \sim_{\times}$ | $(\mathbb{Z} \times (\mathbb{Z} \setminus \{0_{\mathbb{Z}}\})) / \sim_{\times}$ | Multiplicative field of fractions with $+_{\mathbb{Q}}, \times_{\mathbb{Q}}$ | [[#^def-1-7\|Definition 1.7]] |
| $\mathbb{R}, \lvert \cdot \rvert_{\infty}$ | $\overline{\mathbb{Q}}_{\lvert \cdot \rvert_{\infty}}$ | Cauchy completion of $\mathbb{Q}$ under Archimedean absolute value | [[#^def-1-8\|Definition 1.8]] |
| $\exp, \ln, \log_{2}$ | $\mathbb{R} \leftrightarrow \mathbb{R}_{> 0}$ | Analytic exponential and logarithmic functions on $\mathbb{R}$ | [[#^thm-1-11\|Theorem 1.11]] |
| $u \mid_{\Sigma} v$ | Predicate on $\Sigma^* \setminus \{\varepsilon\}$ | Unary word divisibility ($\exists w \neq \varepsilon, \, \text{flatMap}(w, u) = v$) | [[#^def-2-1\|Definition 2.1]] |
| $\mathcal{P}, p_{k}$ | $\mathcal{P} = \{p_{1}, p_{2}, \dots\} \subset \Sigma^*$ | Set and length-ordered infinite sequence of prime words | [[#^def-2-2\|Definition 2.2]], [[#^def-2-3\|Definition 2.3]] |
| $P_{k}, N_{k}$ | $P_{k} \in \Sigma^*, \, N_{k} = \text{len}(P_{k})$ | $k$-th primorial word and scalar primorial product $\prod_{i=1}^{k} \text{len}(p_{i})$ | [[#^def-2-4\|Definition 2.4]] |
| $\Psi_{k}$ | $\mathbb{Z}/N_{k}\mathbb{Z} \xrightarrow{\cong} \prod_{i=1}^{k} \mathbb{F}_{p_{i}}$ | Canonical Chinese Remainder Theorem residue ring isomorphism | [[#^def-2-5\|Definition 2.5]] |
| $\Omega_{k}, \mathbb{P}_{k}, X_{i}$ | $\Omega_{k} = \mathbb{Z}/N_{k}\mathbb{Z}$ | Uniform residue probability space and $i$-th prime channel projection | [[#^def-2-6\|Definition 2.6]], [[#^def-2-7\|Definition 2.7]] |
| $H(X_{i}), I(X_{i}; X_{j})$ | $\Omega_{k} \to \mathbb{R}_{\ge 0}$ | Shannon channel entropy in bits and pairwise mutual information | [[#^def-2-8\|Definition 2.8]] |
| $\mathcal{Z}_{k}, \nu_{k}, \mathcal{M}_{k}$ | $\mathbb{Z} \times \{0, \dots, N_{k} - 1\} \leftrightarrow \mathbb{Z}$ | Mixed-radix primorial tuple state space and Euclidean bijections | [[#^def-3-1\|Definition 3.1]], [[#^def-3-2\|Definition 3.2]] |
| $\oplus, \otimes, \ominus, \oslash, \odot$ | Binary operators on $\mathcal{Z}_{k}$ | Bounded-carry/borrow tuple arithmetic and Euclidean operators | [[#^thm-3-2\|Theorem 3.2]], [[#^def-3-3\|Definition 3.3]] |
| $\mathcal{F}, \mathcal{F}_{\mathbb{Z}}, \text{Val}$ | $[e, \Xi^{b}, \Xi^{m}] \mapsto \mathbb{Q}_{\ge 0}$ | Unsigned and signed-exponent Tri-String floating-point spaces | [[#^def-3-4\|Definition 3.4]], [[#^def-3-5\|Definition 3.5]] |
| $\digamma, \mathcal{M}, \dagger$ | $\mathcal{P}_{\ge 5} \to \{-1, +1\}$ | Lowercase digamma mod-$6$ parity operator and chiral gap FST | [[#^def-3-6\|Definition 3.6]], [[#^def-3-7\|Definition 3.7]] |
| $R_{\infty}, B_{k}(\vec{r}_{k})$ | $\varprojlim_{k} (\mathbb{Z}/N_{k}\mathbb{Z}) \cong \prod_{i=1}^{\infty} \mathbb{F}_{p_{i}}$ | Profinite square-free limit ring and clopen cylinder basis | [[#^def-4-2\|Definition 4.2]], [[#^thm-4-1\|Theorem 4.1]] |
| $\mathcal{T}, d(x, y)$ | $R_{\infty} \times R_{\infty} \to \mathbb{R}_{\ge 0}$ | Infinite primorial prefix trie and complete ultrametric distance | [[#^def-4-3\|Definition 4.3]], [[#^def-4-4\|Definition 4.4]] |
| $\Delta_{\mathcal{T}}, D_{\text{KL}}$ | $V(\mathcal{T}) \times V(\mathcal{T}) \to \mathbb{N}, \mathbb{R}_{\ge 0}$ | Trie LCA geodesic distance and branch rewrite KL-divergence | [[#^def-4-5\|Definition 4.5]], [[#^def-4-6\|Definition 4.6]] |
| $\delta_{k}, \phi_{\vec{r}_{k}}, D_{\mathcal{T}}^{(k)}$ | $R_{\infty} \to \mathbb{R}$ | Valuation step $N_{k}^{-1}$, van der Put indicator, and trie derivative | [[#^def-4-7\|Definition 4.7]], [[#^thm-4-11\|Theorem 4.11]] |
| $\mu, H_{k}, g_{\theta\theta}, g^{(k)}$ | $\mu(B_{k}) = 2^{-H_{k}} = (g^{(k)})^{-1/2}$ | Normalized Haar measure, surprise entropy, and dual Fisher metrics | [[#^def-4-8\|Definition 4.8]], [[#^def-4-9\|Definition 4.9]] |
| $\rho_{k}, \pi$ | $\Omega_{k}^{2} \to \mathbb{Q}_{> 0}, \, \pi \in \mathbb{R}_{> 0}$ | Bivariate prime non-collision density and emergent circle constant | [[#^def-5-1\|Definition 5.1]], [[#^thm-5-2\|Theorem 5.2]] |
| $\theta(x), \sigma_{k}, e$ | $\mathbb{R}_{\ge 2} \to \mathbb{R}_{\ge 0}, \, e = \exp(1)$ | Chebyshev first function, specific entropy density, and Euler's number | [[#^def-5-2\|Definition 5.2]], [[#^thm-5-4\|Theorem 5.4]] |
| $v_{p}, \mathbb{Z}_{p}, \mathbb{Q}_{p}$ | $\varprojlim_{n} (\mathbb{Z}/p^{n}\mathbb{Z}) \subset \operatorname{Frac}(\mathbb{Z}_{p})$ | Discrete $p$-adic valuation, compact $p$-adic integers, and local field | [[#^lem-5-5a\|Lemma 5.5a]], [[#^def-5-3\|Definition 5.3]], [[#^def-5-4\|Definition 5.4]] |
| $\mathbb{A}_{\mathbb{Q}}, \Delta, d\mu_{\mathbb{A}}$ | $\mathbb{R} \times \prod'_{p} (\mathbb{Q}_{p}, \mathbb{Z}_{p})$ | Restricted adele ring, diagonal rational lattice, and product Haar measure | [[#^def-5-5\|Definition 5.5]], [[#^def-5-6\|Definition 5.6]] |
| $\psi, \mathbb{Q}^\perp$ | $\mathbb{A}_{\mathbb{Q}} \to S^{1} \subset \mathbb{C}^\times$ | Global adelic additive character and self-dual rational annihilator | [[#^def-5-7\|Definition 5.7]], [[#^thm-5-11\|Theorem 5.11]] |
| $\mathcal{S}(\mathbb{A}_{\mathbb{Q}}), \widehat{f}$ | Adelic Schwartz-Bruhat space | Factorizable test functions and global adelic Fourier transform | [[#^def-6-1\|Definition 6.1]], [[#^thm-6-2\|Theorem 6.2]] |
| $\mathbb{I}_{\mathbb{Q}}, \lVert \cdot \rVert, d^\times x$ | $\mathbb{A}_{\mathbb{Q}}^\times \to \mathbb{R}_{> 0}$ | Idele group, global idele norm, and normalized multiplicative Haar measure | [[#^def-6-3\|Definition 6.3]] |
| $\Lambda(s)$ | $\pi^{-s/2}\Gamma(s/2)\zeta(s)$ | Completed Riemann zeta function satisfying $\Lambda(1 - s) = \Lambda(s)$ | [[#^thm-6-3\|Theorem 6.3]], [[#^thm-6-4\|Theorem 6.4]] |
| $Z_{\Lambda}, r_{\rho}$ | $\Lambda(\rho) = 0, \, r_{\rho} = -i(\rho - \frac{1}{2})$ | Multiset of non-trivial zeta zeros and critical-line spectral parameter | [[#^thm-6-5\|Theorem 6.5]] |
| $\mathcal{S}_{\text{exp}}(\mathbb{R}), W(g)$ | Involutive test algebra $\to \mathbb{C}$ | Exponentially weighted Schwartz algebra and Weil distribution functional | [[#^def-6-5\|Definition 6.5]], [[#^thm-6-6\|Theorem 6.6]] |

---

## A.3 Complete Treatise Closure Verification ^app-a-3


<br>

##### Theorem A.1: Global Constructive Closure from Singleton Alphabet to Spectral Positivity ^thm-a-1

*Parent Derivation:* [[#^postulate-0-1|Postulate 0.1]], [[#^thm-0-1|Theorem 0.1]], [[#^thm-1-11|Theorem 1.11]], [[#^thm-2-8|Theorem 2.8]], [[#^thm-3-9|Theorem 3.9]], [[#^thm-4-13|Theorem 4.13]], [[#^thm-5-11|Theorem 5.11]], [[#^thm-6-6|Theorem 6.6]], [[#^def-a-1|Definition A.1]], [[#^def-a-2|Definition A.2]].

Every mathematical object, analytic constant, and spectral equivalence indexed in [[#^def-a-1|Definition A.1]] and [[#^def-a-2|Definition A.2]] is derived strictly feed-forward from [[#^axiom-1-1|Axiom 1.1]] ($\Sigma = \{\Xi\}$) in compliance with [[#^postulate-0-1|Postulate 0.1]] and [[#^thm-0-1|Theorem 0.1]], forming a single unbroken deductive chain from discrete combinatorics to the Weil positivity criterion for the Riemann Hypothesis.

*Intuition:* Tracing the dependency graph backward from `Theorem 6.6` collapses every analytic, probabilistic, and topological layer sequentially onto the free monoid $(\Sigma^*, \cdot, \text{flatMap}, \varepsilon, \Xi)$, proving that no external primitive was imported at any stage.

*Proof:*

1. **Discrete Algebraic and Continuum Closure ($S_{1}$):** Starting solely from $\Sigma = \{\Xi\}$ ([[#^axiom-1-1|Axiom 1.1]]), Section 1 establishes the commutative semiring $(\Sigma^*, \cdot, \text{flatMap}, \varepsilon, \Xi)$, Peano arithmetic ($\mathbb{N}$), terminating Euclidean rewriting ($\to_{B}$), the Grothendieck ring $\mathbb{Z}$, the fraction field $\mathbb{Q}$, and the complete Archimedean field $\mathbb{R}$ with $\exp, \ln, \log_{2}$ ([[#^thm-1-11|Theorem 1.11]]).

2. **Prime Factorization, CRT Orthogonality, and Finite Automata ($S_{2} \to S_{3}$):** Section 2 derives the infinite prime word sequence $\mathcal{P}$, unique prime word factorization, the CRT ring isomorphism $\Psi_{k}$, and zero Shannon mutual information $I(X_{i}; X_{j}) = 0$ with additive capacity $\log_{2} N_{k}$ ([[#^thm-2-8|Theorem 2.8]]), which Section 3 lifts into unbounded mixed-radix registers $\mathcal{Z}_{k}$, signed Tri-Strings $\mathcal{F}_{\mathbb{Z}}$, and the deterministic Chiral Prime Parity FST $\mathcal{M}$ ([[#^thm-3-9|Theorem 3.9]]).

3. **Profinite Continuum Duality and Information Geometry ($S_{4}$):** Section 4 passes to the projective limit $R_{\infty} = \varprojlim_{k} (\mathbb{Z}/N_{k}\mathbb{Z})$, proving homeomorphism to the Cantor space $\mathbf{2}^{\mathbb{N}}$, measure isomorphism to $([0, 1], \lambda)$, non-Archimedean van der Put calculus, and the tripartite equivalence $\mu(B_{k}) = 2^{-H_{k}} = (g^{(k)})^{-1/2} = \delta_{k}$ ([[#^thm-4-13|Theorem 4.13]]).

4. **Emergent Transcendentals, Adelic Self-Duality, and Spectral Positivity ($S_{5} \to S_{6}$):** Section 5 extracts $\pi$ and $e$ from asymptotic prime statistics, constructs vertical $p$-adic towers $\mathbb{Q}_{p}$, and establishes Artin scale invariance and Pontryagin autoduality $\mathbb{Q}^\perp = \Delta(\mathbb{Q})$ on $\mathbb{A}_{\mathbb{Q}}$ ([[#^thm-5-11|Theorem 5.11]]), enabling Section 6 to prove adelic Poisson summation, Tate's functional equation $\Lambda(1 - s) = \Lambda(s)$, and the bidirectional equivalence between Weil positivity on $\mathcal{S}_{\text{exp}}(\mathbb{R})$ and the Riemann Hypothesis ([[#^thm-6-6|Theorem 6.6]]).

---

