course = main

.PHONY : all clean test

all: clean $(course)

test: clean
	raco test .

$(course):
	scribble --htmls \
		++style css/extra.css \
		++style css/fancyverb.css \
		++extra js/accessibility.js \
		++xref-in setup/xref load-collections-xref \
		--redirect-main http://docs.racket-lang.org/ \
		$(course).scrbl
	mkdir -p $(course)/code/
	cd notes ; \
		tar -c `git ls-files -X .gitignore abscond blackmail con dupe extort fraud hustle` | \
		(cd ../main/code ; tar -x) ; cd ../..

clean:
	rm -rf $(course)
