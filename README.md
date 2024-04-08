# Dynamic Trader Flask

Dynamic Trader Flask is a robust application built on Flask, aimed at providing users with a comprehensive platform for learning and practicing stock trading with live data. Users can access real-time and historical stock prices, execute trades, and monitor their portfolio performance. The admin panel offers tools for managing user accounts, overseeing transactions, and more.

## UML Diagram

```
+----------------------------------------------------+
|                    Flask Application               |
+----------------------------------------------------+
|                      Controllers                    |
|    +------------------------------------------+    |
|    |             QuoteController              |    |
|    | + get_ltp(instrument_identifier: str)    |    |
|    | + get_all_instrument_identifiers(): list |    |
|    | + get_quote_details(instrument_identifier: str): dict|    |
|    |                                          |    |
|    |             UserController               |    |
|    | + login(): dict                          |    |
|    | + register(): dict                       |    |
|    | + buy(): dict                            |    |
|    | + sell(): dict                           |    |
|    | + get_purchase_history(user_id: str): dict|    |
|    | + get_sell_history(user_id: str): dict   |    |
|    | + add_favorite_symbols(user_id: str): dict|   |
|    | + get_favorite_symbols(user_id: str): dict|   |
|    | + delete_favorite_symbols(user_id: str): dict| |
|    |                                          |    |
|    |             AdminController              |    |
|    | + create_admin(): dict                   |    |
|    | + create_user(): dict                    |    |
|    | + pause_user(): dict                     |    |
|    | + ban_user(): dict                       |    |
|    | + get_user_history(user_id: str): dict   |    |
|    +------------------------------------------+    |
|                                                    |
|                      Models                        |
|    +------------------------------------------+    |
|    |              QuoteModel                 |    |
|    | + get_last_trade_price(instrument_identifier: str): float|    |
|    | + get_all_instrument_identifiers(): list |    |
|    | + get_quote_details(instrument_identifier: str): dict|    |
|    |                                          |    |
|    |              UserModel                  |    |
|    | + create_user(username: str, password: str, email: str, role='user'): dict|    |
|    | + get_user_by_id(user_id: str): dict    |    |
|    | + update_user(user_id: str, update_data: dict): dict|    |
|    | + get_user_by_username(username: str): dict|    |
|    | + add_purchase_to_history(user_id: str, purchase_data: dict)|    |
|    | + add_sale_to_history(user_id: str, sale_data: dict): |    |
|    +------------------------------------------+    |
|                                                    |
|                      Config                        |
|    +------------------------------------------+    |
|    |                 config.py                |    |
|    +------------------------------------------+    |
+----------------------------------------------------+
       |              |            |
       |              |            |
       v              v            v
UserController   AdminController
       |               |
       v               |
QuoteController -----
```

## Features

- **Secure User Authentication:** Robust user authentication system ensures secure registration, login, and account management.
- **Real-time Stock Trading:** Users can buy and sell stocks using real-time market data streamed via websockets.
- **Portfolio Management:** Track owned stocks, review purchase history, and analyze portfolio performance.
- **Favorite Stocks:** Easily manage a list of favorite stocks for quick access and tracking.
- **Admin Panel:** Admins have access to features for managing user accounts, monitoring transactions, and overseeing system activity.

## Installation

1. **Clone the Repository:**
   ```
   git clone https://github.com/parth-5097/dynamic_trader_flask.git
   ```

2. **Navigate to the Project Directory:**
   ```
   cd dynamic_trader_flask
   ```

3. **Create a Virtual Environment** (Optional but Recommended):
   ```
   python -m venv venv
   ```

4. **Activate the Virtual Environment:**
   - On Windows:
     ```
     venv\Scripts\activate
     ```
   - On macOS and Linux:
     ```
     source venv/bin/activate
     ```

5. **Install Required Dependencies:**
   ```
   pip install -r requirements.txt
   ```

6. **Set Up the Database:**
   - MongoDB is used as the database. Ensure MongoDB is installed and running locally, or update the database configuration in `app/config.py`.

7. **Start the Flask Server:**
   ```
   python app.py
   ```

8. **Access the Application** in your web browser at `http://127.0.0.1:5000`.

## Usage

- Register a new account or log in with existing credentials.
- Explore the stock market and manage favorite stocks for tracking.
- Buy and sell stocks based on real-time market data.
- Monitor portfolio performance and transaction history.
- Admins can manage user accounts, view transaction logs, and perform system maintenance tasks.
