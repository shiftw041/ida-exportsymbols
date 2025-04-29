# ida-exportsymbols

IDA plugin to export symbols from IDA database to ELF file or plaintext.

Original repository added support for IDA 7.4+ (Python 3.8) and tested on IDA Pro 7.7, IDA Pro 8.3. But IDAPython 9.0 has modified some API functions, so older plugins are not compatible with the new version. This fork has been adapted to IDA Pro 9.1 and has fixed some bugs. It has been tested and works properly on Version 9.1.250226 Windows x64 (64-bit address size).

Idea taken from https://github.com/danigargu/syms2elf but written from scratch.

## Installation

Copy all files from plugin durectory to IDA plugin directory.

## Usage

- Open and parse any ELF file. Then click "Edit->Plugins->Export symbols to file".

- Select segments that you would like to export symbols such as `.text` / `.data` / `.bss`. 

- To quickly select custom segments, use `Select custom` button. You can modify default custom segments in the first line of `exportsymbols.py` :

    ```
    USER_SEGMENTS = ['.text', '.data', '.bss', '.rodata']
    ```

- Change export symbols types and options as you want. 

- In file dialog, You can save file as plaintext or a copy of input ELF file with IDA symbols imported by selecting file type.

There is a bug that exporting `extern` segment **might fail** for unknown reason. Make sure to 
backup original file and use at your own risk.


## Difference from original

- Updated idapython api
- Redesigned dialog using layouts for better flexibility instead of hard-coded setGeometry.
- More convenient selection buttons
- Fix some bugs.

## Screenshot

![picture 0](/img/fork_main.png)  

Original Screenshot:

![Main dialog](/img/main.png)
