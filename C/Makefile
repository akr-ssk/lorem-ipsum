#!/usr/bin/make

# C99 Bild Makefile
FINAL_BIN = example
CFLAGS = -std=c99 -Wall -O2
INCLDIR = -I/usr/include
LIBDIR = -L/lib64 -L/usr/lib64
LIBS = -lc

OBJS = 

.SUFFIXES: .c .o

.c.o:
	${CC} ${CFLAGS} ${INCLDIR} -c $<

all: depend ${FINAL_BIN}

${FINAL_BIN}: ${OBJS}
	${CC} -o ${FINAL_BIN} ${LIBDIR} ${LIBS} $^
	
.PHONY: clean

# header dependency
depend: ${OBJS:.o=.c}
	-@ ${RM} depend.inc
	-@ for i in $^; do ${CC} -MM $$i >> depend.inc; done

clean:
	${RM} ${OBJS} ${FINAL_BIN}

 -include depend.inc
