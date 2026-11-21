[README.md](https://github.com/user-attachments/files/35217915/README.md)
# Nexora ASI1-30B

**A private, local AI assistant for Windows.** Nexora ASI1-30B starts the model, launches its web chat, and keeps inference on the user's computer.

## Download and run

Download every part attached to the latest GitHub Release, extract the complete `Nexora-ASI1-30B` folder, and double-click `Nexora-ASI1-30B.exe`. Keep the `model` and `runtime` folders beside the executable. The model weights are included in the release package; no separate model download is needed.

The app opens the web chat at `http://127.0.0.1:8080` after the model is ready. If that address is already in use, stop the other local model server and select **Start model** again. Closing the launcher stops its model server.

## System requirements

**Minimum**

- Windows 10 or 11, 64-bit
- NVIDIA GPU with at least 8 GB of CUDA VRAM
- 32 GB system RAM
- Compatible NVIDIA graphics driver
- 40 GB free disk space for download and extraction
- Expected generation speed: approximately 6–10 tokens per second

**Recommended**

- NVIDIA GPU with 16 GB of CUDA VRAM
- 32 GB system RAM: approximately 20–30 tokens per second
- 64 GB system RAM: approximately 60–70 tokens per second
- Compatible NVIDIA graphics driver

The performance figures are indicative estimates supplied by the project maintainer, not guaranteed benchmark results. Actual speed depends on the exact GPU and its memory bandwidth, system memory, background load, and prompt length. More system RAM alone does not guarantee higher speed.

The ready-to-run release includes llama.cpp and the CUDA runtime libraries used by the packaged server. A compatible NVIDIA driver is still required. Python and the CUDA Toolkit are only needed when building the app from source; end users do not need to install them separately.

## What is included

- Nexora-branded Windows launcher and local web chat
- Automatic GPU layer fitting, with a 500 MiB VRAM margin
- 12,288-token context and single-user serving
- Bundled model weights, llama.cpp server, and CUDA runtime libraries
- Model and third-party license notices

The server listens on loopback (`127.0.0.1`) so it is available to this computer only by default.

## GitHub release downloads

The source repository excludes the large model and generated runtime from normal Git commits. Ready-to-run downloads are published as GitHub Release assets. GitHub limits each release asset to less than 2 GiB, so the complete package may be supplied as multiple compressed parts. Download all parts before extracting them.

## Building from source

For contributors: use Windows, Python 3.10 or later, a CUDA-enabled llama.cpp Windows build, and CUDA Toolkit 12.4. Put the model file at `model\Nexora-ASI1-30B.gguf`, then run in PowerShell:

```powershell
.\build_windows.ps1
```

The script creates `release\Nexora-ASI1-30B`. Keep that whole folder together. See `requirements-build.txt` for the build dependency.

## Model and acknowledgments

Nexora ASI1-30B is a branded application assembled and published by **Syed Abdul Moiz**; its underlying weights are not newly trained by this project. The bundled weights are based on **Qwen3-30B-A3B**, created by Alibaba Cloud's Qwen team and distributed under the Apache License 2.0. The GGUF conversion and llama.cpp runtime are third-party components. Their notices are included with the release.

## Copyright and license

Copyright © 2026 **Syed Abdul Moiz**. The launcher source is licensed under the MIT License in `LICENSE`. The model weights, llama.cpp, and CUDA runtime retain their respective upstream licenses.
