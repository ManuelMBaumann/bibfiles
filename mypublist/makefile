TEX=$(wildcard *.tex)
PDF=$(patsubst %.tex,%.pdf,$(TEX))
PDFSUF=print

all: $(PDF) $(PDFPRINT)
pdf: all

$(PDF): %.pdf: %.tex
	# twice is enough here? ;)
	pdflatex $<
	bibtex msc.aux
	bibtex rev.aux
	bibtex ppt.aux
	bibtex prc.aux
	pdflatex $<
	pdflatex $<


.PHONY: clean
clean: 
	rm $(PDF) $(PDFPRINT) 
	rm $(patsubst %.pdf,%.aux,$(PDF))
	rm $(patsubst %.pdf,%.log,$(PDF))
	rm $(patsubst %.pdf,%.out,$(PDF))
	rm $(patsubst %.pdf,%.toc,$(PDF))
	rm $(patsubst %.pdf,%.snm,$(PDF))
	rm $(patsubst %.pdf,%.nav,$(PDF))
