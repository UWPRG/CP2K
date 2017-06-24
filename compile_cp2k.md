### Instructions to compile CP2K (intel 17 compilers)

1) Clone CP2K:  

  ` git clone https://github.com/cp2k/cp2k.git`

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
`make -j 28 ARCH=Linux-x86-64-intel-host VERSION=psmp`

If everything went ok, the executables are in the
`cp2k/exe/Linux-x86-64-intel-host` directory.

6) Testing

Run
`make -j 2 ARCH=Linux-x86-64-intel-host VERSION=psmp test`
more information on the website.

You can test Plumed and CP2K with the files in

`cp2k/tests/Fist/regtest-plumed2`

for example

`cp2k.psmp -o water.out water.inp`
