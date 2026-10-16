# 🏦 Bank Account Management System
A simple Object-Oriented Python project for creating and managing bank accounts in Jupyter Notebook.
It demonstrates OOP concepts: `class`, `__init__`, `__str__`, `deposit()` and `withdraw()`.
![Python](https://img.shields.io/badge/Python-3.13-blue?logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)
![OOP](https://img.shields.io/badge/Paradigm-OOP-green)
![License](https://img.shields.io/badge/License-MIT-lightgrey)
## 📋 Table of Contents
- [About](#-about-the-project)
- [Features](#-features)
- [Project Structure](#-project-structure)
- [Requirements](#-requirements)
- [Installation & Usage](#-installation--usage)
- [Code Overview](#-code-overview)
- [Example Run](#-example-run)
- [Withdrawal Logic](#-withdrawal-logic)
- [Future Improvements](#-future-improvements)
- [License & Author](#-license--author)
## 📖 About the Project
This notebook implements a `BankAccount` class that stores **owner name** and **balance**,
and supports basic banking operations: **deposit** and **withdrawal**.
Perfect for Python beginners practicing classes, instance attributes,
string representation with `__str__`, and conditional balance checking.
## ✨ Features
- Create multiple accounts with owner name and initial balance
- Deposit money with instant balance update
- Withdraw only if sufficient funds exist, otherwise show warning
- Display account info with `print(account)`
- Friendly console messages for every operation
- Zero dependencies, only Python standard library
## 📁 Project Structure
```text
Bank-Account/
├── Bank Account.ipynb   # Main notebook: class + test cases
└── README.md            # Project documentation
```
## ⚙️ Requirements
- Python `>= 3.8`
- Jupyter Notebook / JupyterLab / VS Code with Python extension
## 🚀 Installation & Usage
1. Clone the repository:
```bash
git clone https://github.com/NazaninFereydouniF/Bank-Account
cd bank-account
```
2. Launch Jupyter:
```bash
jupyter notebook "Bank Account.ipynb"
```
3. Run all cells top to bottom to create accounts and test transactions.
## 🧠 Code Overview
### Class: `BankAccount`
```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self.balance = balance
    def __str__(self):
        return f"Account Owner: {self.owner} \nAccount Balance: {self.balance}"
    def deposit(self, dp_amt):
        self.balance += dp_amt
        print(f'Deposit Accepted. \nAmount of current deposit: {dp_amt} \nCurrent Account Balance: {self.balance}')
    def withdraw(self, wd_amt):
        if self.balance >= wd_amt:
            self.balance -= wd_amt
            print(f'Withdrawal Accepted. \nAmount of current withdraw: {wd_amt} \nCurrent Account Balance: {self.balance}')
        else:
            print('Funding is Unavailable!')
```
### Creating Accounts:
```python
act1 = BankAccount('John', 100)
act2 = BankAccount('Sara', 150)
act3 = BankAccount('Tom', 0)
act4 = BankAccount('Lisa', 200)
act5 = BankAccount('Amy', 50)
```
## 💡 Example Run
**Deposit:**
```text
Deposit Accepted.
Amount of current deposit: 230
Current Account Balance: 330
```
**Successful Withdraw:**
```text
Withdrawal Accepted.
Amount of current withdraw: 75
Current Account Balance: 255
```
**Failed Withdraw (insufficient funds):**
```text
Funding is Unavailable!
```
> Example: `act4` with balance `320` tries to withdraw `500` → rejected.
## 🛡️ Withdrawal Logic
| Condition | Result |
| :--- | :--- |
| `balance >= withdraw_amount` | Accepted, balance decreased |
| `balance < withdraw_amount` | `Funding is Unavailable!`, balance unchanged |
## 🔮 Future Improvements
- [ ] Add account number and transaction history
- [ ] Validate negative / zero amounts for deposit and withdraw
- [ ] Add `transfer()` method between accounts
- [ ] Save accounts to CSV / JSON and convert to `bank_account.py` module
## 📄 License & Author
Released under the **MIT License**. Free to use, modify and share.
Created for Python OOP practice with Jupyter Notebook. If useful, please ⭐ star the repo!
