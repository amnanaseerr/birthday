# WhatsApp Birthday Wisher Bot 🎉

This Python script automatically sends birthday wishes to your WhatsApp contacts at midnight by reading from a `birthdays.json` file and using Selenium to automate WhatsApp Web.

## 💡 Features
- Reads contacts' birthdates from a JSON file.
- Sends a birthday wish at 12:00 AM automatically.
- Works through Chrome browser using your saved session.
- Fully automated using Selenium WebDriver.

---

## 🗂 Requirements

- Python 3.x
- Google Chrome installed
- Chrome WebDriver compatible with your Chrome version
- Selenium
- A `birthdays.json` file (see format below)

---

## 🧾 Setup Instructions

### 1. Install Selenium

```bash
pip install selenium
```

### 2. Download Chrome WebDriver

Download the Chrome WebDriver matching your Chrome browser version from:  
https://sites.google.com/a/chromium.org/chromedriver/downloads

Extract and place it somewhere, then note the full path.

### 3. Create `birthdays.json`

Place it in the same directory as your script. Example content:

```json
[
  {
    "name": "Alice Smith",
    "birth_month": "6",
    "birth_date": "15"
  },
  {
    "name": "Bob Johnson",
    "birth_month": "12",
    "birth_date": "25"
  }
]
```

### 4. Edit Script

Replace the following placeholders in the script:

```python
chropt.add_argument("user-data-dir=<LOCATION TO YOUR CHROME USER DATA>")
driver = webdriver.Chrome(executable_path ="<LOCATION TO CHROME WEBDRIVER>", options = chropt)
```

- `user-data-dir`: Path to your Chrome user profile (e.g., `C:/Users/YourName/AppData/Local/Google/Chrome/User Data`)
- `executable_path`: Full path to your `chromedriver.exe`

This ensures the bot opens your logged-in Chrome profile and doesn't ask you to log in to WhatsApp Web again.

---

## 🕒 How It Works

- The script continuously checks the current system time and date.
- Once the date matches any contact's birthday, it opens WhatsApp Web.
- Finds the contact using their exact name as in WhatsApp.
- Sends a wish like: `Happy Birthday Alice!!`

---

## 🚀 Running the Script

Make sure you're logged into WhatsApp Web in your Chrome profile. Then simply run:

```bash
python birthday_wisher.py
```

Let it run in the background; it will automatically trigger at the right time.

---

## ⚠️ Notes

- Do not close the Chrome window while the script is running.
- Ensure the contact names in `birthdays.json` match **exactly** with the names in your WhatsApp contacts.
- This script requires a stable internet connection.
- Avoid using this for spamming or automation of unrelated messages — it's intended for educational and personal use only.

---

## 📌 Disclaimer

This bot uses Selenium to automate browser actions. It's your responsibility to use this responsibly and not violate WhatsApp's terms of service.

---

## 📬 Sample Output

```
Script Running
['Alice Smith']
Message sent: Happy Birthday Alice!!
```



