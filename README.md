# A nilpotent cellular automaton that remembers under noise

Seth Douglas and Nidhal Mghirbi. Version 1.1.0, November 2026. DOI: [10.5281/zenodo.24117111](https://doi.org/10.5281/zenodo.24117111). Version 1.0.0: [10.5281/zenodo.24101507](https://doi.org/10.5281/zenodo.24101507). Concept DOI (all versions): [10.5281/zenodo.24101506](https://doi.org/10.5281/zenodo.24101506).

**This is a preprint. It has not been peer reviewed.**

## Abstract

Does every positive zero-range perturbation of a nilpotent cellular automaton have a unique attracting stationary law? We construct a counterexample on ℤ³, answering a question of Marcovici, Sablik and Taati. Each site carries a bit and a bounded countdown. The deterministic rule reaches the all-zero configuration after a fixed number of steps, while independent uniform replacements renew the countdowns and allow a horizontal bit plane to retain its initial value. With stationary countdowns, the plane is exactly a north-east-centre majority process with independent gates and independent replacement faults. We calculate the gate law and apply Toom's stability theorem in the quantitative version of Gács to obtain two translation-invariant stationary laws. For the same fixed automaton, a dependency-path estimate proves uniform exponential ergodicity at sufficiently small and sufficiently large noise rates. We also construct, for every prescribed separation, a nilpotent automaton, a set of replacement events at pairwise distance exceeding that separation, and two initial configurations whose bits differ on a whole plane at all times under those common events.

The countdown also lifts other rules. Applied to the computable family of positive-rate automata on ℤ⁸ whose ergodicity at a fixed noise rate is undecidable (Douglas and Mghirbi, Forgetting under noise is undecidable), it gives a computable family of radius-one cellular automata on ℤ⁹, all nilpotent within the same number of steps, with alphabets that grow with the machine. At every rate in [ε₀/2, ε₀], where ε₀ = 490000^(−99), uniform replacement noise makes the member built from a Turing machine M ergodic if and only if M halts. For every n, we also construct one nilpotent automaton on ℤ³ with n disjoint intervals of noise rates that carry two translation-invariant stationary laws, alternating with intervals of uniform exponential ergodicity. Whether a single nilpotent rule can have infinitely many such windows is open.

## What the paper proves

A cellular automaton is nilpotent if it erases every starting configuration in a bounded number of steps. Marcovici, Sablik and Taati (Electron. J. Probab. 24 (2019), Problem 6.5) asked whether adding independent positive noise to such an automaton always leaves a process that forgets its start. The paper answers no, on ℤ³:

- **The rule.** Each site holds a bit and a countdown in {0, ..., H}. The countdown falls along one axis; the bit follows north-east-centre majority while the countdown above it is open, and resets to 0 otherwise. Without noise, everything is zero after H + 1 steps.
- **Memory under noise.** Under independent uniform replacement at rate ε, one horizontal bit plane is exactly a noisy north-east-centre majority process with independent gates. With Toom's stability theorem (in Gács's quantitative exposition), the noisy rule has two different translation-invariant stationary laws, for example at ε = 2^-44 with H = 2^88.
- **Re-entrance.** The same fixed rule is uniformly exponentially ergodic at all sufficiently small and all sufficiently large noise rates.
- **Separated events.** For every separation, a nilpotent rule keeps a whole bit plane different forever under common replacement events that are pairwise farther apart than that separation.

Version 1.1.0 adds two theorems:

- **Undecidability within nilpotent rules (Section 6).** The countdown lift turns the computable ℤ⁸ family of the authors' paper *Forgetting under noise is undecidable* (version 1.3.0, DOI [10.5281/zenodo.24115709](https://doi.org/10.5281/zenodo.24115709)) into a computable family of radius-one cellular automata on ℤ⁹ that are all nilpotent within the same number of steps. At every rate ε in [ε₀/2, ε₀], with ε₀ = 490000^(−99), uniform replacement makes the member built from a Turing machine M ergodic if and only if M halts. The alphabet grows with M; the rates, radius, dimension and nilpotency time do not.
- **Many windows (Section 7).** For every n, one nilpotent rule on ℤ³ has two translation-invariant stationary laws on n disjoint open intervals of noise rates, separated by n − 1 open intervals of uniform exponential ergodicity, and is ergodic at all sufficiently small and all sufficiently large rates. Its ergodicity therefore changes at least 2n times as the rate varies; the status between the stated intervals is not determined. Whether one rule can have infinitely many windows is open.

The single-rule examples are three-dimensional and the undecidable family is nine-dimensional; dimensions one and two are not addressed. The two-transition phenomenon itself was established in one dimension by Marsan, Sablik and Törmä for a rule that is not nilpotent.

## Contents and reproduction

- `paper/main.pdf`: the manuscript.
- `paper/`: LaTeX source (`main.tex`), plain-text abstract and a strict build driver. Run `python -B build.py` there with pdflatex installed. The build disables shell escape, runs pdflatex three times and rejects warnings, unresolved references and box defects.
- `SHA256SUMS`: SHA-256 hashes of every shipped file except this manifest. Check with `sha256sum -c SHA256SUMS` from the repository root.

No computation is used in any proof written in this paper. Section 6 imports the three-token theorem of *Forgetting under noise is undecidable*, whose proof there includes one finite lemma checked by computer (its Lemma 9.12).

## Citation and rights

See `CITATION.cff` for citation metadata. Paper and documentation: CC BY 4.0. Build script: MIT or Apache 2.0, at your option. See `RIGHTS.md`, the license files and `NOTICE`.
