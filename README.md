# Learning WASM

Web Assembly is a technology to run several programming language directly on a browser.

https://developer.mozilla.org/en-US/docs/WebAssembly/C_to_wasm

# Guide

Assuming that you already download and install [Emscripten](https://emscripten.org/docs/getting_started/downloads.html)

If `emsdk` command doesn't work, write this instead:

```bash
# Powershell
./emsdk.ps1 install latest

# CMD
./emsdk.bat install latest
```

### Add `emsdk` and `emcc` command to environment variables:

1. Go to start menu, search for Environment Variable. Click on `Edit the system environment variables`

2. Click on `Environment Variables...`

3. On system variables, search for Path and `Edit...`

4. Click `New`, then copy the `emsdk` path

5. Now the command should work on any directory

### Compiling code to HTML, JS, WASM

Activate the `emsdk`:

```bash
emsdk activate latest
```

Compile the source code to HTML:

```bash
emcc <FILE_NAME>.c -o <FILE_NAME>.html
```

The command will generate an HTML, JS, and a WASM file.

You can run the HTML via VSCode [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)

### Using custom HTML template

```bash
emcc -o hello2.html hello2.c -O3 --shell-file html_template/shell_minimal.html
```