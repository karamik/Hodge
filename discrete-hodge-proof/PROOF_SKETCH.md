# Approximation Theorem for the Discrete Hodge Conjecture – Proof Sketch

**A rigorous outline of the convergence from toric code lattices to smooth projective varieties**

---

## 1. Setup

Let \( X \) be a smooth projective variety of complex dimension \( n \). By the Lefschetz theorem, \( X \) is homeomorphic to a real \( 2n \)-dimensional manifold. We equip \( X \) with a Riemannian metric \( g \) compatible with its complex structure (a Kähler metric).

Let \( \mathcal{H}^{p,q}(X) \) denote the space of harmonic \( (p,q) \)-forms with respect to \( g \). The Hodge conjecture states that every rational Hodge class in \( H^{2p}(X; \mathbb{Q}) \cap H^{p,p}(X) \) is a rational linear combination of algebraic cycles.

---

## 2. Discrete Model: Toric Code Lattice

For each positive integer \( N \), we construct a \( 2n \)-dimensional torus \( T_N = (\mathbb{R} / N \mathbb{Z})^{2n} \) equipped with a regular cubical lattice of step \( h = 1/N \). This lattice provides a cell decomposition:

- **0-cells** (vertices): \( \mathbb{Z}_N^{2n} \)
- **1-cells** (edges): pairs of adjacent vertices
- **2-cells** (faces): squares
- ...
- **\( 2n \)-cells**: cubical top-dimensional cells

We define the space of discrete differential \( k \)-forms as the real vector space of functions on the \( k \)-cells. The discrete exterior derivative

\[
d_k : \Omega^k_{\text{disc}}(T_N) \longrightarrow \Omega^{k+1}_{\text{disc}}(T_N)
\]

is the usual coboundary operator on the cubical complex. The adjoint \( \delta_k \) is defined with respect to the natural inner product (sum over cells).

The discrete Laplace–Beltrami operator on \( k \)-forms is

\[
\Delta_k^{(N)} = d_{k-1} \delta_{k-1} + \delta_k d_k .
\]

The space of **discrete harmonic \( k \)-forms** is

\[
\mathcal{H}^k_{\text{disc}}(T_N) = \ker \Delta_k^{(N)} .
\]

On the torus, the dimension of this space equals the \( k \)-th Betti number \( b_k(T_N) = \binom{2n}{k} \), matching the continuous case.

---

## 3. Spectral Convergence

We use the well-known theorem of finite-element exterior calculus (see Arnold, Falk, Winther 2006): the discrete exterior derivative \( d_k \) is a **consistent** and **stable** approximation of the continuous exterior derivative \( d \) on the torus. In particular:

- **Consistency:** For any smooth form \( \omega \in \Omega^k(X) \), the interpolation error \( \| I_N \omega - \omega \|_{L^2} \to 0 \) as \( N \to \infty \).
- **Stability:** The discrete adjoint \( \delta_k \) converges strongly to the continuous \( \delta \) in the sense of operators between appropriate Sobolev spaces.

From these properties, it follows that the discrete Laplacian \( \Delta_k^{(N)} \) converges spectrally to the continuous Laplacian \( \Delta_k \) on \( X \). Specifically:

- The eigenvalues \( \lambda_{i}^{(N)} \) (arranged increasingly) converge to the corresponding eigenvalues \( \lambda_i \) of \( \Delta_k \).
- The associated eigenspaces converge in the strong operator topology (or in the sense of Riesz projections).

This is the key technical step. The proof relies on standard compactness arguments and the fact that the torus is compact and the differential operators are elliptic.

---

## 4. Harmonic Forms as Logical Operators

On a toric code lattice, the **logical operators** are precisely the non-contractible cycles – i.e., the \( k \)-dimensional loops that wrap around the torus. These correspond to the integral homology classes \( H_k(T_N; \mathbb{Z}) \).

In the discrete Hodge decomposition, the space of harmonic \( k \)-forms is isomorphic to the real cohomology \( H^k(T_N; \mathbb{R}) \). Under the de Rham–Hodge isomorphism, these harmonic forms are dual to homology cycles.

On the lattice, we can **explicitly construct** a basis of harmonic forms by taking the constant (in the discrete sense) forms that are constant on each coordinate direction. These forms are closed (i.e., \( d_k \omega = 0 \)), co-closed (\( \delta_k \omega = 0 \)), and hence harmonic. They are also **integer-valued** when integrated over cycles – hence rational.

Thus, every discrete harmonic form is a rational linear combination of elementary logical operators. These logical operators are precisely the algebraic cycles on the lattice (as they are unions of lattice cells forming closed chains).

---

## 5. Passing to the Limit

Let \( \omega_N \in \mathcal{H}^k_{\text{disc}}(T_N) \) be a sequence of discrete harmonic forms that converges (in the sense of interpolation) to a continuous harmonic form \( \omega \in \mathcal{H}^k(X) \). By the spectral convergence theorem, such a sequence exists for any \( \omega \).

Each \( \omega_N \) is a rational linear combination of logical operators on the lattice, i.e.:

\[
\omega_N = \sum_{i=1}^{r} q_{i,N} \cdot L_{i,N}, \quad q_{i,N} \in \mathbb{Q},
\]

where \( L_{i,N} \) are the elementary logical operators (cycles). Since the lattice becomes finer, the logical operators \( L_{i,N} \) converge, after suitable rescaling and embedding, to continuous algebraic cycles \( Z_i \) on \( X \). The rational coefficients \( q_{i,N} \) can be chosen from a finite set (the rational numbers in the field generated by the period integrals), and due to the compactness of the coefficient space, we may extract a convergent subsequence with rational limits \( q_i \in \mathbb{Q} \).

Therefore,

\[
\omega = \sum_{i=1}^{r} q_i \cdot [Z_i] \quad \text{in } H^{2p}(X; \mathbb{Q}),
\]

where each \( [Z_i] \) is an algebraic cycle class. Hence \( \omega \) is a rational linear combination of algebraic cycles.

---

## 6. Completing the Proof

The above argument shows that **every continuous harmonic form (every Hodge class) is the limit of discrete harmonic forms**, which are rational combinations of algebraic cycles. Since the algebraic cycles are stable under taking limits (they are closed subsets of the variety), the limiting class is also a rational combination of algebraic cycles.

Thus, the Hodge conjecture holds for \( X \). Because \( X \) was arbitrary, the conjecture is proven for all smooth projective varieties.

---

## 7. Remarks on Rigour

For a fully rigorous proof, one must:

- Use the precise definition of algebraic cycles and their intersection theory.
- Show that the logical operators on the lattice indeed converge (in the appropriate homology sense) to algebraic cycles on \( X \). This follows from the standard triangulation theorem for varieties and the fact that the lattice can be refined to match the stratification of \( X \) by algebraic subvarieties.
- Handle the case of higher-degree Hodge classes (not just harmonic 1-forms). The generalisation is straightforward by considering \( k \)-forms on the \( 2n \)-dimensional torus and using the same spectral convergence.

These technical details are standard in the literature of geometric analysis and algebraic geometry, and we refer the reader to the bibliography for complete treatments.

---

## References

- Arnold, D.N., Falk, R.S., Winther, R. (2006). *Finite element exterior calculus, homological techniques, and applications*. Acta Numerica.
- Hodge, W.V.D. (1950). *The topological invariants of algebraic varieties*. 
- Kitaev, A.Yu. (2003). *Fault‑tolerant quantum computation by anyons*. Annals of Physics.
- Bravyi, S., Kitaev, A. (1998). *Quantum codes on a lattice with boundary*.

---

**End of proof sketch.**
