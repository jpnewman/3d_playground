
# Vulkan Development on MacOS

## Main References

- <https://www.youtube.com/watch?v=oxVPdnie8sA>
- <https://docs.google.com/document/d/1-coOfxxubUEaC-JOn_gaWk_vYjHtuUL4ISr5_EKlg6I/>

## Other References

- <https://vulkan.lunarg.com/doc/sdk/1.1.101.0/mac/getting_started.html>
- <https://vulkan-tutorial.com>
- <https://gist.github.com/vlsh/a0d191701cb48f157b05be7f74d79396>

## Install Xcode

Install Xcode and run the following command: -

```bash
xcode-select --install
```

## Install CMake, GLFW, and GLM

```bash
brew install cmake
brew install glfw --HEAD

brew install glm
```

## Install gdb

```bash
brew install gdb
```

CodeSign gdb: -

- <https://gist.github.com/danisfermi/17d6c0078a2fd4c6ee818c954d2de13c>

CodeSign gdb, other references: -

- <https://gist.github.com/hlissner/898b7dfc0a3b63824a70e15cd0180154>
- <https://stackoverflow.com/questions/18423124/please-check-gdb-is-codesigned-see-taskgated8-how-to-get-gdb-installed-w>
- <https://medium.com/@royalstream/how-to-install-and-codesign-gdb-on-os-x-el-capitan-aab3d1172e95>

## Install Vulkan SDK

1. Download from <https://vulkan.lunarg.com/sdk/home#mac>
2. Extract to ```/Users/Shared```.  
   *e.g.* ```/Users/Shared/vulkansdk-macos-1.1.101.0```
3. Link Vulkan SDK: -

    ```bash
    ln -sn /Users/Shared/vulkansdk-macos-1.1.101.0 /Users/Shared/vulkansdk
    ```

> If extracted path changes and not linked to ```/Users/Shared/vulkansdk``` also update paths in VSCode ```launch.json``` file.

## Setup

Add the following to file ```~/.zshrc``` and source it: -

```bash
# Vulkan
export VULKAN_ROOT_LOCATON="/Users/Shared"
export VULKAN_SDK_VERSION="1.1.101.0"
export VULKAN_SDK="$VULKAN_ROOT_LOCATON/vulkansdk-macos-$VULKAN_SDK_VERSION/macOS"
export DYLD_LIBRARY_PATH="$VULKAN_SDK/lib"
export VK_ICD_FILENAMES="$VULKAN_SDK/etc/vulkan/icd.d/MoltenVK_icd.json"
export VK_LAYER_PATH="$VULKAN_SDK/etc/vulkan/explicit_layer.d"
export PATH="/usr/local/opt/python/libexec/bin:$VULKAN_SDK/bin:$PATH"
```

> If Vulkan SDK was linked to ```/Users/Shared/vulkansdk``` the following can be added instead: -

```bash
# Vulkan
export VULKAN_SDK="/Users/Shared/vulkansdk/macOS"
export DYLD_LIBRARY_PATH="$VULKAN_SDK/lib"
export VK_ICD_FILENAMES="$VULKAN_SDK/etc/vulkan/icd.d/MoltenVK_icd.json"
export VK_LAYER_PATH="$VULKAN_SDK/etc/vulkan/explicit_layer.d"
export PATH="/usr/local/opt/python/libexec/bin:$VULKAN_SDK/bin:$PATH"
```
