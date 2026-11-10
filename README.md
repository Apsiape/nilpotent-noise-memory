# A nilpotent cellular automaton that remembers under noise

Seth Douglas and Nidhal Mghirbi. Version 1.0.0, November 2026. The version DOI is recorded in the commit that follows the release.

**This is a preprint. It has not been peer reviewed.**

## Abstract

Does every positive zero-range perturbation of a nilpotent cellular automaton have a unique attracting stationary law? We construct a counterexample on ℤ³, answering a question of Marcovici, Sablik and Taati. Each site carries a bit and a bounded countdown. The deterministic rule reaches the all-zero configuration after a fixed number of steps, while independent uniform replacements renew the countdowns and allow a horizontal bit plane to retain its initial value. With stationary countdowns, the plane is exactly a north-east-centre majority process with independent gates and independent replacement faults. We calculate the gate law and apply Toom's stability theorem in the quantitative version of Gács to obtain two translation-invariant stationary laws. For the same fixed automaton, a dependency-path estimate proves uniform exponential ergodicity at sufficiently small and sufficiently large noise rates. We also construct, for every prescribed separation, a nilpotent automaton, a set of replacement events at pairwise distance exceeding that separation, and two initial configurations whose bits differ on a whole plane at all times under those common events.

## What the paper proves

A cellular automaton is nilpotent if it erases every starting configuration in a bounded number of steps. Marcovici, Sablik and Taati (Electron. J. Probab. 24 (2019), Problem 6.5) asked whether adding independent positive noise to such an automaton always leaves a process that forgets its start. The paper answers no, on ℤ³:

- **The rule.** Each site holds a bit and a countdown in {0, ..., H}. The countdown falls along one axis; the bit follows north-east-centre majority while the countdown above it is open, and resets to 0 otherwise. Without noise, everything is zero after H + 1 steps.
- **Memory under noise.** Under independent uniform replacement at rate ε, one horizontal bit plane is exactly a noisy north-east-centre majority process with independent gates. With Toom's stability theorem (in Gács's quantitative exposition), the noisy rule has two different translation-invariant stationary laws, for example at ε = 2^-44 with H = 2^88.
- **Re-entrance.** The same fixed rule is uniformly exponentially ergodic at all sufficiently small and all sufficiently large noise rates.
- **Separated events.** For every separation, a nilpotent rule keeps a whole bit plane different forever under common replacement events that are pairwise farther apart than that separation.

The example is three-dimensional; dimensions one and two are not addressed. The two-transition phenomenon itself was established in one dimension by Marsan, Sablik and Törmä for a rule that is not nilpotent.

## Contents and reproduction

- `paper/main.pdf`: the manuscript.
- `paper/`: LaTeX source (`main.tex`), plain-text abstract and a strict build driver. Run `python -B build.py` there with pdflatex installed. The build disables shell escape, runs pdflatex three times and rejects warnings, unresolved references and box defects.
- `SHA256SUMS`: SHA-256 hashes of every shipped file except this manifest. Check with `sha256sum -c SHA256SUMS` from the repository root.

No computation is used in any proof.

## Citation and rights

See `CITATION.cff` for citation metadata. Paper and documentation: CC BY 4.0. Build script: MIT or Apache 2.0, at your option. See `RIGHTS.md`, the license files and `NOTICE`.
