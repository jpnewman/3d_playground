
# Vulkan Multisampling example - VSCode

## References

- <https://vulkan-tutorial.com/Multisampling>

## Setup

### Install GLM

```
brew install glm
```

> Update ```/usr/local/Cellar/glm/0.9.9.4/include``` in file ```CMakelists.txt``` if needed.

### Install stb

```
git clone git@github.com:nothings/stb.git /usr/local/share/stb
```

> Update ```/usr/local/share/stb``` in file ```CMakelists.txt``` if needed.

### Install tinyobjloader

```
git clone git@github.com:syoyo/tinyobjloader.git /usr/local/share/tinyobjloader
```

> Update ```/usr/local/share/tinyobjloader``` in file ```CMakelists.txt``` if needed.

## Add Resources

Download the following resources: -

|Resource|Download Folder|Note|
|---|---|---|
|<https://github.com/Overv/VulkanTutorial/blob/master/resources/chalet.jpg>|```textures```||
|<https://github.com/Overv/VulkanTutorial/blob/master/resources/chalet.obj.zip>|```models```|Extract ZIP file|

## Open

Open VSCode in this folder: -

```bash
code .
```

## Build Release

```bash
mkdir -p Release
cd Release

cmake -DCMAKE_BUILD_TYPE=Release ..
make
```

## Run

```bash
./Multisampling
```
