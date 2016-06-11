## Instructions to compile AMBER14 on Hyak

1) Download or clone CP2K:
  
   ```bash
    https://www.cp2k.org/download or
    git clone https://github.com/cp2k/cp2k.git
  ```
  
2) Instructions from the website, out-of-dated, but worth to read.

https://www.cp2k.org/howto:compile

3) Load module.
  ```bash
   module load icc_15.0.3-impi_5.0.3
 ```

4) Arch file

I have attached my arch file here (with the Plumed FLAGS, no need to source code patches). Copy it to the arch folder.
  
5) Install 
 
  Go to cp2k/makefiles and build CP2K:
  ```bash
    cd cp2k/makefiles
    make -j 8 ARCH=Linux-x86-64-intel-host VERSION=psmp
    ```
  
If everything went ok, the executables are in the cp2k/exe/Linux-x86-64-intel-host directory.
  
6) Testing

You can test Plumed and CP2K with the files in cp2k/tests/Fist/regtest-plumed2
 ```bash
cp2k.psmp -o water.out water.inp
 ```
NB: I used the latest Plumed compiled by Chris (with MATHEVAL)
 
