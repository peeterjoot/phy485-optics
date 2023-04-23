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

# uncomment-in for kdp version (no mathematica notebooks in appendix.)
#PRINT_VERSION := 1

ifdef PRINT_VERSION
DISTEXTRA := kdp
else
PARAMS += --no-print
endif

FIGURES := ../figures/phy485-optics

#ONCEFLAGS := -justonce

SOURCE_DIRS += appendix
SOURCE_DIRS += $(FIGURES)

#EPS_FILES := $(wildcard $(FIGURES)/*.eps)
#PDFS_FROM_EPS := $(subst eps,pdf,$(EPS_FILES))
#THISBOOK_DEPS += $(PDFS_FROM_EPS)

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
