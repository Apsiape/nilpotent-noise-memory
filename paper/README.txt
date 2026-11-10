A nilpotent cellular automaton that remembers under noise
Seth Douglas and Nidhal Mghirbi
Version 1.1.0, November 2026

Build: python -B build.py [--build-dir NEW_OR_EMPTY_DIRECTORY]
Requires Python 3 and pdflatex. The bibliography is inline. The build runs pdflatex three times without shell escape and rejects
warnings, unresolved references and overfull or underfull boxes. main.pdf is the compiled preprint (17 pages). abstract.txt is the abstract as plain text.
No computation is used in any proof written in this paper. Section 6 imports the three-token theorem of
"Forgetting under noise is undecidable" (DOI 10.5281/zenodo.24115709), whose proof there includes one
finite lemma checked by computer (its Lemma 9.12). No publication or submission is performed by the build.
