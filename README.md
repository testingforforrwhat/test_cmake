# test_cmake

```asm
cd Desktop/
git clone https://github.com/testingforforrwhat/test_cmake.git
ls -l
cd test_cmake
mkdir build
cd build
cmake ..
make
ls -l
./test_cmake hw:0 12.pcm

ctrl+c
ffplay -ar 44100 -channels 2 -f s16le -i 12.pcm
```