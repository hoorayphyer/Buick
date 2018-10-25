# BUICK: Build Usher In CmaKe
## `cd build && cmake ..` no more! Let's `buick .`!

`buick` is a snippet to automate running `cmake` in a user-defined build directory to prevent the notorious cmake build cache files contamination.

## Install
Download and `chmod` the script `buick`.

## Usage
1. `buick *path_to_CMakeLists* *cmake_commandline_arguments*` will creates `./build` and run `cmake *cmake_commandline_arguments*` in it. *path_to_CMakeLists* can be relative.
2. The above command will create `./.buick` in which the build directory and last successful cmake command are cached.
3. So next time `buick` will repeat step 1 automatically.
4. `buick --clean` will `rm -rf ` the cached build directory if it exists. Passing `--clean` will make `buick` ignore all other arguments.

## Caveats
* Relative paths used in cmake commandline options may not be all supported
