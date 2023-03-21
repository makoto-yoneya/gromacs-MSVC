# gromacs-MSVC

Sample binary executables (in release section) of [GROMACS-2023][1] build with Visual Studio 2022 Native Tools

## Releases

- gromacs-2023-win64cuda.zip

Single precision executable run with (at least) AVX-256 CPU under 64bit Windows (and cuda12.1) with NVIDIA GPU

Apply patch for the original gromacs-2023 sources.

`patch -p1 < gromacs-2023_MSVC_cuda.patch`

then

Build under Visual Studio 2022 x64 Native Tools Command Prompt with

`cmake -G "NMake Makefiles" -DGMX_FFT_LIBRARY=fftpack -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX="C:\opt\gromacs-2023cuda" -DGMX_SIMD=AVX_256 -DGMX_GPU=CUDA ..\gromacs-2023`

then

`nmake install`

- gromacs-2023-win32.zip

Single precision executable run with (at leaset) SSE2 CPU under 32bit (or 64bit) Windows

Build under Visual Studio 2022 x86 Native Tools Command Prompt with

`cmake -G "NMake Makefiles" -DGMX_FFT_LIBRARY=fftpack -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX="C:\opt\gromacs-2023" -DGMX_SIMD=SSE2 -DGMX_GPU=OFF ..\gromacs-2023`

then

`nmake install`

## Prerequisites

[Visual studio 2022 redistributable][2]

[cuda12.1][3] (for NVIDIA GPU)

## Creater

Makoto Yoneya.

[1]: http://manual.gromacs.org/documentation/
[2]: https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads
[3]: https://developer.nvidia.com/cuda-toolkit
