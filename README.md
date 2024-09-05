# Kilo Text Editor

Kilo is a simple, lightweight text editor implemented in C. It operates in the terminal and supports basic text editing features such as navigation, saving files, and syntax highlighting.

This implementation is heavily inspired by the Kilo text editor tutorial by [snaptoken](https://viewsourcecode.org/snaptoken/kilo/index.html).

## Features

- **Basic text editing**: Navigate and modify text files using the arrow keys, and save your work with `Ctrl-S`.
- **Syntax highlighting**: Syntax highlighting is supported for C, C++, and header files.
- **File operations**: Open and edit existing files, create new ones, and save changes with ease.
- **Customizable tab width**: Default tab stop is set to 8 characters.
- **Raw mode**: Uses raw input mode for terminal interaction, making it fast and responsive.
- **Search functionality**: Easily search for text using `Ctrl-G`.

## Keybindings

- **Ctrl-Q**: Quit the editor (asks for confirmation if the file is unsaved).
- **Ctrl-S**: Save the current file.
- **Ctrl-G**: Search within the file.
- **Ctrl-A/Home**: Move the cursor to the beginning of the line.
- **Ctrl-E/End**: Move the cursor to the end of the line.
- **Ctrl-B/Left Arrow**: Move the cursor left.
- **Ctrl-F/Right Arrow**: Move the cursor right.
- **Ctrl-P/Up Arrow**: Move the cursor up.
- **Ctrl-N/Down Arrow**: Move the cursor down.
- **Ctrl-H/Backspace**: Delete the character before the cursor.
- **Delete**: Delete the character at the cursor.

## Dependencies

This program requires a Unix-like environment (Linux/macOS) to work properly. It uses standard C libraries and system calls for terminal control.

## Compilation

To compile Kilo, run the following command in the source directory:

```sh
make
```

This will generate an executable named `kilo`.

## Usage

To run Kilo, use the following command:

```sh
./kilo <filename>
```

Where `<filename>` is the file you want to open or create.

For example, to edit a file called `example.txt`, run:

```sh
./kilo example.txt
```

## Terminal Input Mode

Kilo uses raw mode to capture keystrokes directly from the terminal without buffering, which allows for real-time interaction. It sets various terminal attributes using `termios` to disable canonical mode, echo, and signal generation.

## Syntax Highlighting

The editor provides basic syntax highlighting for C and C++ files. The following syntax elements are highlighted:

- Keywords (`if`, `else`, `return`, etc.)
- Single-line comments (`//`)
- Multi-line comments (`/* */`)
- Strings (`"string"`, `'char'`)
- Numbers (including hexadecimal)

### Customization

To add support for other programming languages, modify the `HLDB` array in the `syntax.c` file. You can define new file extensions and keywords for syntax highlighting.

## Exit Warning

When you attempt to exit the editor with unsaved changes, Kilo will prompt a confirmation message. You need to press `Ctrl-Q` two times to quit without saving.