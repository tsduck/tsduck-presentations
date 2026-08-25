#-----------------------------------------------------------------------------
#
#  TSDuck - The MPEG Transport Stream Toolkit
#  Copyright (c) 2005-2026, Thierry Lelegard
#  BSD-2-Clause license, see LICENSE.txt file or https://tsduck.io/license
#
#  Makefile to rebuild draw.io diagrams.
#
#-----------------------------------------------------------------------------

TSIMGDIR  = ../../tsduck/images
DIAGRAMS  = $(wildcard *.drawio)
PNGS      = $(patsubst %.drawio,%.png,$(DIAGRAMS))
PDFS      = $(patsubst %.drawio,%.pdf,$(DIAGRAMS))
DRAWIO   ?= drawio
OPTIPNG  ?= optipng
PNGFLAGS ?= -t
PDFFLAGS ?=
OPTFLAGS ?= -silent

default: $(PNGS) $(PDFS) $(if $(wildcard $(TSIMGDIR)),$(addprefix $(TSIMGDIR)/,$(PNGS)))
	@true
clean:
	rm -f .\$$*.drawio.bkp
%.png: %.drawio
	$(DRAWIO) -x $(PNGFLAGS) $< -o $@ && $(OPTIPNG) $(OPTFLAGS) $@
%.pdf: %.drawio
	$(DRAWIO) -x $(PDFFLAGS) $< -o $@
$(TSIMGDIR)/%: %
	cp -f $< $@
