# HSLN archive — the June 2026 files, unchanged

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23690426.svg)](https://doi.org/10.5281/zenodo.23690426)

This repository is a frozen record. It holds the files produced between 29 May and
4 June 2026 during an attempt to design an efficient *heterotic spiking liquid network*
(HSLN): a reservoir computer whose state lives on a modular curve, whose parameters are the
Fourier coefficients of a modular form, and whose trained models compose by multiplying
forms. The attempt ran into classical number theory almost immediately (the E8 lattice,
Eisenstein series, Dirichlet series, the Euler product) and most of the files are about that.

A reservoir computer is a fixed dynamical system whose state is read out by a trained
linear map. Here the system's parameters are the Fourier coefficients of a modular form,
called its "DNA" in the files, and "heterotic" refers to the E8×E8 lattice from which the
seed form is taken.

Nothing in `files/` has been edited. Every file is covered either by an OpenTimestamps
proof anchored in the Bitcoin blockchain, by a git history whose later state is so
covered, or both. The companion repositories (the audit and the Lean formalisation,
linked at the end) are where the mathematics is graded and, where it holds,
machine-checked. This repository only establishes *what existed, when*.

## Provenance at a glance

| Date (UTC) | Event | Evidence |
|---|---|---|
| 2026-05-29 08:29 | first git commit: spec, Lean files, visualisation scripts | `git/hsln-2026-05.bundle`, commit `eaf2bc9` |
| 2026-05-29 to 05-31 | 28 further commits (29 in all): zeta from Euler factors, factorising by composition, spectral/Hilbert–Pólya threads, Weil positivity, bosons/fermions, Shor as period-finding, torsion of E8×E8 | `git/COMMITS.txt` |
| 2026-06-02 16:46 | earliest timestamp: a first version of the Lean patch (file not retained) | block 952131 |
| 2026-06-02 18:27 | the Lean patch `langlands_program.patch` timestamped (proof file `langlands_millennium.patch(1).ots`; the patch was renamed before the 4 June stamps) | block 952138 |
| 2026-06-03 | `python.zip` assembled (entry modification times) | zip metadata only |
| 2026-06-04 08:21 | all 28 Lean files, `math-connections.md`, `system-spec.md`, both visualisation zips timestamped | block 952310 |
| 2026-06-04 22:10 | second confirmation of the same 34 digests | block 952402 |

The two evidence chains agree. The timestamped files are the repository's working tree on
2–4 June: the final commit of 31 May plus uncommitted edits in 21 files, 30 lines in all,
recorded verbatim in `git/worktree-vs-HEAD.diff`. Before the files were shared, the
author's first name was replaced by `[REDACTED NAME]` in 19 of them, and a home-directory
path was shortened in `SECURITY_IMPACT.md`; the git bundle predates that redaction and
carries the author's commit identity. The only other edits are in two scripts:
`explicit.py` (500 zeta zeros raised to 5 000, longer K list) and `factor_battery.py`
(the five classical factoring baselines commented out). Everything else is byte-identical.
Git commit dates are self-reported; the Bitcoin attestations are not.

Full per-file table: [`TIMESTAMPS.md`](TIMESTAMPS.md), which records the earliest block
per file (every 4 June proof also carries block 952402). Digests: [`SHA256SUMS`](SHA256SUMS).

## What the work is

The idea, in the spec's own order:

1. A holomorphic function `F` on the upper half-plane defines an energy `|F|²` whose only
   minima are the zeros of `F`. Gradient flow on this energy is a reservoir whose
   attractors are the zeros: the "neurons".
2. If `F` is a modular form, the zeros are a modular-invariant object, and a trained model
   is a finite list of Fourier coefficients (Sturm's bound): the DNA.
3. Multiplying two forms unions their zero sets, so two separately trained models can be
   combined without retraining. The scripts verify the zero-union identity to machine
   precision. Whether the combined model still performs both tasks is a separate empirical
   question the log pursues: the basins interact, and the direct sum of genus-2 forms was
   introduced to address that. Ordinary reservoirs have no comparable composition law.
4. The seed form is the theta series of the E8 lattice, which is the Eisenstein series
   `E₄`, so its coefficients are `240 σ₃(n)`. Two copies give E8×E8, the heterotic lattice.
5. The same coefficient list can be multiplied in two different ways: as a power series in
   `q` (the form) or as a Dirichlet series (the L-function). These are two different rings
   on one carrier. Hecke eigenforms are the forms whose coefficients are multiplicative, so
   that their Dirichlet series factor as Euler products; the Euler product for `ζ` is the
   statement that `ζ` is assembled one prime at a time under the Dirichlet product.

From there the log explores where that leads: eta quotients as a linear composition
calculus, the j-invariant as a readout, Siegel forms of degree 2 as coupled pairs of
models, the Lie derivative `q d/dq` as the grading operator, Dirichlet L-functions as a
family of generators, and the spectral (Hilbert–Pólya) picture of the zeta zeros.

## How to read it, and how not to

**Start with `system-spec.md`.** Its §4, "Critical analysis", separates what is
watertight (seven items), what needs more argument (five), and what is speculative or
wrong as stated (four). That section was written at the time; the companion audit
broadly upholds its grading.

**Read `math-connections.md` as a log, not a paper.** It was written over three days and
grows less careful towards the end. Its earlier sections (the two-ring structure, the
L-function family and its class-number values, the two-square count from `ζ · L(s, χ₋₄)`)
are correct and are reproduced in the audit. Its later claims that conjectures are "proved
in Lean modulo cited sorries" are wrong: a `sorry` is a hole in a proof, not a citation.
The audit counts 234 theorem statements in the 24 `HSLN*.lean` files (the four
`Spectral*.lean` files are not yet counted); 143 are both `sorry`-free and in files that
compile against the Mathlib the audit used. Four files fail there from API drift between
Lean releases, not from errors in the mathematics. The remaining statements carry `sorry`:
statements of open conjectures (RH, BSD, Hodge, Yang–Mills), cited theorems used as black
boxes (Kolyvagin, Gross–Zagier, Wiles), and consequences conditional on them. They are
scaffolding, not results.

**Several files are named after Millennium problems.** None proves anything about them.
They state the conjectures in Lean and prove classical or conditional consequences.
`HSLNHilbertPolya.lean` proves "RH ⇔ a Hilbert–Pólya operator exists" by building the
operator from the zeros themselves, which `SECURITY_IMPACT.md` already notes makes the
equivalence a restatement rather than progress. `HSLNBSD.lean` chains Kolyvagin and
Gross–Zagier as `sorry`'d black boxes. The commit described as "P vs NP wired" formalises
a composition/verification asymmetry, not a separation. `HSLNYangMills.lean` proves that a
spectral gap scales with the coupling, nothing about existence. The audit lists each file.

**The complexity and cryptography files are negative results.** `HSLNFactor.lean`,
`HSLNComplexity.lean`, `SpectralShor.lean` and the scripts `factorize.py`,
`factor_prime_pair.py`, `factor_battery.py`, `hsln_reverse_factor.py`,
`hsln_hash_dance.py`, `hsln_hash_dance_v2.py`, `hsln_hash_inverse.py`,
`hsln_pgp_dance.py` and the `hsln_bitcoin_*` probes ask whether the composition algebra
gives any purchase on factoring or on hash inversion. The answer recorded in them, and
confirmed by the audit, is no: every factoring route tried is trial division or
period-finding in new vocabulary, the hash landscape is structureless, and the one Lean
theorem in this area is the classical reduction "a period gives a factor", which is
Shor's, not new. `SECURITY_IMPACT.md`, written at the time, reaches the same conclusion.
Nothing in this archive has cryptographic consequences.

**What stands.** Four things survive the audit intact: the architecture of items 1–3
above; the zero-union merge law, implemented and measured; the classical but correctly
placed observation that one coefficient list carries two ring structures, Cauchy and
Dirichlet, and that under the second the Euler product is the composition rule; and the
self-contained number-theory script sequence (figures 31–36: zeta from Euler factors, the
sieve, factoring as its inverse, the explicit formula). The rest is exploration, and is
labelled as such in the companion audit.

## Contents

```
files/        the original artefacts, byte-for-byte
ots/          36 OpenTimestamps proofs, upgraded to complete Bitcoin attestations
git/          the May 2026 git history as a bundle, its commit and file lists, and the diff
              from its last commit to the timestamped working tree
SHA256SUMS    digests of everything in files/
TIMESTAMPS.md which proof covers which file, with block height and block time
```

| File | What it is | Timestamped |
|---|---|---|
| `files/lean.zip` | 28 Lean 4 files (`HSLN*.lean`, `Spectral*.lean`), lakefile, manifest, toolchain, two shell scripts | every `.lean` individually, block 952310 |
| `files/docs.zip` | `system-spec.md` (the architecture, with its own critical analysis), `math-connections.md` (the research log), `SECURITY_IMPACT.md` | the two design documents, block 952310 |
| `files/python.zip` | 79 Python scripts, `pyproject.toml`, `uv.lock`, cached zeta zeros | no proof of its own; its 79 scripts match the `viz/` tree of the bundle up to the redaction and the two edits noted above, and every figure they produce is in the timestamped visualisation zips |
| `files/visualizations_part1.zip`, `..._part2.zip` | 68 figures and 7 animations produced by the scripts | both zips, block 952310 |
| `files/langlands_program.patch` | the Lean files as a single git patch against a Mathlib tree (43 files) | block 952138 |
| `files/patch.txt` | an earlier, smaller patch (13 files) | no proof |
| `git/hsln-2026-05.bundle` | the working repository, 29 commits, 196 tracked files | its working tree on 2–4 June (last commit + `worktree-vs-HEAD.diff`) is the timestamped set |

A cover letter that accompanied the files when they were first shared is not reproduced
here; it contained no mathematics.

## How to verify

```bash
sha256sum -c SHA256SUMS                       # the files are the ones listed
pip install opentimestamps-client
ots info ots/HSLNHecke.lean.ots               # prints the digest and the Bitcoin block
unzip -p files/lean.zip lean/HSLNHecke.lean | sha256sum   # must equal that digest
ots verify ots/HSLNHecke.lean.ots -f <file>   # full check against a Bitcoin node
git clone git/hsln-2026-05.bundle hsln-may    # the history, with dates and messages
```

Block times were read from a public block explorer and are recorded in `TIMESTAMPS.md`;
anyone can re-read them from any Bitcoin node.

An independent snapshot of release `v2026.06-archive` is archived at Zenodo,
DOI [10.5281/zenodo.23690426](https://doi.org/10.5281/zenodo.23690426) (deposited 27 October 2026).

## Companion repositories

- **The audit**: [rmorleysmith/fugue](https://github.com/rmorleysmith/fugue), directory
  `Fugue/`: every claim in these files graded by evidence, with reproductions.
- **The formalisation**: [rmorleysmith/fugue-formal](https://github.com/rmorleysmith/fugue-formal):
  the parts of the corpus that survive, re-proved from scratch in Lean 4 against Mathlib:
  99 audited theorems, only Lean's three standard axioms, no `sorry`. With
  [fugue-formal-pnt](https://github.com/rmorleysmith/fugue-formal-pnt) (Ingham's theorem)
  and [palomar-ingham](https://github.com/rmorleysmith/palomar-ingham) (registry entries).
- **The exposition**: in preparation.

## Licence

Code (Lean, Python, shell): Apache-2.0 (`LICENSE-CODE`). Text and figures: CC-BY-4.0
(`LICENSE-TEXT`). The timestamp proofs and digests are not copyrightable and carry no
licence.
