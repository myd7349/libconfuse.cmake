libconfuse.cmake
=====

`CMakeLists.txt` for [```libconfuse```](https://github.com/martinh/libconfuse)

Test with [<kbd>2f7d120</kbd>](https://github.com/martinh/libconfuse/tree/2f7d120e170351cf424845ed27a532cce443247d).

Build & Install
=====

mkdir my_genimage && cd my_genimage
mkdir build-libconfuse
git clone https://github.com/libconfuse/libconfuse
# put to original libconfuse/ folder files CMakeLists.txt and config.h.in (replace)
cmake -S libconfuse/ -B build_libconfuse/ -DCMAKE_BUILD_TYPE=Release
cmake --build build_libconfuse/ --parallel 
cd build_libconfuse/
sudo checkinstall
# to remove use: dpkg -r build-libconfuse

License
=====

MIT
