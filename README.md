# LLD+LLVM packages for Windows
Download builds from [actions](https://github.com/valium007/win-llvm/actions) tab

## Abstract

LLVM is huge, and it's getting bigger with each and every release. Building it together with a project that depends on it (e.g., a programming language) during a CI build is **not an option** -- building *just LLVM* eats most (earlier LLVM releases), and all (recent LLVM releases) of the allotted CI build time.

So why not use pre-built packages from the official [LLVM download page](https://releases.llvm.org) Unfortunately, the official binaries cover just a *tiny fraction* of possible build configurations on Microsoft Windows. There are no Debug libraries, no builds for the static LIBCMT, and only a single toolchain per LLVM release.

The llvm-package-windows project builds all major versions of LLVM on **GitHub Actions** for the following, much more complete matrix:

* Toolchain:
	- Visual Studio 2019

* Configuration:
	- Release

* Target CPU:
	- AMD64 (a.k.a. x86_64)

* C/C++ Runtime:
	- MSVCRT (dynamic)

The resulting LLVM binary packages are uploaded as GitHub Release artifacts. Compiler developers can now thoroughly test their LLVM-dependent projects on GitHub CI or AppVeyor CI simply by downloading and unpacking an archive with the required LLVM prebuilt binaries during the CI installation stage.

