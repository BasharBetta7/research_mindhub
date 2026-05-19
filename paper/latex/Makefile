MAIN = main
BUILD = build
TEXINPUTS = ./access//:
BIBINPUTS = ../../:
BSTINPUTS = ./access//:
TFMFONTS = ./access//:
T1FONTS = ./access//:
TEXFONTMAPS = ./access//:
LATEX_ENV = TEXINPUTS="$(TEXINPUTS)" BIBINPUTS="$(BIBINPUTS)" BSTINPUTS="$(BSTINPUTS)" TFMFONTS="$(TFMFONTS)" T1FONTS="$(T1FONTS)" TEXFONTMAPS="$(TEXFONTMAPS)"

.PHONY: all clean distclean open watch

all:
	mkdir -p $(BUILD)
	$(LATEX_ENV) pdflatex -interaction=nonstopmode -synctex=1 -output-directory=$(BUILD) $(MAIN).tex
	if grep -q '\\citation' $(BUILD)/$(MAIN).aux; then $(LATEX_ENV) bibtex $(BUILD)/$(MAIN); fi
	$(LATEX_ENV) pdflatex -interaction=nonstopmode -synctex=1 -output-directory=$(BUILD) $(MAIN).tex
	$(LATEX_ENV) pdflatex -interaction=nonstopmode -synctex=1 -output-directory=$(BUILD) $(MAIN).tex

clean:
	rm -f $(BUILD)/*.aux $(BUILD)/*.bbl $(BUILD)/*.blg $(BUILD)/*.log $(BUILD)/*.out $(BUILD)/*.toc $(BUILD)/*.synctex.gz

distclean:
	rm -rf $(BUILD)

open:
	xdg-open $(BUILD)/$(MAIN).pdf

watch:
	@echo "Watching $(MAIN).tex and sections/*.tex. Press Ctrl+C to stop."
	@last=""; \
	while true; do \
		current=$$(find $(MAIN).tex sections -type f -name '*.tex' -printf '%T@\n' | sort -nr | head -n 1); \
		if [ "$$current" != "$$last" ]; then \
			last="$$current"; \
			$(MAKE) all; \
		fi; \
		sleep 1; \
	done
