#!gmake
LATEX=xelatex
LATEXMLC=latexmlc

all: pdf html

clean:
	rm -f *~; rm -f */*~; rm -f */*/*~
	cd output; rm -f *.aux *.log *.toc *.out;

distclean: clean
	rm -rf output;

pdf: source/math-suite-diagram.png
	mkdir -p output;
	cd source && \
	$(LATEX) -output-directory ../output/ MathUI2014-MozillaMathML.tex;

html: source/math-suite-diagram.png
	cd source; \
	$(LATEXMLC) --dest ../output/index.html --format=html5 --splitat=subsection MathUI2014-MozillaMathML.tex;

source/math-suite-diagram.png: source/math-suite-diagram.tex
	mkdir -p output;
	cd source && \
	$(LATEX) -output-directory ../output/ $(subst source,.,$<);
	convert -density 300 $(subst png,pdf, $(subst source,output,$@)) $@

.PHONY: clean distclean pdf html all

