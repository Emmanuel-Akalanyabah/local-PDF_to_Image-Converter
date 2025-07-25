# local-PDF_to_Image-Converter
Convert loaded PDF to an image locally on your PC 

A user-friendly PDF to image converter designed specifically for Jupyter Notebook environments. This tool converts PDF files into high-quality images with real-time progress display and preview capabilities.

**Features**

Convert PDF pages to JPEG, PNG, or TIFF formats

Real-time progress bar and status updates

First-page preview during conversion

Customizable DPI for image quality

Automatic output folder creation

Cross-platform support (Windows, Mac, Linux)

Threaded processing for faster conversions

**Requirements**

Python 3.6+
Jupyter Notebook

Poppler utilities (see installation instructions below)

**Installation**
1. Install Python Packages
pip install pdf2image pillow ipywidgets
pip install pdf2image pillow

3. Install Poppler Utilities
**Windows:**

Download Poppler from poppler-windows

https://github.com/oschwartz10612/poppler-windows/releases/

Extract the ZIP file

Set the path to the bin directory in the configuration section

**Linux (Ubuntu/Debian):**


sudo apt-get install poppler-utils

**macOS**:

brew install poppler

**Usage**

Copy the entire code block into a Jupyter Notebook cell

Configure the settings in the configuration section:

PDF_PATH: Path to your PDF file

POPPLER_PATH: Path to Poppler binaries (Windows only)

dpi: Image quality (200 is standard, 300 for high-res)

fmt: Output format ('jpeg', 'png', or 'tiff')

Run the cell to start conversion

**Example Configuration**

**Configuration section - SET THESE VALUES BEFORE RUNNING**

PDF_PATH = r"C:\Users\huy\Desktop\UCC CDRSRM Certificate EMMANUEL AKALANYABAH.pdf"
POPPLER_PATH = r"C:\Users\huy\Desktop\poppler-24.08.0\Library\bin"  # Windows users

**POPPLER_PATH = None  # For Linux/Mac users**

**How It Works**
Preparation:

Creates an output folder (default: pdf_images_output)

Validates the output format

Initializes progress widgets

**Conversion:**

Processes PDF pages using multi-threading

Shows real-time progress (percentage and page count)

Displays first-page preview during conversion

**Output:**

Saves each page as separate image file

Files are named: [pdfname]_page_[number].[format]

Shows completion message with output location

**Troubleshooting**
Common Issues
Poppler not found:

**Windows:** 
Ensure correct path in POPPLER_PATH

**Linux/Mac:**
Verify installation with pdftoppm -h

**File not found:**

Use raw strings for paths: r"C:\path\to\file.pdf"

Check file exists in the specified location

**Permission errors:**

Run Jupyter Notebook as administrator (Windows)

Ensure write permissions to output folder

**Output format error:**

Use only 'jpeg', 'png', or 'tiff'

Format must be in lowercase

**Increasing Performance**
For large PDFs, increase thread count:

python
images = convert_from_path(..., thread_count=8)
For better quality, increase DPI (300-600)

For faster processing, use JPEG format instead of PNG

**Output Structure**
After conversion, you'll find images organized as:

text
pdf_images_output/
├── yourfile_page_1.png
├── yourfile_page_2.png
└── yourfile_page_3.png


**Note:** This tool is designed for Jupyter Notebook environments. For command-line usage, consider using the pdf2image package directly with proper Poppler configuration.



