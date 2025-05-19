# IBKR Trailing Stop Limit Orders

Automate placing trailing stop limit sell orders on Interactive Brokers (IBKR) using Python and the `ib_insync` library. This tool reads stock order data from a CSV file and places GTC trailing stop-limit orders with logic to protect against selling below your average buy price.

---

## ✅ Features

- Connects to Interactive Brokers via TWS or IB Gateway using API
- Supports delayed data fallback if real-time quotes are unavailable
- Reads orders from a CSV file including:
  - Symbol (e.g., AAPL, TSLA)
  - Quantity
  - Trailing stop percentage
  - Limit price offset
  - Average buy price (to prevent selling at a loss)
- Dynamically calculates stop and limit prices based on live market prices
- Places **Good-Till-Canceled (GTC)** trailing stop-limit sell orders
- Logs all order activity, errors, and skipped trades

---

## 🛠 Requirements

- Python 3.7 or higher
- IBKR Trader Workstation (TWS) or IB Gateway running and API enabled
- Python libraries:
  - `ib_insync`
  - `pandas`

---

## 📁 Setup Instructions

1. Clone this repository  
2. Install required Python packages  
3. Launch IBKR TWS or IB Gateway with API enabled  
4. Prepare your CSV file with the required columns:
   - `Symbol`, `Quantity`, `TrailingPercent`, `LimitOffset`, `AvgBuyPrice`

---

## ▶️ How to Use

1. Start your TWS/IB Gateway and ensure it's connected  
2. Run the script with your CSV file path as input  
3. Orders will be submitted, and logs will be generated showing each action

---

## 📝 Example CSV Format

Symbol,Quantity,TrailingPercent,LimitOffset,AvgBuyPrice

AAPL,10,1.5,0.3,180.25

TSLA,5,2.0,0.5,700.00   


---

## 📌 Important Notes

- Orders will **not** be placed if the current market price is **below your average buy price**
- Script uses GTC time-in-force to keep orders active beyond market hours
- Ensure API access and market data subscription are properly set in your IBKR account

---

## 📬 Optional: Alerts

Support can be added for Telegram or Email alerts on order execution. Contact for integration.

---

## 🧑‍💻 Author

Built by [Jahanzaib] 
Feel free to reach out for custom trading automation projects.

---
