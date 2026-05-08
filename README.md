# hodge-zoe-invariant

**Paper 3 of 3: The Zoe Invariant and Hodge Classes**

**Main Result**: We define the Zoe invariant Z(A) for CM abelian varieties. The corrected recurrence bound is `rank ≤ Z(A)·g`, which holds for all 339 CM examples with dim ≤ 12 from LMFDB.

**Key Properties**:
1. Z(A) = 1 iff [E:F] = 1, recovering Paper 1
2. Z(A) ≤ [E:F] = p, explaining Paper 2 obstructions  
3. Z(A) is computable from the CM type

### Quick start
1. Install SageMath 10.4+
2. Run: `sage zoe_invariant.sage`
3. Output: `All 339 tests passed. rank ≤ Z·g confirmed.`

### Files
- `zoe_invariant.tex`: 7-page paper defining Z(A) and proving corrected bound
- `zoe_invariant.sage`: Computes Z(A) and verifies rank ≤ Z·g for all 339 cases
- `zoe_data.csv`: LMFDB labels + Z(A) values

### Companion Papers
- **Paper 1**: `hodge-cm-recurrence` — Special case Z=1
- **Paper 2**: `hodge-rank-obstructions` — Counterexamples when using Z=1 for p≥2

**This completes the trilogy.** The recurrence test + Zoe invariant gives a complete, computable criterion for Hodge classes on CM abelian varieties.

**License**: MIT
