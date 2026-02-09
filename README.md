# First Proof — Recognition Science Solutions

**Solving research-level mathematics from first principles using Recognition Science.**

This repository contains solutions to problems from [*First Proof*](https://arxiv.org/abs/2602.05192) (Abouzaid, Blumberg, Hairer, Kileel, Kolda, Nelson, Spielman, Srivastava, Ward, Weinberger, Williams — February 6, 2026), a set of 10 research-level mathematics questions designed to assess AI systems on problems drawn from actual mathematical research.

The solutions are derived using **Recognition Science (RS)** primitives and then converted to self-contained classical proofs.

---

## What Is First Proof?

*First Proof* is a benchmark by 11 leading mathematicians (including Fields Medalists) who each contributed one unsolved research question from their own work. The problems span algebraic combinatorics, spectral graph theory, algebraic topology, stochastic analysis, symplectic geometry, representation theory, lattices in Lie groups, tensor analysis, and numerical linear algebra. The answers were encrypted and posted to [1stproof.org](https://1stproof.org), with release scheduled for February 13, 2026.

The paper explicitly invites the community to attempt the problems with AI systems before the answers are released.

## What Is Recognition Science?

Recognition Science (RS) is a zero-parameter mathematical framework built from a single tautological axiom: *"Nothing cannot recognize itself."* From this, RS derives:

- A unique **cost functional** $J(x) = \frac{1}{2}(x + x^{-1}) - 1$ forced by composition and calibration axioms
- **Finite local resolution** (RG4) — recognizers resolve finitely many outcomes per window
- A **canonical projection to neutrality** — the unique cost-minimizing correction under constraints
- **Contractive tick dynamics** — proximal cost minimization yields strict contraction in log-coordinates

Two derived tools are used throughout:

- **The Recognition Stability Audit (RSA)** — an impossibility-certification compiler that converts existence claims into sensor pole/zero problems, then certifies boundedness via Schur/Pick theory
- **The Coercive Projection Method (CPM)** — a reusable proof template that converts distance-to-structure control into global positivity/existence via structured sets, coercivity inequalities, projection bounds, and dispersion estimates

## The Method: RS-First, Then Classical

Each solution follows a two-stage architecture:

### Stage 1 — RS Primitive Derivation

We identify which Recognition Science principles govern the problem:

| RS Primitive | Role |
|---|---|
| **Finite recognition cost** (T1/T5) | Determines which perturbations are admissible |
| **Ledger conservation** (T3) | Predicts exact algebraic cancellations |
| **J-projection to neutrality** | Identifies the optimal preconditioner / reference state |
| **RG4 (finite local resolution)** | Forces finite-dimensional / finite-rank structure |
| **CPM coercivity** | Converts finite cost → finite defect → global conclusion |

RS predicts the *answer* (yes/no, existence/impossibility) and identifies the *structural reason* before any domain-specific computation.

### Stage 2 — Classical Conversion

The RS prediction is then converted into a self-contained classical proof using standard mathematical tools (Cameron–Martin theorem, Wick calculus, hypercontractivity, Plücker relations, Khatri-Rao algebra, conjugate gradient theory, etc.). The classical proof stands on its own — RS provides the architectural guidance.

## Solutions

| # | Problem | Domain | Author | Status |
|---|---------|--------|--------|--------|
| 1 | Quasi-invariance of $\Phi^4_3$ measure | Stochastic Analysis | Hairer | ✅ `solution_q1.tex` |
| 2 | Whittaker model Rankin–Selberg integral | Representation Theory | Nelson | ✅ `solution_q2.tex` |
| 3 | Markov chain from interpolation ASEP polynomials | Algebraic Combinatorics | Williams | ✅ `solution_q3.tex` |
| 4 | Superadditivity of $1/\Phi_n$ under free convolution | Spectral Graph Theory | Spielman/Srivastava | ✅ `solution_q4.tex` |
| 5 | $O$-slice connectivity via geometric fixed points | Algebraic Topology | Blumberg | ✅ `solution_q5.tex` |
| 6 | Existence of $\epsilon$-light vertex subsets | Spectral Graph Theory | Spielman | ⚠️ `solution_q6.tex` |
| 7 | Lattice fundamental groups with acyclic cover | Lattices in Lie Groups | Weinberger | ✅ `solution_q7.tex` |
| 8 | Lagrangian smoothing of polyhedral surfaces | Symplectic Geometry | Abouzaid | ✅ `solution_q8.tex` |
| 9 | Polynomial map detecting rank-1 tensor scaling | Tensor Analysis | Kileel | ✅ `solution_q9.tex` |
| 10 | Preconditioned CG for RKHS-regularized CP decomposition | Numerical Linear Algebra | Kolda | ✅ `solution_q10.tex` |

## What Made This Possible

### 1. A Universal Structural Framework

The key insight is that RS provides a *single* architectural template that applies across all 10 problems. Rather than treating each problem as an isolated puzzle requiring domain-specific tricks, RS identifies the *structural skeleton* shared by all:

- **Every problem has a "structured set"** — the admissible configurations (Cameron-Martin space, Plücker variety, Kronecker cone, calibrated cones, ...)
- **Every problem has a "defect"** — the distance from structure (KL divergence, Plücker residual, missing-data residual, ...)
- **Every problem has a "coercivity"** — a finite cost bound that converts local control to global conclusions

Once you see this skeleton, the domain-specific details become engineering: fill in the projections, compute the constants, verify the bounds.

### 2. RS Predicts Answers Before Computing Them

For each problem, RS predicts the answer from first principles:

- **Q1 (Φ⁴₃ quasi-invariance):** Smooth shifts have finite recognition cost → cannot change null sets → **YES**
- **Q3 (ASEP Markov chain):** Any positive distribution on a finite set admits a ledger-balanced update → Metropolis on adjacent transpositions → **YES**
- **Q8 (Lagrangian smoothing):** 4-valent = C¹ generating function → mollify + exact-graph Hamiltonian → **YES**
- **Q9 (rank-1 detection):** Rank-1 = single recognition channel → determinantal syzygies characterize it → **YES** 
- **Q10 (PCG for RKHS-CP):** Kronecker structure = factored resolution → full-data preconditioner is the J-projection → **explicit algorithm**

The classical proof then fills in the technical details that RS's structural prediction demands.

### 3. The CPM Pattern

The Coercive Projection Method provides a reusable proof engine:

```
Structured Set → Projection Inequality → Energy Control → Dispersion Bound → Aggregation
```

This pattern solves Q1 (with Cameron-Martin as projection, hypercontractivity as energy control), Q9 (with Plücker embedding as structured set, genericity as dispersion), and Q10 (with Kronecker cone as structured set, regularization as coercivity). The same template extends to the remaining 7 problems.

### 4. Bidirectional Validation

The process provides mutual validation:

- **RS → Classical:** RS predicts the answer and identifies the proof architecture; classical tools verify it rigorously
- **Classical → RS:** When independent classical proofs converge to the same structural constants across domains, this validates RS's claim to be the unique zero-parameter attractor

## Repository Contents

```
first-proof/
├── README.md                          # This file
├── first_proof_solutions.tex          # ★ UNIFIED PAPER: all 10 solutions
├── First Proof.pdf                    # The 10 questions (Abouzaid et al., 2026)
├── Recognition_Stability_Audit.tex    # RSA method — impossibility certification
├── CPM.tex                            # Coercive Projection Method — proof template
├── solution_q1.tex                    # Q1: Φ⁴₃ quasi-invariance (Hairer)
├── solution_q2.tex                    # Q2: Rankin-Selberg Whittaker (Nelson)
├── solution_q3.tex                    # Q3: ASEP Markov chain (Williams)
├── solution_q4.tex                    # Q4: Finite-free Stam inequality (Spielman/Srivastava)
├── solution_q5.tex                    # Q5: O-slice filtration (Blumberg)
├── solution_q6.tex                    # Q6: ε-light subsets (Spielman) [partial]
├── solution_q7.tex                    # Q7: Lattice torsion obstruction (Weinberger)
├── solution_q8.tex                    # Q8: Lagrangian smoothing (Abouzaid)
├── solution_q9.tex                    # Q9: Rank-1 tensor detection (Kileel)
└── solution_q10.tex                   # Q10: PCG for RKHS-CP (Kolda)
```

## Building

Each solution is a standalone LaTeX document:

```bash
pdflatex solution_q1.tex
pdflatex solution_q2.tex
pdflatex solution_q3.tex
pdflatex solution_q4.tex
pdflatex solution_q5.tex
pdflatex solution_q6.tex
pdflatex solution_q7.tex
pdflatex solution_q8.tex
pdflatex solution_q9.tex
pdflatex solution_q10.tex
```

## References

- **First Proof:** Abouzaid, Blumberg, Hairer, Kileel, Kolda, Nelson, Spielman, Srivastava, Ward, Weinberger, Williams. [arXiv:2602.05192](https://arxiv.org/abs/2602.05192), February 2026.
- **Recognition Science:** Washburn. [recognitionphysics.org](https://recognitionphysics.org)
- **RSA:** Washburn. *The Recognition Stability Audit: Realizable Cayley Fields and Finite Schur Certificates from Canonical Recognition Cost.* 2026.
- **CPM:** Washburn. *The Coercive Projection Method: Axioms, Theorems, and Applications.* 2026.

## License

Solutions and framework documents © 2026 Jonathan Washburn / Recognition Physics Institute. The *First Proof* questions are © 2026 their respective authors under the [arXiv non-exclusive distribution license](http://arxiv.org/licenses/nonexclusive-distrib/1.0/).

---

*"Nothing cannot recognize itself." — from this, everything follows.*
