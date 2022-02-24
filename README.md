# Local KiCad library
This repository stores common [symbols](symbols), [footprints](footprins), [3D models](3d_models) and [datasheets](datasheets) used in KiCad projects

## To include the libraries in a KiCad project, use [git submodule](https://git-scm.com/docs/git-submodule) use:
###### Note: The following assume that KiCad project files are located in a folder called "hardware" in the following filestructure. ../project name/Hardware
```Bash
git submodule add https://github.com/sbv1307/kicad-library.git Hardware/library
```
## To update the local KiCad library i a project use:
```Bash
git submodule update --remote Hardware/library
```

# To modify Libraries (checklist):

1 Open KiCad project: ..\Projects\kicad-library\kicad-library\kicad-library.kicad_pro
###### Note: This project is an empty project and projectfiles will not be tracked by GIT 

2 Make modifications to the Library and exit KiCad

3 Start GIT Bash i ..\Projects\kicad-library

4 Verify changed and tracked files: git status --untracked-files (Alias = gs)

5 Add un-vanted tracked files to .gitignore: notepad .gitignore

6 Add and commit change / tracked files to git: git add . && git commit -m "< Commit comment >" (Alias = gc "< Commit comment >")

7 Update GitHub: git push origin master



