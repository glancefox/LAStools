# makefile for all example of how to use LASlib (when linking statically)
#
#COPTS    = -g -Wall
COPTS     = -O3 -Wall -Wno-strict-aliasing -Wno-unused-result
COMPILER  = g++
LINKER  = g++
#BITS     = -64

#LIBS     = -L/usr/lib32
#LIBS     = -L/usr/lib64
INCLUDE  = -I/usr/include

LASLIBS     = -L../lib
LASINCLUDE  = -I../../LASzip/src -I../inc

all: lasexample lasexample_write_only lasexample_add_rgb

lasexample: lasexample.o
	${LINKER} ${BITS} ${COPTS} lasexample.o -llas -o $@ ${LIBS} ${LASLIBS} $(INCLUDE) $(LASINCLUDE)

lasexample_write_only: lasexample_write_only.o
	${LINKER} ${BITS} ${COPTS} lasexample_write_only.o -llas -o $@ ${LIBS} ${LASLIBS} $(INCLUDE) $(LASINCLUDE)

lasexample_add_rgb: lasexample_add_rgb.o
	${LINKER} ${BITS} ${COPTS} lasexample_add_rgb.o -llas -o $@ ${LIBS} ${LASLIBS} $(INCLUDE) $(LASINCLUDE)

.cpp.o: 
	${COMPILER} ${BITS} -c ${COPTS} ${INCLUDE} $(LASINCLUDE) $< -o $@

.c.o: 
	${COMPILER} ${BITS} -c ${COPTS} ${INCLUDE} $(LASINCLUDE) $< -o $@

clean:
	rm -rf *.o
	rm -rf lasexample lasexample_write_only lasexample_add_rgb

clobber:
	rm -rf *.o
	rm -rf lasexample lasexample_write_only lasexample_add_rgb
	rm -rf *~
