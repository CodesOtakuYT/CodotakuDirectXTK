DirectX 12 (D3D12) with DirectX toolkit (DirectXTK12) modern setup, C++ 23 programming language, CMake build generator and vcpkg package manager compatible with CLion
Clone the repo with submodules
```ps1
git clone --recurse-submodules https://github.com/CodesOtakuYT/CodotakuDirectXTK.git
cd CodotakuDirectXTK
```
Then everytime you open the project, run this powershell script to configure the dev environment like adding vcpkg to the path for the current session (Optional)
You may need to enable powershell execution first to run that script
otherwise you can just use vcpkg directly (./vcpkg/vcpkg.exe) after bootstraping it (CLion would do it automatically after opening the project)
```ps1
Set-ExecutionPolicy RemoteSigned -Scope Process
./setup-dev.ps1
```
This is a patched version of the official microsoft template d3d12game_vcpkg from [directx-vs-templates](https://github.com/walbourn/directx-vs-templates/tree/88d18638e66f8e2cd61bc743753fd6b5bf7cd83c/d3d12game_vcpkg). patches applied:
- Added vcpkg as a git submodule
- Added DirectXTK12 as a vcpkg port
- Include DirectXTK12 headers and initialize GraphicsMemory in Game.h and Game.cpp
If you want to apply the patches yourself from the official templates, here is a [video tutorial](https://www.youtube.com/watch?v=Qhk7q06IZhM) I made.
some more tips:
- Create a Dev Drive filesystem (ReFS) for faster development comparable to linux filesystem. NTFS windows default filesystem is very inefficient for development
- Install [PIX graphics debugger](https://devblogs.microsoft.com/pix/download/)
- You may wanna enable [Developer Mode](https://learn.microsoft.com/en-us/windows/apps/get-started/enable-your-device-for-development) on windows
- If you have NVIDIA, you may wanna [enable access to GPU performance counters](https://www.nvidia.com/content/Control-Panel-Help/vLatest/en-us/mergedProjects/nvdev/To_enable_access_to_GPU_performance_counters_for_developrs.htm)

Pre-requisites:
- [Build Tools for Visual Studio 2022](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2022) with C++ Desktop Development Workload
- [Git](https://git-scm.com/downloads/win)

Have fun! and feel free to contribute
