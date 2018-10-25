# BUICK: Build Usher In CmaKe
## `cd build && cmake ..` no more! Let's `buick .`!

`buick` is a snippet to automate running `cmake` in a user-defined build directory to prevent the notorious cmake build cache files contamination.

## Install
Download and `chmod` the script `buick`. To make it system-wide available, just create an alias in your shell rc file.

## Usage
0. `buick` with no arguments will `cd` to the build directory and `make`.
1. <pre>buick <i>path_to_CMakeLists</i> <i>cmake_commandline_arguments</i></pre> will create `./build` and run <pre>cmake <i>cmake_commandline_arguments</i></pre> in it. <i>path_to_CMakeLists</i> can be relative.
2. The above command will create `./.buick` in which the build directory and last successful cmake command are cached.
3. `buick --last-cmake` runs the cached cmake command.
3. <pre>buick --build-dir=<i>your_build_dir</i></pre> uses a different directory than the default `./build`.
4. `buick --clean` will `rm -rf ` the cached build directory if it exists. Passing `--clean` will make `buick` ignore all other arguments.

## Caveats
* I only included gnu make. For other build tools, modify the script as needed.
* Relative paths used in cmake commandline options may not be properly supported.
