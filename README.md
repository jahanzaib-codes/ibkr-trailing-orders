# IBKR Trailing Stop Limit Orders

Automate placing trailing stop limit sell orders on Interactive Brokers (IBKR) using Python and the `ib_insync` library. This tool reads stock order data from a CSV file and submits stop-limit sell orders with trailing stop logic based on market prices.

---

## Features

- Connects to IBKR Trader Workstation (TWS) or IB Gateway via API
- Supports delayed market data if real-time data is unavailable
- Reads order details (symbol, quantity, trailing stop %, limit offset, average buy price) from a CSV file
- Calculates dynamic stop and limit prices based on the current market price and trailing percentages
- Submits Good-Till-Canceled (GTC) trailing stop limit sell orders
- Logs detailed info, skips invalid or risky orders to prevent unintended losses

---

## Requirements

- Python 3.7+
- `ib_insync` library
- `pandas` library
- Interactive Brokers Trader Workstation (TWS) or IB Gateway running and API enabled

---

## Installation

1. Clone the repo:
   ```bash
   git clone https://github.com/JAHANZAIB571/ibkr-trailing-orders.git
   cd ibkr-trailing-orders
