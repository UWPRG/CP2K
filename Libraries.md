
## Instructions to compile additional libraries for CP2k

1) ELPA: Download ELPA from http://elpa.mpcdf.mpg.de/elpa-tar-archive tar -xvzf
cd elpa
mkdir build ( as per developers suggestions)
cd build ( as per developers suggestionns)
../configure SCALAPACK_LDFLAGS="-L$MKLROOT/lib/intel64 -lmkl_scalapack_lp64 -lmkl_intel_lp64 -lmkl_sequential \
                           -lmkl_core -lmkl_blacs_intelmpi_lp64 -lpthread -lm -Wl,-rpath,$MKLROOT/lib/intel64"       SCALAPACK_FCFLAGS="-L$MKLROOT/lib/intel64 -lmkl_scalapack_lp64 -lmkl_intel_lp64 -lmkl_sequential \
                          -lmkl_core -lmkl_blacs_intelmpi_lp64 -lpthread -lm -I$MKLROOT/include/intel64/lp64" --prefix=PATH/OF/THE/BUILD/FOLDER/
                          
make
make install
