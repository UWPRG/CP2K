
## Instructions to compile additional libraries for CP2k  with intel 17 compilers. 
 
1) ELPA: Download ELPA from http://elpa.mpcdf.mpg.de/elpa-tar-archivedddd

Version 2016.05.004 is tested

tar -xvzf elpa-2016.05.004.tar.gz

cd elpa

mkdir build (as per developers suggestions)

cd build (as per developers suggestionns)


../configure SCALAPACK_LDFLAGS="-L$MKLROOT/lib/intel64 -lmkl_scalapack_lp64 -lmkl_intel_lp64 -lmkl_sequential \
                           -lmkl_core -lmkl_blacs_intelmpi_lp64 -lpthread -lm -Wl,-rpath,$MKLROOT/lib/intel64"       SCALAPACK_FCFLAGS="-L$MKLROOT/lib/intel64 -lmkl_scalapack_lp64 -lmkl_intel_lp64 -lmkl_sequential \
                          -lmkl_core -lmkl_blacs_intelmpi_lp64 -lpthread -lm -I$MKLROOT/include/intel64/lp64" --prefix=/gscratch/pfaendtner/lflo/cp2k_icc_15.0.3-impi_5.0.3/elpa-2016.05.004/build --prefix=PATH/OF/THE/BUILD/FOLDER/
                          
make

make install

2) LIBXC

Download LIBXC

Version 2.2 is tested

untar then cd

autoreconf
./configure --prefix=PATH/to/the/library/folder/libxc

make 

make install

3) LIBINIT
Download libinit: http://sourceforge.net/projects/libint/files/v1-releases/libint-1.1.4.tar.gz/download

