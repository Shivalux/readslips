# ReadSlip

Lightweight OCR slip processing tool for extracting data from Krungthai slips in images and exporting the results to CSV or optionally XLSX.

---

## 📝 Description

ReadSlip is a Python-based OCR [(Optical Character Recognition)](https://www.ibm.com/think/topics/optical-character-recognition) tool that processes [Krungthai bank slip images](slip_sample.jpg) from JPG-format or JPEG-format images from one or more file(s) or directory(ies). It extracts key data fields, structures them into a table (Pandas DataFrame), and exports to a `.csv` file by default. Optionally, you can export to `.xlsx`

### Features
- Supports Krungthai slip format only (bank slip template/layout)
- Processes JPG / JPEG image files
- Recognizes both **Thai** and **English** text
- Default export format: `.csv`
- Optional export format: `.xlsx`

## 💻 Installation

### Requirments
- Python 3.x  
- `pip`

### Steps

1. Clone the repository:
```bash
$ git clone https://github.com/Shivalux/readslips.git
$ cd readslips
```

2. (Optional but recommended) Create and activate a virtual environment:
```bash
# MacOS / Linux
$ python3 -m venv <virturl_environment_path>
$ source <virturl_environment_path>/bin/activate

# Window
$ python -m venv <virturl_environment_path>
$  .\venv\Scripts\activate
```

3. Install dependencies:
```bash
$ pip install -r requirment.tst
```

4. Update the shebang (first line) in `readslip` script to point to your Python interpreter path, e.g.:

```py
#!./venv/bin/python3 <---- update this line.

import easyocr
import argparse
import os
import cv2
...
```
You can find the correct path via:
Mac/Linux
```bash
$ which python3    # MacOS/Linux
$ where python     # Window
```

5. (If you activated virtual environment) deactivate when done:
```bash
$ deactivate
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
* if `--filename` option is given, the `--xlsx` option will be ignored.
* if `--append` option is used, the option `--open` and `--filename` are ignored to avoid conflicts.

## Input
* Images of Krungthai bank slips in `JPG` or `JPEG` format.
* One or more file paths or directories.

## Output
* Default: `.csv` file with structured data extracted from the slips.
* Optional: `.xlsx` file if --xlsx flag used (and not overridden).
* Output fields may include: date, time, amount, company, noted, filename(hyperlink)

## Example
### Command
```bash
$ ./readslips -x -f slips_data .
```
### What happens
* Processes all `.jpg` / `.jpeg` images inside `current directory`.
* Recognise text from each image.
* Exports the extracted data into slips_data.xlsx

### result
```csv
date,time,amount,company,noted,filename
05/08/2568,15:42,"1,000.00 บาท time 0.0d",AI,EasyPass,"=HYPERLINK(""file:///Users/shivarakii/Documents/payment_orc/slip_sample.jpg"", ""slip_sample.jpg"")"
```



## 👥 Authors & Acknowledments

Created by @Shivalux

## ⚖️License
This project is licensed under the MIT License.  
See the [LICENSE](LICENSE) file for more information.
