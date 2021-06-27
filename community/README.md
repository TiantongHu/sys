This directory hosts files and tools maintained by the community.



Added:


To build the dockerfile (may take 15-18mins):
  1. cd to community directory, or the directory containing the dockerfile
  2. Use the command : `$docker build -t <image name you give> .` 
      
      * if this outputs error on the line `RUN ./contrib/setup-lingeling.sh && ./configure.sh --shared --prefix /usr`, change the dockerfile line 32 to `RUN ./contrib/setup-lingeling.sh && ./contrib/setup-btor2tools.sh && ./configure.sh --shared --prefix /usr`
  
  



To run the container: 

  Use : `$docker run <options> -it <image name>` 
  
  Typical options are: 
   * `--rm` removes the container after existing
  
   * `-v <path to working directory>:/host` which will mount your working directory with the `/host` directory in the container, so you can acess any needed file
     * Add `--read-only` before `-v` to make the directory read only in the container 
    
     * Inside the container, you can use `$ cp <path to file> /host` to copy files in the image to the `<working directory>` you stated in `-v` option.
 
