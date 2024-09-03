
# Login Automation

Automate the login process to avoid manual entry of usernames and passwords.

## Installation

Install the `pyautogui` library by running the following command:

```bash
pip install pyautogui
```

## Create the Python Script

Create a new file called `login_automation.py` and copy the following code:

```python
import pyautogui
import time

# Define your login credentials for multiple accounts
accounts = {
    "Gmail": ("gmailUsername", "gmailPassword"),
    "Work Portal": ("workUsername", "workPassword"),
    "GitHub": ("githubUsername", "githubPassword")
}

def select_account():
    print("Select the account to log in:")
    for i, account in enumerate(accounts, start=1):
        print(f"{i}. {account}")
    choice = int(input("Enter the number of the account: "))
    return list(accounts.items())[choice - 1]

def login(username, password):
    # Wait a few seconds to switch to the login page
    time.sleep(3)  # Adjust as needed to give you time to open the login page

    # Type username
    pyautogui.typewrite(username)
    pyautogui.press('tab')

    # Type password
    pyautogui.typewrite(password)
    pyautogui.press('enter')

if __name__ == "__main__":
    account_name, credentials = select_account()
    print(f"Logging into {account_name}...")
    login(*credentials)
```

## Running the Script

Run the script using the command:

```bash
python login_automation.py
```

## Create a Shortcut to Run the Script

To run the Python file with a shortcut, follow these steps:

1. **Create a Batch File**:
   - Create a new file on your desktop or in a folder with a `.bat` extension, such as `run_login.bat`.
   - Add the following content to the file:

     ```batch
     @echo off
     REM Runs the Python script to automate login
     start "" "python" "C:\path\to\your\script\login_automation.py"
     exit
     ```

   - Replace `C:\path\to\your\script\` with the actual path to your `login_automation.py` script.

2. **Create a Shortcut**:
   - Right-click on the batch file (`run_login.bat`) and select **Create Shortcut**.

3. **Assign a Keyboard Shortcut**:
   - Right-click on the newly created shortcut and select **Properties**.
   - In the **Shortcut** tab, click on the **Shortcut key** field.
   - Press the keyboard combination you want to use, such as `Ctrl + Alt + L`. Windows will automatically assign the shortcut.
   - Click **Apply** and then **OK**.

### Note:
After running the Python code, make sure to click once on the first input field where you want the username to be entered.

---
