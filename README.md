# Keylogger Project

## Objective

This project involves building a Python-based keylogger to record keyboard inputs for educational purposes and to demonstrate ethical hacking techniques. The goal is to understand how keyloggers operate, learn the principles of monitoring input devices, and emphasize the importance of securing systems against such threats.

> **Note:** This project is strictly for educational use and ethical learning. Do not deploy or use the keylogger for malicious purposes.

### Skills Learned

- Proficiency in Python programming for interacting with operating system APIs.
- Understanding of keylogging mechanisms and input capture techniques.
- Hands-on experience with libraries like `pynput` for monitoring keyboard inputs.
- Knowledge of secure data handling and encryption of sensitive logs.
- Awareness of ethical hacking principles and system protection strategies.

### Tools Used

- Python 3 for development.
- Libraries:
  - `pynput` for capturing keyboard inputs.
  - `smtplib` for sending logs via email (optional).
  - `os` and `time` for file management and scheduling.
- Virtual Machine (e.g., VirtualBox) for safe testing.

---

## Steps

1. **Set Up the Environment:**
   - Installed Python 3 and required libraries (`pynput`, `smtplib`).
   - Created a virtual environment to manage dependencies.

2. **Capture Keyboard Inputs:**
   - Used the `pynput` library to monitor and record keyboard inputs.
   - Stored logs in a secure text file or encrypted format.

3. **Encrypt and Store Logs:**
   - Implemented basic encryption using the `cryptography` library to secure logged data.
   - Ensured logs were stored in an inaccessible or hidden directory for demonstration purposes.

4. **Optional: Send Logs via Email:**
   - Configured the `smtplib` library to send encrypted logs to a preconfigured email address securely.
   - Utilized environment variables for storing sensitive email credentials.

5. **Implement Stealth Mode:**
   - Ensured the script runs silently in the background without alerting the user.
   - Set up auto-start functionality on the test environment for educational purposes.

6. **Test and Debug:**
   - Tested the keylogger on a virtual machine to ensure it captures inputs accurately.
   - Validated encryption and email delivery functionality.

7. **Document Ethical Usage:**
   - Clearly documented the ethical guidelines and educational intent of the project.

---

## Example Code

Here’s a basic implementation for capturing keystrokes:

```python
from pynput.keyboard import Listener

# Log file to store captured keystrokes
log_file = "keylog.txt"

# Function to log keys
def log_key(key):
    with open(log_file, "a") as f:
        key_str = str(key).replace("'", "")
        f.write(key_str + "\n")

# Start the listener
with Listener(on_press=log_key) as listener:
    listener.join()