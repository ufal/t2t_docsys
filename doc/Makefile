include ../Makefile.include

all:
	@echo "make [html | txt | md | pdf | manual]"

html: readme.html
txt: readme.txt
md: readme.md
pdf: readme.pdf
manual: readme.txt readme.md
	cp readme.txt ../README
	cp readme.md ../README.md

%.html: %.t2t $(wildcard *.t2t)
	$(call t2t_docsys_html,$@,$<,manual striplevel)

%.txt: %.t2t $(wildcard *.t2t)
	$(call t2t_docsys_txt,$@,$<,manual)

%.md: %.t2t $(wildcard *.t2t)
	$(call t2t_docsys_md,$@,$<,manual)

%.pdf: %.t2t $(wildcard *.t2t)
	$(call t2t_docsys_pdf,$@,$<,manual striplevel)

.PHONY: clean
clean:
	@rm -f $(wildcard $(T2T_DOCSYS_OUTPUT_WILDCARDS))
