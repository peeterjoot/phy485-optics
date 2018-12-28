THISDIR := phy485-optics
THISBOOK := phy485

export BOOKSUBVER := 1
export BOOKMAJVER := 0
# This isn't a good way to version.  It depends on the local git reflog history count.
export REVCOUNTSTART := 1

include ../latex/make.bookvars

FIGURES := ../figures/phy485-optics

#ONCEFLAGS := -justonce

SOURCE_DIRS += appendix
SOURCE_DIRS += $(FIGURES)

GENERATED_SOURCES += mathematica.tex 

include ../latex/make.rules
