# $Id: makefile 162 2019-01-14 09:36:11Z rishi $

file=paper_tennantite


all: pdf out 
	make pdf
	make bibtex
	make pdf
	make view

out:
	if  [ -f $(file).out ] ; then cp $(file).out tmp.out; fi ;
	sed 's/BOOKMARK/dtxmark/g;' tmp.out > x.out; mv x.out tmp.out ;

bibtex:
	bibtex $(file).aux
pdf:
	pdflatex -interaction nonstopmode -halt-on-error -file-line-error $(file).tex

index:
	makeindex -s gind.ist -o $(file).ind $(file).idx 

changes:
	makeindex -s gglo.ist -o $(file).gls $(file).glo

xview:
#	xpdf -z 200 $(file).pdf &>/dev/null
	open -a 'Skim.app' $(file).pdf 

view:
	open -a 'Preview.app' $(file).pdf

ins:
	latex $(file).ins 

diff:
	diff $(file).sty ../$(file).sty |less

copy:
	cp $(file).sty ../




