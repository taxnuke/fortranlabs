FC=gfortran
FFLAGS=-Wall -std=f2008ts -fimplicit-none -Wno-maybe-uninitialized -static-libgfortran -flto
FOPT=-O3 -fopt-info-vec

all:
	$(FC) $(FFLAGS) -c src/environment.f90 -J obj/ -o obj/environment.o
	$(FC) $(FFLAGS) -c src/m_common.f90 -J obj/ -o obj/m_common.o
	$(FC) $(FFLAGS) -c src/m_io.f90 -J obj/ -o obj/m_io.o
	$(FC) $(FFLAGS) $(FOPT) -c src/m_sorting.f90 -J obj/ -o obj/m_sorting.o
	$(FC) $(FFLAGS) $(FOPT) -c src/lab_3.f90 -I obj/ -o obj/lab_3.o
	$(FC) $(FFLAGS) $(FOPT) -o bin/lab_3 obj/environment.o obj/m_sorting.o obj/m_common.o obj/m_io.o obj/lab_3.o

clean:
	rm -f obj/*
	rm -f bin/*

run:
	cd ./bin; ./lab_3
	cat ./bin/F2.txt
	cat ./bin/F3.txt
