
%.pdf: %.dvi
	dvipdfmx $(@:.pdf=.dvi)

%.dvi %.log %.aux: %.tex
	platex $<

%.ppm: %.png
	convert $< $@

%.bb: %.ppm
	bbox $< > $@

%.o: %.hs
	ghc -c -Wall $<

bbs = 

all:: $(bbs) CabalDebian.dvi CabalDebian.pdf

clean::
	$(RM) *.o *.hi
	$(RM) *.dvi *.log *.aux *.toc
	$(RM) *.vrb *.out *.nav *.snm
	$(RM) *.bb

veryclean: clean
	$(RM) *.pdf
