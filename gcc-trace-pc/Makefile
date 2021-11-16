CC=gcc
CFLAGS=-g -ggdb -fsanitize-coverage=trace-pc
LIBS=
DEPS=trace.h
OBJ=main.o trace.o

all: main

trace.o: trace.c
	$(CC) -c -o $@ $<

main.o: main.c
	$(CC) -c -o $@ $< $(CFLAGS) $(LIBS)

main : $(OBJ)
	$(CC) -o $@ $^ $(CFLAGS) $(LIBS)

.PHONY: clean

clean:
	rm -f *.o main