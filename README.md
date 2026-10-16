# An elliptic curve of rank ≥ 34 and root number −1 over a quadratic field

**Dylan T. Costa and Álvaro Lozano-Robledo**

The paper is available at [https://hexagonmath.org/2610.00280v1](https://hexagonmath.org/2610.00280v1).

This repository contains the paper
[`costa--lozano-robledo_rank35.pdf`](costa--lozano-robledo_rank35.pdf) (LaTeX source
[`costa--lozano-robledo_rank35.tex`](costa--lozano-robledo_rank35.tex), bibliography
[`twist-4239.bib`](twist-4239.bib)) and the Magma code that verifies its results.

## Summary

Let E/Q be the elliptic curve of rank ≥ 32 found by Elkies, Klagsbrun and Li
([ICARM Elliptic Curve Rank Leaderboard, curve #4239](https://elliptic-rank.icarm.cloud/curve/4239)).
Using a family of quadratic twists of rank ≥ 2 over Q(t) constructed by Mestre, we search for twists
E^D with root number −1, computing all root numbers without factoring the (very large) twisting
parameter D. The parameter t = 3 gives an explicit integer D with 411 digits (a square times an
integer with 381 digits) such that

- E^D has root number −1 and two independent rational points, so rank E^D(Q) ≥ 2 (and ≥ 3 under the
  Parity Conjecture);
- rank E(Q(√D)) ≥ 34 unconditionally, and ≥ 35 assuming the Parity Conjecture.

## Verifying the results

[`g3-twist-data.m`](g3-twist-data.m) defines all the data for t = 3 (the curve E, its short
Weierstrass model, the 32 known points, D, the twist E^D with the points P and Q, the field
K = Q(√D), and the points P33, P34 on E(K)). It re-checks every claim in the paper with `assert`.
To run it:

```
magma -b verify.m
```

On success it prints `g3-twist-data.m: all assertions passed.` It takes about 35 seconds with
Magma V2.29-10. To use the data interactively, run `load "g3-twist-data.m";` inside a Magma session.

## Acknowledgments

We thank Noam Elkies, Zev Klagsbrun and Samuel Li for making their curve publicly available, and
ICARM (supported by NSF Grant DMS 2425401). The Magma code was written with the help of Claude
Opus 5.5; see the declaration of AI use in the paper.
