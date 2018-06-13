### Instructions to compile CP2K (intel 17 compilers)

1) Clone CP2K:  

  ` git clone https://github.com/cp2k/cp2k.git`  
  update June/2018: the most recent version (Version 7 from cp2k github) will not work with my arch file (the one in this repo).
  Use version 6 instead `/gscratch/pfaendtner/codes/`

2) Instructions from the website, a little bit out of date but worth to read.

https://www.cp2k.org/howto:compile

3) Load modules.

`module load icc_17-impi_2017`

4) Arch file

An arch file, Linux-x86-64-intel-mic.psmp, is in this repository (with FLAGS for different libraries, see Additional_libraries_howto.md for their installation).
Copy the installation file to the arch folder.

5) Install

Go to cp2k/makefiles and compile CP2K:

`cd cp2k/makefiles`  
`make -j 28 ARCH=Linux-x86-64-intel VERSION=psmp`

If everything went ok, the executables are in the
`cp2k/exe/Linux-x86-64-intel` directory.

6) Testing

Update June/2018: if you compiled CP2K with my Elpa, before running the tests, you have to set this:
`export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/gscratch/pfaendtner/codes/cp2k/lib/elpa-2016.05.004/build/lib`

Run
`make -j 2 ARCH=Linux-x86-64-intel-host VERSION=psmp test`
more information on the website.


