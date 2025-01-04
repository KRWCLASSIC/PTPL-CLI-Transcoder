# `PTPL` CLI Transcoder

## Overview

The `PTPL` CLI Transcoder is a command-line tool designed to decode `.ptpl` files into `.xml` and encode `.xml` files back into `.ptpl` format. This tool is designed for working with PTPL files generated by the MCreator program.

## How it Works

### Decoding

When decoding, the tool:

1. Reads the `.ptpl` file as a gzip-compressed archive.
2. Extracts and decodes the base64-encoded XML content.
3. Formats the XML for readability.
4. Outputs the result to the console or saves it to a specified file.

### Encoding

When encoding, the tool:

1. Reads the XML file.
2. Encodes the content into base64.
3. Compresses the encoded data using gzip.
4. Outputs the result to a `.ptpl` file.

## Usage

Run the `transcoder.py` script with the following syntax:

```bash
python transcoder.py [-d | -e] <file_path> [--output <output_path>] [--verbose]
```

### Arguments

- `-d`, `--decode`: Decode a `.ptpl` file into XML.
- `-e`, `--encode`: Encode an XML file into `.ptpl` format.
- `<file_path>`: The path to the input file. Use a `.ptpl` file for decoding or an XML file for encoding.
- `--output`, `-o`: (Optional for decoding) Specify the path to save the output file. If not provided, decoded XML content is printed to the console, and encoded data defaults to `<input_name>.ptpl`.
- `--verbose`, `-v`: (Optional) Enable verbose output for detailed processing information.

## Examples

### Decode a `.ptpl` File

To decode a `.ptpl` file and print the result:

```bash
python transcoder.py -d example.ptpl
```

To decode a `.ptpl` file and save the XML to `output.xml`:

```bash
python transcoder.py -d example.ptpl -o output.xml
```

### Encode an XML File

To encode an XML file and save the `.ptpl` to `output.ptpl`:

```bash
python transcoder.py -e example.xml -o output.ptpl
```

## Notice

> **This tool is intended for use in the PTPL Editor project. PTPL files are generated by the MCreator program.**

## Requirements

- Python 3.x
- Required libraries:
  - `argparse`
  - `base64`
  - `gzip`
  - `lxml`
