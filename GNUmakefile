THISDIR := phy485-optics
THISBOOK := phy485

BIBLIOGRAPHY_PATH := classicthesis_mine
HAVE_OWN_CONTENTS := 1
HAVE_CUSTOM_DEDICATION := 1
MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/Index.tex
MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/ContentsAndFigures.tex
BOOKTEMPLATE := ../latex/classicthesis_mine/ClassicThesis2.tex

include make.revision
include ../latex/make.bookvars

# comment this out for online pdf version (uncomment for KDP)
#PRINT_VERSION := 1
#ifdef KINDLE_VERSION
#PARAMS += --kindle
#endif

ifdef PRINT_VERSION
SUBFIGDIR := bw
else
SUBFIGDIR := color
endif

ifndef PRINT_VERSION
PARAMS += --no-print
endif
PARAMS += -subfig $(SUBFIGDIR)
DISTEXTRA := $(SUBFIGDIR)
ifdef PRINT_VERSION
DISTEXTRA := $(DISTEXTRA).kdp
endif

FIGURES += ../figures/$(THISBOOK)/$(SUBFIGDIR)
FIGURES += ../figures/$(THISBOOK)
SOURCE_DIRS += $(FIGURES)

#ONCEFLAGS := -justonce

SOURCE_DIRS += appendix

EPS_FILES := $(foreach dir,$(FIGURES),$(wildcard $(dir)/*.eps))
PDFS_FROM_EPS := $(subst eps,pdf,$(EPS_FILES))
#$(error PDFS_FROM_EPS $(PDFS_FROM_EPS))

THISBOOK_DEPS += $(PDFS_FROM_EPS)

GENERATED_SOURCES += mathematica.tex
GENERATED_SOURCES += backmatter.tex

DO_SPELL_CHECK := $(shell cat spellcheckem.txt)

include ../latex/make.rules

.PHONY: spellcheck
spellcheck: $(patsubst %.tex,%.sp,$(filter-out $(DONT_SPELL_CHECK),$(DO_SPELL_CHECK)))

%.sp : %.tex
	spellcheck $^
	touch $@
 
scrpage2.sty : ../latex/scrpage2.sty
	cp $^ $@

backmatter.tex: ../latex/classicthesis_mine/backmatter2.tex
	rm -f $@
	ln -s ../latex/classicthesis_mine/backmatter2.tex backmatter.tex
