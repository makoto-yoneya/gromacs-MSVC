# gromacs-MSVC

Sample binary executables (in release section) of [GROMACS-2019.6][1] build with Visual Studio 2019

## Releases

- gromacs-2019.6-win64gpu.zip

Single precision executable run with (at least) AVX-256 CPU under 64bit Windows (and cuda10.1) with NVIDIA GPU

Build under Visual Studio 2019 x64 Native Tools Command Prompt with

`cmake -G "NMake Makefiles" -DGMX_FFT_LIBRARY=fftpack -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX="C:\app\gromacs" -DGMX_SIMD=AVX_256 -DGMX_GPU=ON ..\gromacs-2019.6`

then

`nmake install`

- gromacs-2019.6-win32.zip

Single precision executable run with (at leaset) SSE2 CPU under 32bit (or 64bit) Windows

Build under Visual Studio 2019 x86 Native Tools Command Prompt with

`cmake -G "NMake Makefiles" -DGMX_FFT_LIBRARY=fftpack -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX="C:\app\gromacs" -DGMX_SIMD=SSE2 -DGMX_GPU=OFF ..\gromacs-2019.6`

then

`nmake install`

## Prerequisites

[Visual studio 2019 redistributable][2]

[cuda10.1][3] (for NVIDIA GPU)

## Creater

Makoto Yoneya.

[1]: http://manual.gromacs.org/documentation/
[2]: https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads
[3]: https://developer.nvidia.com/cuda-10.1-download-archive-base
