# Natural Language Toolkit: Technical report Makefile
#
# Copyright (C) 2001-2012 NLTK Project
# Author: Edward Loper <edloper@gradient.cis.upenn.edu>
# URL: <http://www.nltk.org/>
# For license information, see LICENSE.TXT
#
# $Id: Makefile,v 1.2 2004/04/27 04:26:37 stevenbird Exp $

##############################################
##  The name of the report
REPORT = acl04

##############################################
##  Figure dependancies

##############################################
##  You shouldn't have to change anything below here.

# Find the name of the dvi and ps files.
DVI := $(REPORT).dvi
PS := $(REPORT).ps
PDF := $(REPORT).pdf

# Top-level rules.
dvi: $(DVI)
ps: $(PS)
pdf: $(PDF)
clean:
	rm -f *.eps *.log *.aux *.dvi *.ps *.toc *.pdf

# General rules
%.dvi: %.tex
	latex $<
	latex $<

%.ps: %.dvi
	dvips -t letter -o $@ $<

%.eps: %.dot
	dot -Tps -o $@ $<

%.eps: %.obj
	tgif -print -eps $<

%.pdf: %.ps
	ps2pdf $< $@
