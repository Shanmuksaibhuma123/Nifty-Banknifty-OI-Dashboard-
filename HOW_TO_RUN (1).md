# ⬡ OI Terminal v3.0 — How to Run This Project

Hi! Follow these simple steps one by one. No experience needed. 🙂

---

## What You Need Before Starting

- A computer with **Python installed**
  - Don't have Python? Download it free from 👉 https://www.python.org/downloads/
  - ✅ During install — check the box **"Add Python to PATH"**
- A **Zerodha account** (for live market data)
- Internet connection

---

## Step 1 — Download the Project

1. Click the green **"Code"** button on this GitHub page
2. Click **"Download ZIP"**
3. Extract (unzip) the folder on your Desktop

---

## Step 2 — Get Your Zerodha API Keys

This project uses Zerodha to fetch live market data. You need a free API key.

1. Go to 👉 https://developers.kite.trade/
2. Login with your Zerodha username & password
3. Click **"Create new app"**
4. Fill in any app name (example: `OI Dashboard`)
5. In the **Redirect URL** box, type exactly:
   ```
   http://127.0.0.1:5000/callback
   ```
6. Click Save → You will get an **API Key** and **API Secret**
7. Copy both — you will need them in the next step

---

## Step 3 — Add Your API Keys to the Project

1. Open the project folder
2. Open the file called **`app.py`** in Notepad (or any text editor)
3. Find these 2 lines near the top:
   ```
   API_KEY    = "YOUR_API_KEY_HERE"
   API_SECRET = "YOUR_API_SECRET_HERE"
   ```
4. Replace `YOUR_API_KEY_HERE` with your actual API Key
5. Replace `YOUR_API_SECRET_HERE` with your actual API Secret
6. Save the file

---

## Step 4 — Install Required Packages

1. Open **Command Prompt** (Windows) or **Terminal** (Mac/Linux)
2. Go to your project folder by typing:
   ```
   cd Desktop/oi-terminal
   ```
3. Type this command and press Enter:
   ```
   pip install flask kiteconnect
   ```
4. Wait for it to finish installing ✅

---

## Step 5 — Run the Project

In the same Command Prompt / Terminal, type:

```
python app.py
```

You will see this message:

```
→ Open: http://127.0.0.1:5000
→ Paper Trading: Virtual ₹1,00,000 capital
→ 5 Auto Strategies ready
```

✅ The server is now running!

---

## Step 6 — Open the Dashboard

1. Open your browser (Chrome, Firefox, Edge)
2. Go to 👉 **http://127.0.0.1:5000**
3. Click **"Login with Zerodha"**
4. Enter your Zerodha username & password
5. You will be taken to the dashboard automatically 🎉

---

## 📊 What You Will See on the Dashboard

| Feature | What it does |
|---|---|
| Live OI Chain | Shows Call & PUT data for each strike price |
| PCR Ratio | Tells if market is Bullish or Bearish |
| Long / Short Buildup | Shows where big traders are placing bets |
| Buy / Sell Signal | Auto-generated trade signal based on OI |
| Paper Trading | Practice trading with virtual ₹1,00,000 |
| P&L Tracker | Shows your profit & loss on paper trades |

---

## ⚠️ Important Notes

- The dashboard works only during **market hours (9:15 AM – 3:30 PM, Mon–Fri)**
- Every morning you need to **login again** (Zerodha token resets daily at 6 AM)
- To login again: delete the file called `access_token.txt` and refresh the page

---

## ❓ Something Not Working?

| Problem | Fix |
|---|---|
| `python` not found | Reinstall Python and check "Add to PATH" |
| `pip install` fails | Try `pip3 install flask kiteconnect` |
| Login fails | Make sure redirect URL is exactly `http://127.0.0.1:5000/callback` |
| No data showing | Check if market is open and Kite subscription is active |

---

## ⚠️ Disclaimer

This project is for **learning and practice purposes only**.
It is not financial advice. The creator is not responsible for any trading losses.
Always consult a SEBI-registered advisor before real trading.

---

*Made with ❤️ for learning options trading through data*

> **Nifty 50 + Bank Nifty Live OI Dashboard with Paper Trading**  
> Built with Flask + Zerodha Kite API

---

## 📋 Prerequisites

Before running this project, make sure you have the following:

- Python 3.8 or higher
- A **Zerodha Demat Account**
- A **Zerodha Kite Connect API** subscription (₹2000/month)
  - Sign up at: https://developers.kite.trade/

---

## 📁 Project Structure

```
oi-terminal/
│
├── app.py                  # Main Flask backend server
├── static/
│   └── dashboard.html      # Frontend dashboard UI
├── paper_trades.json       # Auto-created: stores paper trade data
├── access_token.txt        # Auto-created: stores Zerodha login token
├── requirements.txt        # Python dependencies
└── HOW_TO_RUN.md           # This file
```

---

## ⚙️ Step 1 — Get Your Zerodha API Keys

1. Go to https://developers.kite.trade/
2. Login with your Zerodha credentials
3. Create a new app → get your **API Key** and **API Secret**
4. Set the redirect URL to: `http://127.0.0.1:5000/callback`

---

## 🔑 Step 2 — Add Your API Keys

Open `app.py` and replace the placeholder values:

```python
API_KEY    = "YOUR_API_KEY_HERE"      # ← Replace with your API Key
API_SECRET = "YOUR_API_SECRET_HERE"   # ← Replace with your API Secret
```

> ⚠️ **Never share your API keys publicly or push them to GitHub!**  
> Add `access_token.txt` and your keys to `.gitignore`

---

## 📦 Step 3 — Install Dependencies

Open your terminal and run:

```bash
# Create a virtual environment (recommended)
python -m venv venv

# Activate it
# On Windows:
venv\Scripts\activate
# On Mac/Linux:
source venv/bin/activate

# Install required packages
pip install -r requirements.txt
```

### requirements.txt
```
flask
kiteconnect
```

Or install manually:
```bash
pip install flask kiteconnect
```

---

## ▶️ Step 4 — Run the Server

```bash
python app.py
```

You should see:

```
============================================================
  ⬡ OI TERMINAL v3.0 — PAPER TRADING EDITION
  Nifty 50 + Bank Nifty
============================================================
  → Open: http://127.0.0.1:5000
  → Paper Trading: Virtual ₹1,00,000 capital
  → 5 Auto Strategies ready
  → OI Activity with full timestamps
============================================================
```

---

## 🔐 Step 5 — Login with Zerodha

1. Open your browser and go to: **http://127.0.0.1:5000**
2. Click **"Login with Zerodha"**
3. Enter your Zerodha credentials
4. You will be redirected back to the dashboard automatically
5. The access token is saved locally — you won't need to login again until it expires (daily)

> 💡 Zerodha access tokens expire every day at **6:00 AM IST**.  
> Delete `access_token.txt` and login again each trading day.

---

## 📊 Step 6 — Using the Dashboard

Once logged in, the dashboard provides:

| Feature | Description |
|---|---|
| **Live OI Chain** | Strike-wise Call & PUT OI for Nifty + BankNifty |
| **PCR Ratio** | Live Put-Call Ratio with sentiment gauge |
| **Long/Short Buildup** | Real-time buildup detection across strikes |
| **OI Activity Log** | Timestamped OI activity feed |
| **5 Auto Strategies** | PCR Reversal, Call Wall Breakout, Put Wall Bounce, Long Buildup Ride, Short Cover Squeeze |
| **Paper Trading** | Auto paper trade execution with ₹1,00,000 virtual capital |
| **P&L Tracking** | Win/loss stats, daily P&L, trade history |

---

## 🔁 API Endpoints

| Endpoint | Description |
|---|---|
| `GET /` | Main dashboard |
| `GET /api/data/NIFTY` | Nifty OI data |
| `GET /api/data/BANKNIFTY` | BankNifty OI data |
| `GET /api/paper/state` | Paper trading portfolio state |
| `POST /api/paper/reset` | Reset paper trading capital |
| `POST /api/paper/close/<id>` | Manually close a position |
| `GET /api/paper/strategies` | List all 5 strategies |
| `GET /api/activity_log/<symbol>` | OI activity log |
| `GET /api/health` | Server health check |

---

## 🛑 Common Issues

**Login keeps failing?**
- Delete `access_token.txt` and try again
- Make sure redirect URL in Kite Console is exactly: `http://127.0.0.1:5000/callback`

**No OI data showing?**
- Market must be open (9:15 AM – 3:30 PM IST, weekdays)
- Check your Kite Connect subscription is active

**Module not found error?**
- Make sure your virtual environment is activated
- Run `pip install flask kiteconnect` again

---

## 🔒 Security Notes

Add this `.gitignore` file to your project before pushing to GitHub:

```
access_token.txt
paper_trades.json
__pycache__/
venv/
*.pyc
.env
```

And **never hardcode** your API keys in code you push publicly. Use environment variables instead:

```python
import os
API_KEY    = os.environ.get("KITE_API_KEY")
API_SECRET = os.environ.get("KITE_API_SECRET")
```

---

## ⚠️ Disclaimer

This project is for **educational and paper trading purposes only**.  
It does not constitute financial advice.  
The creator is not responsible for any real trading losses.  
Always consult a SEBI-registered advisor before making investment decisions.  
**Use at your own risk.**

---

## 📄 License

MIT License — Copyright (c) 2025  
See `LICENSE` file for full details.
