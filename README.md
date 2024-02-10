# Local KiCad library
This repository stores common [symbols](symbols), [footprints](footprins), [3D models](3d_models) and [datasheets](datasheets) used in KiCad projects under https://github.com/sbv1307


## To include the libraries in a KiCad project, using [git submodule](https://git-scm.com/docs/git-submodule) use:
###### Note: The following assume that KiCad project files are located in a folder called "hardware" in the following filestructure. ../project name/Hardware
```Bash
git submodule add https://github.com/sbv1307/kicad-library.git Hardware/library
```

Then add the specific symbol library in KiCad by:<br> KiCad -> Preferences -> Manage Symbol Libraries -> Project spedific Libraries.

##### Note: Nickname (Take mname form library name e.g. Local MCU Modues. <br>Libarary path: Just select the symbol library downloaded from github. ${KIPRJMOD} will automatically substitude the path.

## To update the local KiCad library i a project use:
```Bash
git submodule update --remote Hardware/library
```

# To modify Libraries (checklist):

1 Open KiCad project: ..\Projects\kicad-library\kicad-library\kicad-library.kicad_pro
###### Note:&emsp; This project is an empty project and projectfiles will not be tracked by GIT. <br>&emsp;&emsp;&emsp;&emsp;Remember! in Preferences -> Configure Path... insert: <br>&emsp;&emsp;&emsp;&emsp;KICAD_LOCAL_SYMBOL_DIR = <br>&emsp;&emsp;&emsp;&emsp;C:\Users\Steen\Documents\3 - My OTHER  documents\Projects\kicad-library\symbols <br>&emsp;&emsp;&emsp;&emsp;and <br>&emsp;&emsp;&emsp;&emsp;KICAD_LOCAL_DATASHEETS =<br>&emsp;&emsp;&emsp;&emsp;C:\Users\Steen\Documents\3 - My OTHER  documents\Projects\kicad-library\datasheets

2 Make modifications to the Library and exit KiCad

3 Start GIT Bash i ..\Projects\kicad-library

4 Verify changed and tracked files: git status --untracked-files (Alias = gs)

5 Add un-vanted tracked files to .gitignore: notepad .gitignore

6 Add and commit change / tracked files to git: git add . && git commit -m "< Commit comment >" (Alias = gc "< Commit comment >")

7 Update GitHub: git push origin master


Symbols will in generel have the following set of properti fields:
Name | Value | Show
---|---|---
Reference | A, C, D, J, JP, Q, R, RN, SW or U | [V]
Value | < Component value > | [V]
Footprint | < Reference to footprint[^1] > | [V] 
Datasheet | < Link to Datasheet (Taken form prviders website e.g. [JLCPCB](https://jlcpcb.com/) )> | [V]
Mount Option | F.Mount / B.Mount[^2] | [  ]
Description | < Text taken from providers website > | [ ]
LibPart | <Refenence to symbol lib, where the symbol is located>  | [ ]
JLCBCB Part /  Digi-Key Part| < Link to providers website > | [ ]
JLCPCB Part # /Digi-Key Part # | < Providers part- / ordernumber > | [  ]
JLCPCB Basic or Extended / Digi-Key Delstatus| Basic part / Extended part / Aktiv / Forældet | [  ]
Manufacturer | < Manufacture name, taken from providers website > | [  ]
MFR. Part # | < Manufactures part- / ordernumber > | [  ]
Category | Resistors, Capasitors... ( taken from providers website )  | [  ]
Famely | Chip Resistor - Surface Mount, Ceramic Capacitors... ( taken from providers website ) | [  ]
Excluded from BOM | YES / NO ( Generel rule: NO, if it's a [JLCPCB](https://jlcpcb.com/) basic component) | [  ]
Pinout | < Link to printout or other doc. ( Used for e.g. development boards line arduino )> | [  ]

###### [^1]: Footprint for components, which can be mounted on both sides, the the name is expected to include: (F.Mount) / (B.Mount). 
###### [^2]: Frontside / Backside mount. For components which can be mounted on both sides e.g. screw terminals.