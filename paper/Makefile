#!gmake
LATEX=xelatex
LATEXMLC=latexmlc

all: pdf html

clean:
	rm -f *~; rm -f */*~; rm -f */*/*~
	cd output; rm -f *.aux *.log *.toc *.out;

distclean: clean
	rm -rf output;

pdf:
	mkdir -p output;
	cd source; \
	$(LATEX) -output-directory ../output/ MathUI2014-MozillaMathML.tex;

html:
	cd source; \
	$(LATEXMLC) --dest ../output/index.html --format=html5 --splitat=section MathUI2014-MozillaMathML.tex

.PHONY: clean distclean pdf html all
