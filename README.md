# XORer - XOR Encryption/Decryption Tool

A simple command-line tool for encrypting and decrypting files or strings using the XOR cipher.

## Overview

XORer performs XOR cipher operations on files or text strings. The XOR cipher combines each byte of data with a key byte using the exclusive OR operation. Since XORing twice with the same key reverses the operation, the same tool handles both encryption and decryption.

## Features

- Encrypt and decrypt files or text strings
- Support for binary files (images, executables, etc.)
- Multiple output formats (raw binary, Python byte string, C array)
- Configurable encryption keys (string or file-based)
- Verbose mode for debugging
- Pipe-friendly output

## Installation

```bash
# Clone the repository
git clone https://github.com/flexbusterman/xorer.git
cd xorer

# Make the script executable (Unix/Linux/macOS)
chmod +x xorer.py
```

## Usage

```bash
python xorer.py [-h, --help] -i INPUT [-o, --output [OUTPUT]] [-k, --key [KEY]] [-f, --format [{raw,python,c}]] [-v, --version] [-V, --verbose]
```

### Required Arguments

- `-i, --input`: Input file path or string to encrypt/decrypt

### Optional Arguments

- `-h, --help`: Prints help and quit
- `-o, --output`: Output file path (prints to stdout if not specified)
- `-k, --key`: Encryption key (string or file path). Default: "secret"
- `-f, --format`: Output array format - `raw` (default), `python`, or `c`
- `-V, --verbose`: Enable verbose output for debugging
- `-v, --version`: Show version information and quit

## Examples

```bash
# Encrypt a file to output file using key in file with verbose output
python xorer.py -i message.txt -o encrypted.bin -k mykeyfile -V

# Decrypt a file and display as text
python xorer.py -i encrypted.bin -k "mysecretkeystring"

# Simple encryption and decryption using default key, then reversing encryption and printing to stout
python xorer.py -i "My message" -o cipherfile
python xorer.py -i cipherfile
```

## Security Note

**Important**: XOR cipher is not cryptographically secure for real-world encryption needs. It's vulnerable to known-plaintext attacks and other cryptanalysis techniques. This tool is intended for:
- Educational purposes
- Simple obfuscation
- CTF challenges
- Learning about encryption basics

For production use, employ modern encryption standards like AES.

## Output Formats

- **raw**: Binary output suitable for files or piping
- **python**: Python byte string format (`b"\x48\x65..."`)
- **c**: C-style array declaration (`unsigned char buf[] = { 0x48, 0x65, ... };`)

## Requirements

- Python 3.10 or higher (uses match-case statements)

## Acknowledgments

AI tools were used in the development of this software and this README document.
