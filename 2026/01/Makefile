SOURCE_DOCS := $(wildcard *.md)

EXPORTED_DOCS=\
 $(SOURCE_DOCS:.md=.pdf) \

PANDOC=/usr/bin/pandoc

TEMPLATE=/home/bobfett/Documents/Cours/style/pandoc/templates/cours

TEMPLATEPOLY=/home/bobfett/Documents/Cours/style/pandoc/templates/poly


PANDOC_OPTIONS=-s \
               --lua-filter=include-files.lua \
               --lua-filter=/home/bobfett/Documents/Cours/scripts/pandoc/filters/exercices.lua \
               --lua-filter=diagram-generator.lua \
	       --lua-filter=/home/bobfett/Documents/Cours/hk-pandoc-filters/column-div/column-div.lua \
               --listings \
               -f markdown
               
PANDOC_PDF_OPTIONS=--pdf-engine=xelatex

# Pattern-matching Rules

%.pdf : %.md
	$(PANDOC) $(PANDOC_OPTIONS) $(PANDOC_PDF_OPTIONS) --template $(TEMPLATE) -o $@ $<

%-poly-%.pdf) : %-poly-%.md)
	$(PANDOC) $(PANDOC_OPTIONS)  --template $(TEMPLATEPOLY) $(PANDOC_PDF_OPTIONS) -o $@ $<

00-poly-%.pdf : 00-poly-%.md *.md
	$(PANDOC) $(PANDOC_OPTIONS)  --template $(TEMPLATEPOLY) --top-level-division="chapter" $(PANDOC_PDF_OPTIONS) -o $@ $<

# Targets and dependencies

.PHONY: all clean

all : $(EXPORTED_DOCS)

pdf : $(SOURCE_DOCS:.md=.pdf)

clean:
	- $(RM) $(EXPORTED_DOCS)

