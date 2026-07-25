#-----------------------------------------------------------------------------
#
#  TSDuck - The MPEG Transport Stream Toolkit
#  Copyright (c) 2005-2026, Thierry Lelegard
#  BSD-2-Clause license, see LICENSE.txt file or https://tsduck.io/license
#
#  Makefile to rebuild draw.io diagrams.
#
#-----------------------------------------------------------------------------

DIAGRAMS  = $(wildcard *.drawio)
PNGS      = $(patsubst %.drawio,%.png,$(DIAGRAMS))
PDFS      = $(patsubst %.drawio,%.pdf,$(DIAGRAMS))
DRAWIO   ?= drawio
PNGFLAGS ?= -t
PDFFLAGS ?=

default: $(PNGS) $(PDFS)
	@true
clean:
	rm -f .\$$*.drawio.bkp
%.png: %.drawio
	$(DRAWIO) -x $(PNGFLAGS) $< -o $@ && optipng -silent $@
%.pdf: %.drawio
	$(DRAWIO) -x $(PDFFLAGS) $< -o $@
