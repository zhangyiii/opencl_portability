CCFLAGS=-O3 -std=gnu99 -ffast-math

LIBS = -lm -lOpenCL -fopenmp -lrt

all: convolve

utils.o: ../utils.c
	gcc -c $^ -o $@ -lrt -g

convolve: main.c utils.o
	gcc $(CCFLAGS) -o $@ $^  $(LIBS)
	
convolve_image: main.c utils.o
	gcc $(CCFLAGS) -o $@ $^  $(LIBS) `pkg-config --cflags --libs MagickWand` -D USE_MAGICK 

clean:
	rm *.o convolve