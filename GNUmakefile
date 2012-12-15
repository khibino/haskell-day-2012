
%.pdf: %.dvi
	dvipdfmx -f cid-embed $(@:.pdf=.dvi)

%.dvi %.log %.aux: %.tex
	platex $<

%.png: %.dia
	dia -e $@ $<

%.ppm: %.png
	convert $< $@

%.bb: %.ppm
	bbox $< > $@

%.o: %.hs
	ghc -c -Wall $<

images = \
	dep10.png dep10.bb \
	dep11.png dep11.bb \
	dep12.png dep12.bb \
	dep13.png dep13.bb \
	dep20.png dep20.bb \
	dep21.png dep21.bb \



all:: $(images) CabalDebian.dvi CabalDebian.pdf

CabalDebian.dvi: $(images)

clean::
	$(RM) *.o *.hi
	$(RM) *.dvi *.log *.aux *.toc
	$(RM) *.vrb *.out *.nav *.snm
	$(RM) *.bb *.png

veryclean: clean
	$(RM) *.pdf
