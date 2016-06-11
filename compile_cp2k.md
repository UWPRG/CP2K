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
    
4) Arch file and make

I have attached my arch file here (with the Plumed, no need to source code patches). So copy it to your arch folder and then:
    ```bash
  cd cp2k/makefiles
      ```
  
