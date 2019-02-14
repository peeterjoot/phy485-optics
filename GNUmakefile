THISDIR := phy485-optics
THISBOOK := phy485

export BOOKSUBVER := 1
export BOOKMAJVER := 0
export REVISIONNUMBER := 8

#.revinfo/gitCommitDateAsMyTime.tex:\newcommand{\myTime}{April 2018}\newcommand{\myVersion}{version V0.117\xspace}
VER := $(shell grep Version .revinfo/gitCommitDateAsMyTime.tex | sed 's/.*{//;s/.xspace.*//;')

include ../latex/make.bookvars

FIGURES := ../figures/phy485-optics

#ONCEFLAGS := -justonce

SOURCE_DIRS += appendix
SOURCE_DIRS += $(FIGURES)

GENERATED_SOURCES += mathematica.tex 

include ../latex/make.rules

dist:
	cp $(THISBOOK).pdf $(THISBOOK).$(VER).pdf

# a for annotate (releases).
tag:
	git tag -a $(THISBOOK).$(VER).pdf
