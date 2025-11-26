# ASTR 104 – Problem Set 4, Part 2: Hydrogen EOS

This repository contains a self-contained Python implementation of the hydrogen
equation of state as required in **Part 2** of ASTR 104 Problem Set 4.

It models a pure hydrogen gas with:
- Molecular hydrogen: H₂
- Neutral atomic hydrogen: H I
- Ionized hydrogen: H II + e⁻

and computes:

1. Molecular equilibrium: H₂ ⇌ 2 H I  
2. Ionization equilibrium: H I ⇌ H II + e⁻  
3. Species number densities as functions of T and P  
4. Specific Helmholtz free energy and entropy for each species  
5. Total mixture entropy `s_mix(T, P)`  
6. Logarithmic derivatives of `log s_mix` w.r.t. `log T` and `log P`  
7. The adiabatic temperature gradient `∇_ad(T, P)`  
8. Colour maps for:
   - Composition (H₂ / H I / H II)
   - Mixture entropy `s_mix`
   - Adiabatic gradient `∇_ad`

The implementation is idealized but follows the physics and equations in the
problem set:

- H₂ internal partition function:
  - Electronic: ground + first excited state split by the bond energy
  - Vibrational: quantum harmonic oscillator
  - Rotational: rigid rotor with ortho/para splitting

- H I partition function: truncated sum over bound levels up to n = 10

- Equilibrium chemistry via Saha–like relations

The grid is computed in `(log10 T, log10 P)` space:

- 2 ≤ log10 T ≤ 5 (T in K)
- 0 ≤ log10 P ≤ 13 (P in dyne cm⁻²)

## Installation

Create a virtual environment (optional but recommended), then install dependencies:

```bash
pip install -r requirements.txt
