# Deskpad STEP support

The optional STEP support download for [Deskpad](https://50400studios.com): `StepToMesh.exe`, a small
separate program that turns STEP files (.step, .stp) into .glb models for Deskpad's 3D viewer.
Deskpad downloads these files only when you press **Download** in Settings → Hardware tools, checks
each one against the SHA-256 in `manifest.json`, and keeps them on your PC.

## What's inside

- `StepToMesh.exe`, built from Deskpad's `tools/StepToMesh` source (C++, CMake, vcpkg).
- **Open CASCADE Technology 8.0.1** DLLs (`TK*.dll`), under the GNU LGPL 2.1 with the Open CASCADE
  exception (`LICENSE-opencascade.txt`). They're unmodified and kept as separate DLLs, so you can
  swap them for your own build. Source: https://github.com/Open-Cascade-SAS/OCCT (tag V8_0_1),
  built with vcpkg's `opencascade` port (features: freetype, rapidjson).
- FreeType, libpng, zlib, bzip2 and brotli DLLs, each under its own licence (`LICENSE-*.txt`).

## Building it yourself

With Visual Studio's "Desktop development with C++", CMake and vcpkg (`VCPKG_ROOT` set), run
`tools\StepToMesh\build.cmd` from a Developer Command Prompt. In Deskpad, Settings → Hardware tools →
"Install from a folder…" uses your own build instead of this download.
