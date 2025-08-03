# Python-Keylogger
This is a simple Python script that logs keyboard activity using the `pynput` library. It records keystrokes and writes them to a local text file (`keyfile.txt`). This tool is designed **solely for educational and ethical testing purposes**, such as understanding how keyloggers work and how to detect or prevent them.

DISCLAIMER

> **This project is intended strictly for educational use.**  
> Do **not** use this software on any system without **explicit written permission** from the owner.

 How It Works
- Listens to all keyboard input using the `pynput.keyboard` module.
- Logs printable characters to `keyfile.txt`.
- Records special keys like `Enter`, `Tab`, `Shift` as `[Key.enter]`, `[Key.shift]`, etc.
- Stops recording when the **Escape** key is pressed.

from pynput import keyboard 


