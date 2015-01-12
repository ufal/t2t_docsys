include ../Makefile.include

.PHONY: all doc install
all: doc
doc: readme.txt readme_md.md
install: doc
	cp readme.txt ../README
	cp readme_md.md ../README.md

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
