FILENAME = report

# LATEX = pdflatex
# LATEX = xelatex
LATEX = lualatex

BIBTEX = bibtex
# BIBTEX = biber

default: document

all: default

text:
	latexmk -$(LATEX) -logfilewarnings -halt-on-error $(FILENAME)

document: clear_screen text

clear_screen:
	clear

clean:
	rm -f *.aux *.bbl *.blg *.dvi *.idx *.lof *.log *.lot *.toc \
		*.glg *.gls *.glo *.xdy *.nav *.out *.snm *.vrb *.mp \
		*.synctex.gz *.brf *.fls *.fdb_latexmk

realclean: clean
	rm -f *.ps *.pdf

final:
	if [ -f *.aux ]; then \
		$(MAKE) clean; \
	fi
	$(MAKE) text
	$(MAKE) clean
