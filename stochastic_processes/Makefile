all: homework-doob-h-transform-with-python-notebooks.pdf \
    midterm-sample-exam-1.pdf \
    midterm-sample-exam-2.pdf \
    perfect-sampling-with-coupling-from-the-past.pdf

%.pdf: %.md Makefile
	pandoc $< -o $@
