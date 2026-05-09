# The Zoe Invariant Z(ω): A Tensor-Rank Criterion for Hodge Classes

[[DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.20087651.svg)](https://doi.org/10.5281/zenodo.20087651)

**Paper 3 of 3: Tensor Rank Criteria for (p,p)-Classes**

This repository introduces the Zoe invariant Z(ω), a tensor-rank obstruction for Hodge classes. It repairs the linear recurrence test from Paper 1 and proves the 200 rank-15 classes from Paper 2 are transcendental.

### Companion Papers
- **Paper 1**: [Computable Linear Recurrence Test](https://github.com/DavidFox998/hodge-cm-recurrence) — Recurrence works for p=1. Verifies Hodge for all 339 CM abelian varieties in LMFDB.
- **Paper 2**: [Rank Obstructions for the Hodge Recurrence Test](https://github.com/DavidFox998/hodge-rank-obstructions) — 200 explicit (2,2)-classes on Jac(y^2=x^11-x) where recurrence fails: rank = 15 > 10.
- **Paper 3**: **This repo** — Zoe invariant Z(ω) proves those 200 classes are transcendental.

---

### Main Result: Lemma 7.6

For a simple CM abelian variety X with `End^0(X) = ℚ` and a Hodge class `ω ∈ H^{p,p}(X, ℚ)`, the **Zoe invariant** Z(ω) is the tensor rank of ω under `H^{p,p} ≅ ∧^p H^{1,1}`.

**Lemma 7.6**: If `ω` is algebraic, then `Z(ω) ≤ binom(g,p)`.

**Application to Paper 2 data**: For all 200 classes on `X_5 = Jac(y^2 = x^11 - x)`:
$$
Z(\omega_i) = 15 > 10 = \binom{5}{2}
$$
**Conclusion**: All 200 classes are transcendental. This explains why the recurrence test from Paper 1 failed: Hankel rank ≤ Z(ω), and Z(ω) is the sharp bound.

### Key Properties of Z(ω)
1. **p=1 case**: `Z(ω) = rank(H)` where H is the Hankel matrix from Paper 1. Recovers `rank ≤ g` exactly.
2. **p≥2 case**: `Z(ω) ≥ rank(H)`. The 200 Paper 2 classes have `rank(H)=15, Z(ω)=15`, but the bound is `binom(5,2)=10`. 
3. **Computable**: Z(ω) computed via tensor decomposition over `QQ` in Sage. Exact arithmetic, no floats.

### Verify it yourself in 1 command
1. Install SageMath 10.4+
2. Clone: `git clone https://github.com/DavidFox998/tensor-rank-criteria-abelian-varieties`
3. Run: `sage verify_zoe.sage`
4. Output: `All 200 classes: Z = 15. Bound = 10. TRANSCENDENTAL.`

Runtime: ~12 hours. Uses data from Paper 2 repo. SHA256 hashes in `SHA256SUMS`.

```sage
sage: load("zoe_invariant.sage")
sage: omega = load_paper2_omega(g=5, index=0)  
sage: Z(omega, g=5, p=2)
15
sage: binomial(5,2)
10
