# ReadSlip

ReadSlip is a lightweight ORC (Object-Relational Capture) slip processing tool for scanning and extracting data 
from JPG-format or JPEG-format images located in the provided file(s) or directory path(s).
The extracted information  will be automatically converted into a DataFrame and exported as a .csv file
by default. Optionally, it can also be saved as .xlsx. writing in Python.

---

## 📝 Description

Let people know what your project can do specifically. Provide context and add a link to any reference visitors might be unfamiliar with. A list of Features or a Background subsection can also be added here. If there are alternatives to your project, this is a good place to list differentiating factors.

### Features

-
-
-
-

## 💻 Installation

### Requirment



### Steps

clone the git repo 
```bash
$ git clone https://github.com/Shivalux/readslips.git
```

(optionnal) create the virturl environment and activate tht virturl environment
Mac/Linux
```bash
# Mac/Linux
$ python3 -m venv <virturl_environment_path>
$ source <virturl_environment_path>/bin/activate

# Window
$ python -m venv <virturl_environment_path>
$ python -m venv <virturl_environment_path>\Scripts\activate.bat
```

install requirments.txt
```bash
$ pip install -r requirment.tst
```

fix the shibang path on the top of readslip file with your your python path check by

readslip
```py
#!./venv/bin/python3 <---- change this line with your python interperter path

import easyocr
import argparse
import os
import cv2
...
```
check by
Mac/Linux
```bash
# Mac/Linux
$ where python3

# Window
$ where python
```

Deactivate the vitrual environ ment 
```bash
deactivate
```
---
## 🚀 Usage
```bash
readslips [-h] [-v] [-x] [-f FILE_NAME] [-o FILE_NAME] [-a FILE_NAME] [PATHS ...]
```
### Arguments
`[PATHS...]`         One or more file paths or directories containing slip images.

### Option
Option | Description |
-------|-------------|
`-h`, `--help` |  Show this help message and exit |
`-v`, `--version` | Show the current version of the program and exit |
`-x`, `--xlsx` | Export the result as an .xlsx file. When the --filename option is specified, this option will be ignored |
`-f FILE_NAME`, `--filename FILE_NAME` | Specify the name of the output file to export results |
`-o FILE_NAME`, `--open FILE_NAME` |  Specify a file to open and load existing data |
`-a FILE_NAME`, `--append FILE_NAME` | Append new data to an existing file |

### Noted 
* When the `--filename` option is specified, the `--xlsx` option will be ignored.
* When `--append` option is used, both `--open` and `--filename` will be ignored.

## Input
## Output
## Example
---
## 👥 Authors & Acknowledments

Created by @Shivalux
---
## ⚖️License
This project is licensed under the MIT License.  
See the [LICENSE](LICENSE) file for more information.
