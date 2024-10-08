Project SEKAI custom streaming CRIWARE HCA Decoder
---
# Installation
**NOTE:** It's recommended to use a virtual environment to install the package.
**NOTE:** **ONLY** Python **3.11** is supported.
- It's recommended to install the package from the source code
```bash
    git clone https://github.com/mos9527/sssekai_streaming_hca_decoder
    cd sssekai_streaming_hca_decoder
    pip install -r requirements.txt
```
- Alternatively, you can install the package directly from the repository
```bash
    pip uninstall sssekai_streaming_hca_decoder # If you have installed the package before and have issues
    pip -U install git+https://github.com/mos9527/sssekai_streaming_hca_decoder
```
# Usage
**NOTE:** You need to acquire the `libcri_ware_unity` binary from the game (or through other means since it's a part of the **full** CriWare SDK) to decode the HCA segments.

**NOTE:** This repo DOES NOT nor WILL BE able to provide the binary for you. DO NOT submit issues or PRs regarding this matter.

**NOTE:** Currently, binaries from Android (arm64) are supported. Windows (amd64), and Linux (amd64) binaries are also supported through FFI (ctypes, WIP).

**NOTE:** If you do happen to have the binary for Windows (amd64), please use the [windows-cpp-native](https://github.com/mos9527/sssekai_streaming_hca_decoder/tree/windows-cpp-native) branch instead.

- To decode the HCA segments
```bash
    python -m sssekai_streaming_hca_decoder --lib <path to your criware lib> --arch <optional. architecture of your lib. defaults to android-aarch64>  <input file or directory> <output WAV file>
```
The HCA segements will be decoded and merged into a single, very large (depending on the no. of hca segments provided) WAV file.

# Credits
- https://github.com/maiyao1988/ExAndroidNativeEmu
- https://github.com/mos9527/sssekai/blob/main/sssekai/fmt/rla.py
- [This discussion in the UnityPy discord](https://discord.com/channels/603359898507673630/1275510423772463125)
