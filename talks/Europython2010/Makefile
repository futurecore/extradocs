### Variables you MUST edit:

DOC=pythoncsp# LaTeX document name without .tex extention.
BIBDOC=pythoncsp# How embarrassing :-(((

### Variables you might want to edit:

PDF_VIEWER=acroread # Usually varies between platforms, etc.
EDITOR=emacs   # Only used in 'make edit'.

### Best not to edit after this line unless you grok the whole file :) 

LATEX=latex
LATEX_FLAGS=

BIB=bibtex
BIB_FLAGS= 

GEN_PS_FLAGS=-P cmz -t letter # Optimised for ACM papers.
# GEN_PS_FLAGS=-P cmz -t a4 # A4 version
GEN_PDF_FLAGS=
GEN_PS=dvips $(GEN_PS_FLAGS) -f $(DOC).dvi -o $(DOC).ps
GEN_PDF=dvipdfm $(DOC).dvi

HOSTNAME=$(shell hostname)
VIEW_FILE=$(DOC).pdf

VIEW_2_TEXT=ps2ascii

WORD_COUNT=wc -w

GENERATED=$(DOC).log $(DOC).toc $(DOC).dvi $(DOC).ps $(DOC).pdf $(DOC).txt $(DOC).lol $(DOC).los $(DOC).lof  $(DOC).blg $(DOC).bbl $(DOC).aux $(DOC).idx $(DOC).ind $(DOC).ilg
### Generate everything except a .ps file.
all:    pdflatex view
#dvi pdf view
# all:  fig dvi pdf view
pdflatex:
	pdflatex $(DOC).tex
	pdflatex $(DOC).tex
	pdflatex $(DOC).tex
### Remove generated files (except a couple needed by BibTeX).
clean:
	rm -f $(GENERATED)
	find . -name "*~" -exec rm '{}' ';'
#       rm -f chapters/*.aux	 ### From the Python notes.
#       rm -f figures/*/*.eps	### From the Python notes.
#       rm -f listings/images/*.eps  ### From the Python notes.
### Run latex to get a DVI file.
dvi:
	$(LATEX) $(LATEX_FLAGS) $(DOC).tex
	$(LATEX) $(LATEX_FLAGS) $(DOC).tex
#	$(BIB) $(BIB_FLAGS) $(BIBDOC)
	$(LATEX) $(LATEX_FLAGS) $(DOC).tex
	$(LATEX) $(LATEX_FLAGS) $(DOC).tex
### Generate a PS file from a DVI file.
ps: 
	$(GEN_PS)
### Generate a PDF file from a DVI file (gives better results than ps2pdf).
pdf: 
	$(GEN_PDF)
### Process a bibliography.
bib:
	$(BIB) $(BIBDOC)
### View a PDF file.
view:
	$(PDF_VIEWER) $(VIEW_FILE)
### Edit the TeX file.
edit:
	$(EDITOR) $(DOC).tex &
### Count the words in a PS file (might be broken / inaccurate).
words: ps
	$(VIEW_2_TEXT) $(DOC).ps > $(DOC).txt ; $(WORD_COUNT) $(DOC).txt

### SCRATCH SPACE! 

### The commented lines below were used for the Python notes.
### They automatically converted .png / .jpg file to .eps.
### Requires mogrify and chained makefiles. 

# ### Make all without mogrify
# nofig:        dvi pdf view
# ### Convert raster and vector graphics into .eps
# fig:
#       $(MAKE) -C figures
#       $(MAKE) -C listings