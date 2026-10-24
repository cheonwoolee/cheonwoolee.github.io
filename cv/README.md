# CV source

`main.tex` is the original Overleaf source, updated to match the latest uploaded
CV: the current Moloco introduction, six publications, and equal-contribution
marks for the streaming virtual metrology paper. The website's `CV.pdf` is the
exact uploaded PDF.

To update the existing Overleaf project, replace its `main.tex` with this file,
select pdfLaTeX, and recompile. You can also upload `main.tex` to a new Overleaf
project. The project uses the original template's fonts and
packages, including `fontawesome5`, `FiraMono`, `tgheros`, and `ulem`.

With a full TeX Live installation, compile twice from this directory:

```sh
mkdir -p /tmp/cheonwoolee-cv-build
pdflatex -no-shell-escape -interaction=nonstopmode -halt-on-error -output-directory=/tmp/cheonwoolee-cv-build main.tex
pdflatex -no-shell-escape -interaction=nonstopmode -halt-on-error -output-directory=/tmp/cheonwoolee-cv-build main.tex
```

The result is `/tmp/cheonwoolee-cv-build/main.pdf`. After checking it, copy it
to `../CV.pdf` so the personal page's existing CV link serves the new version.

In the prepared cloud environment, the missing font packages were installed
locally at `/workspace/.cv-texmf`. Use `TEXMFHOME=/workspace/.cv-texmf` and
replace the final `main.tex` argument in both commands above with:

```sh
'\pdfmapfile{+fontawesome5.map}\pdfmapfile{+fira.map}\pdfmapfile{+qhv.map}\input{main.tex}'
```
