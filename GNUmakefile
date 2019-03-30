THISDIR := phy485-optics
THISBOOK := phy485

BIBLIOGRAPHY_PATH := classicthesis_mine
HAVE_OWN_CONTENTS := 1
HAVE_CUSTOM_DEDICATION := 1
MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/Index.tex
MY_CLASSICTHESIS_FRONTBACK_FILES += ../latex/classicthesis_mine/FrontBackmatter/ContentsAndFigures.tex

include make.revision
include ../latex/make.bookvars

FIGURES := ../figures/phy485-optics

#ONCEFLAGS := -justonce

SOURCE_DIRS += appendix
SOURCE_DIRS += $(FIGURES)

GENERATED_SOURCES += mathematica.tex

include ../latex/make.rules

clean ::
	git checkout $(THISBOOK).tex
