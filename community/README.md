This directory hosts files and tools maintained by the community.


Added:

To build the dockerfile (may take 15-18mins):
  1. cd to community directory, or the directory containing the dockerfile
  2. Use the command : `$docker build -t <image name> .`
    note: if this outputs error on the line `RUN ./contrib/setup-lingeling.sh && ./configure.sh --shared --prefix /usr`, change it to `RUN ./contrib/setup-lingeling.sh && ./contrib/setup-btor2tools.sh && ./configure.sh --shared --prefix /usr`
  

To run the image: 

  Use : `$docker run <options> -it <image name>` 
  
  Typical options are: 
  
   * `-v <working directory, such as /home/user/sys>:/host` which will copy everything under your working directory into the /host directory in the image
    
  * `--rm` removes the container after existing
    
  Inside the container, you can use `$ cp <path to file> /host` to copy files in the image to the directory where you start the container.
