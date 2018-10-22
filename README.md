#### installing wasm
      official link : http://kripken.github.io/emscripten-site/docs/getting_started/downloads.html
      prerequisites : python , node, git, jre(optional)
      
      
#### Download sdk
      home> git clone https://github.com/juj/emsdk.git

#### Enter that directory
      cd emsdk
      ../emsdk>
      

#### Fetch the latest version of the emsdk (not needed the first time you clone)
    ../emsdk> git pull

#### Download and install the latest SDK tools.
    ../emsdk> ./emsdk install latest

#### Make the "latest" SDK "active" for the current user. (writes ~/.emscripten file)
    ../emsdk> ./emsdk activate latest

#### Activate PATH and other environment variables in the current terminal
    ../emsdk> source ./emsdk_env.sh
    
    
    
#### running first program

      http://kripken.github.io/emscripten-site/docs/getting_started/Tutorial.html
      
#### emscripten version
      home> ./emcc -v
      or
      home> emcc -v
      
#### Document/example/wasmhw.c
      #include <stdio.h>

      int main() {
        printf("hello, world!\n");
        return 0;
      }


#### build
      ./emcc tests/wasmhw.c
      or
      emcc tests/wasmhw.c



      You should see two files generated by that command: a.out.js and a.out.wasm. 
      The second is a WebAssembly file containing the compiled code, 
      and the first is a JavaScript file containing the runtime support to load and execute it. 
      You can run them using node.js:

      node a.out.js
