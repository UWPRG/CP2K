
## Instructions to compile additional libraries for CP2k  with intel 17 compilers.

#### ELPA: Download ELPA from

a) Download, uncompress and create build folder

Download  ELPA from:

http://elpa.mpcdf.mpg.de/elpa-tar-archive

Version 2016.11.004 is tested

`tar xf elpa-2016.05.004.tar.gz`

`cd elpa-2016.05.004`

`mkdir build (as per developers suggestions)`

`cd build`

b) Load intel 17 compilers

`module load icc_17-impi_2017`

c) configure, make and make install

`../configure SCALAPACK_LDFLAGS="-L$MKLROOT/lib/intel64 -lmkl_scalapack_lp64 -lmkl_intel_lp64 -lmkl_sequential -lmkl_core -lmkl_blacs_intelmpi_lp64 -lpthread -lm -Wl,-rpath,$MKLROOT/lib/intel64" SCALAPACK_FCFLAGS="-L$MKLROOT/lib/intel64 -lmkl_scalapack_lp64 -lmkl_intel_lp64 -lmkl_sequential -lmkl_core -lmkl_blacs_intelmpi_lp64 -lpthread -lm -I$MKLROOT/include/intel64/lp64"--prefix=PATH/OF/THE/BUILD/FOLDER/`

`make`

`make install`

#### LIBXC

a) Download, uncompress and create build folder

Download here: http://octopus-code.org/wiki/Libxc:download

Version 2.2.2 is tested

`tar xf libxc-2.2.2.tar.gz`

`cd libxc-2.2.2`

b) run autoconf, configure then make and make install

`autoreconf -i `
(I got a warning here, doesn't seem to give any further error)

`./configure --prefix=PATH/to/the/library/folder/libxc`

`make`

`make install`

#### LIBINIT

a) Download, uncompress

Download here: https://sourceforge.net/projects/libint/files/v1-releases/libint-1.1.5.tar.gz/download

Version 1.1.5 is tested

`tar xf libint-1.1.5.tar.gz`

`cd libint-1.1.5`

c) load intel 17 compilers:

`module load icc_17-impi_2017`

d) Configure and install

Instructions on the original arch file hold:

 `env AR=xiar FC=ifort F77=ifort F90=ifort FCFLAGS="-O2 -xHost -ipo" CC=icc CFLAGS="-O2 -xHost -ipo"  CXX=icpc CXXFLAGS="-O2 -xHost -ipo" ./configure --prefix=/gscratch/scrubbed/lflo/cp2k2017/cp2k/libint-1.1.5/OBJDIR --with-cc-optflags="-O2 -xHost -ipo" --with-cxx-optflags="-O2 -xHost -ipo" --with-libint-max-am=5 --with-libderiv-max-am1=4`

`make`

`make install`

####   LIBXSMM

a) Clone

`git clone https://github.com/hfp/libxsmm.git`

b) Make

`make -f Makefile`
