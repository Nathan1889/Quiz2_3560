all: build doc doczip

build: myexe

doczip: documentation.tar.gz

doc: html/index.html

myexe: course.o college.o collegemain.o
	g++ -Wall *.o -o myexe
%.o: %.cc %.h
	g++ -g -Wall -c $<
documentation.tar.gz: html/index.html
	tar -czvf documentation.tar.gz html latex
html/index.html: myexe
	doxygen *.cc *.h
clean:
	-rm -rf myexe html/ latex/ *.o *.class *.out *.gz *.tar
