#LATEX = uplatex
LATEX = platex
BIBTEX = bibtex

.PHONY: all


EBB= extractbb -m

#all : a-gift-of-fire-jp.pdf beamerexport-jp-1.pdf beamerexport-jp-2.pdf beamerexport-jp.pdf presentation-jp.pdf
#all : beamerexport-jp.pdf latexexport1.pdf
#all : tanimoto-mod.pdf
#all : tanimoto-mod2.pdf
#all : tanimoto-mod3.pdf
#all : tb_kiban_c.pdf
all : kiban_c.pdf

#a-gift-of-fire-jp.pdf : a-gift-of-fire-jp.dvi
#	dvipdfmx a-gift-of-fire-jp.dvi


%.pdf: %.dvi 
	dvipdfmx  $<

# 	dvipdfmx  -f ipaEmbed.map  $<
# #	dvipdfmx  -f hiraginoEmbed.map  $<
# #	dvipdfmx  -f noEmbed.map  $<


#a-gift-of-fire-jp.dvi : a-gift-of-fire-jp.tex
#	platex a-gift-of-fire-jp.tex

%.dvi: %.tex 
	 $(LATEX)  $<  ; $(BIBTEX) $* ; $(LATEX) $* ; $(LATEX) $* ; $(BIBTEX) $* ; $(LATEX) -shell-escape $* 


#%.dvi: %.tex 
#	(cd images ; ebb *.png ) ; platex  $<

# %.aux: %.tex
# 	bibtex 

#kiban_c.tex : kiban_c_01-02_purpose.tex kiban_c_03-04_plan.tex kiban_c_05_preparation_final_year.tex kiban_c_06-07_publications.tex kiban_c_08_past_funds.tex kiban_c_09_relation.tex kiban_c_10_human_rights_etc.tex kiban_c_11_materials.tex kiban_c_12_travels.tex kiban_c_13_other_applications.tex kiban_c_14_other_funds.tex mypub.tex


#kiban_c.dvi: kiban_c.tex kiban_c_01-02_purpose.tex kiban_c_03-04_plan.tex kiban_c_05_preparation_final_year.tex kiban_c_06-07_publications.tex kiban_c_08_past_funds.tex kiban_c_09_relation.tex kiban_c_10_human_rights_etc.tex kiban_c_11_materials.tex kiban_c_12_travels.tex kiban_c_13_other_applications.tex kiban_c_14_other_funds.tex mypub.tex
# kiban_c.dvi: kiban_c.tex 
# 	(cd images ; $(EBB) *.png ) ; platex kiban_c;  bibtex kiban_c ;platex kiban_c;  bibtex kiban_c ;  platex  -shell-escape  kiban_c.tex

#%.dvi: %.tex
#	(cd images ; $(EBB) *.png ) ; platex  -shell-escape  $< 


 

#%.bb: %.png 
#	ebb  $<

#images/%.bb: images/%.png 
#	ebb  $<


%.xbb : %.png 
	extractbb  $<
%.bb : %.xbb
	extractbb -m $<



#a-gift-of-fire-jp.tex : a-gift-of-fire-jp.org

%.tex: %.org



.PHONY: clean

clean:
	rm -f *.pdf *.dvi *.log *.vrb *.out *.toc *.nav *.snm *.aux *.blg *.bbl


