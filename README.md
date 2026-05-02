# 📊 Daily Tracker — Google Apps Script Backend

A simple and powerful backend built with Google Apps Script to log daily productivity data into Google Sheets.

This project helps you track:

* 🎯 Focus tasks
* ✅ Daily routines
* 🧠 Discipline rules
* ⚡ Energy & mood
* 📝 Notes

All data is stored automatically in a Google Sheet, with optional email summaries and reminders.

---

## 🚀 Features

* 📥 Accepts data via HTTP POST (Web App)
* 📊 Automatically logs entries into Google Sheets
* 🧾 Creates sheet + headers on first run
* 🎨 Styled header row for readability
* 📧 Optional daily email summary
* ⏰ Daily reminder email trigger (10 PM)
* ✅ Lightweight and easy to deploy

---

## 🛠️ Tech Stack

* Google Apps Script
* Google Sheets
* MailApp (for email notifications)

---

## 📁 Project Structure

```
.--index.html #frontend
├── Code.gs   # Main Apps Script backend
└── README.md
```

---

## ⚙️ Setup Guide

### 1. Create Google Sheet

* Go to Google Sheets
* Create a new sheet
* Copy the Sheet ID from the URL

---

### 2. Setup Apps Script

1. Go to https://script.google.com
2. Create a new project
3. Paste the provided script into `Code.gs`
4. Save the project

---

### 3. Configure Script

Edit the config section:

```javascript
const SHEET_NAME = "Daily Log";
const NOTIFY_EMAIL = "your-email@example.com"; // optional
```

---

### 4. Deploy as Web App

1. Click **Deploy → New Deployment**
2. Select **Web App**
3. Set:

   * Execute as: **Me**
   * Access: **Anyone**
4. Click **Deploy**
5. Copy the **Web App URL**

---

## 📡 API Usage

### Endpoint

```
POST {WEB_APP_URL}
```

### Headers

```
Content-Type: application/json
```

### Sample Request Body

```json
{
  "date": "2026-05-02",
  "day": "Saturday",
  "focusTask": "Build tracker app",
  "routineDone": "Workout, Reading",
  "routineScore": "2/3",
  "rulesDone": "No distractions",
  "rulesScore": "1/2",
  "mood": "Energetic",
  "notes": "Good progress today"
}
```

### Sample Response

```json
{
  "status": "success"
}
```

---

## 🔍 Health Check

Open in browser:

```
GET {WEB_APP_URL}
```

Response:

```
✅ Daily Tracker backend is running!
```

---

## ⏰ Setup Daily Reminder

Run this function manually once in Apps Script:

```javascript
setupTrigger();
```

📌 Sends reminder email daily at **10 PM**

---

## 📧 Email Notifications

If `NOTIFY_EMAIL` is set:

* You’ll receive a summary email after each submission
* You’ll get a daily reminder at 10 PM

---

## 🧠 Data Stored in Sheet

| Column         | Description      |
| -------------- | ---------------- |
| Date           | Entry date       |
| Day            | Day name         |
| Focus Task     | Main task        |
| Routine Done   | Completed habits |
| Routine Score  | Habit score      |
| Rules Followed | Discipline rules |
| Rules Score    | Rule score       |
| Energy / Mood  | Mood level       |
| Notes          | Additional notes |
| Submitted At   | Timestamp        |

---

## 🔐 Permissions

The app requires:

* Access to Google Sheets
* Permission to send emails (if enabled)

---

## 💡 Future Improvements

* Prevent duplicate entries per day
* Dashboard with charts
* Mobile-friendly frontend
* Authentication system
* Weekly analytics summary

---

## 🤝 Contributing

Contributions are welcome!
Feel free to open issues or submit pull requests.

---

## 📜 License

This project is open-source and available under the MIT License.

---

## ⭐ Support

If you like this project:

* Star the repo ⭐
* Share it with others 🚀

---

**Stay consistent. Not perfect. 🔁**
