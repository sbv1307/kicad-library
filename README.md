# Local KiCad library
This repository stores common [symbols](symbols), [footprints](footprins), [3D models](3d_models) and [datasheets](datasheets) used in KiCad projects

## To include the libraries in a KiCad project, use [git submodule](https://git-scm.com/docs/git-submodule).
###### Note: The following assume that KiCad project files are located in a folder called "hardware" in the following filestructure. 

../project name/hardware

Exanple:
```Bash
git submodule add <repository> hardware/library
```
## To update the local KiCad library:

Exanple:
```Bash
git add submodule update --remote hardware/library
```

