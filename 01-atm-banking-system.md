# Project — Mini ATM Banking System

* **Team size:** 4  
* **Type:** Console application, Go  

---

## Before You Start (As a Team)

Restate the goal out loud, all four of you, the same way:

> *What does the ATM actually consist of — a balance, a PIN, a menu, a loop, and what else?*

Before splitting the work, agree on what the program needs to remember and how the different parts will work together.

### Integration Contract
Write your integration contract (**one sentence per person**):

> *"I own `___`, I hand off `___` to `___`."*

---

## Objective

A console ATM application where the user logs in using a PIN and can check their balance, deposit money, withdraw money, transfer money, change their PIN, or exit.

* The program should continue running until the user chooses to exit.
* **No web, HTTP, HTML/CSS, or concurrency needed** — this is a console application focused on program flow, conditions, loops, functions, validation, and type conversion.

---

## Interface Mockup

```text
========================
        MINI ATM
========================

Enter PIN: 1234

Login successful!

1. Check Balance
2. Deposit
3. Withdraw
4. Transfer Money
5. Change PIN
6. Exit

Choose an option:
```

---

## Core Requirements

* Login using a PIN with a maximum of 3 attempts
* Check the current balance
* Deposit money
* Withdraw money
* Transfer money to another account
* Change the PIN
* Validate user input
* Track and update the current balance
* Handle insufficient balance
* Keep showing the menu until the user exits
* Display a final message when exiting

---

## Build It in Levels

* **Level 1 — Login & Menu:** Implement PIN authentication, 3 login attempts, a basic menu, and Exit. No banking operations yet — just prove the program flow works.
* **Level 2 — Core Banking:** Add Check Balance, Deposit, and Withdraw. Make sure the balance updates correctly after every successful operation.
* **Level 3 — Transfer & PIN:** Add Money Transfer and Change PIN. Add proper validation and make sure the updated PIN works for future login attempts.
* **Level 4 — Validation & Polish:** Reject invalid menu choices, negative/zero amounts, non-numeric input, insufficient balance, and invalid PIN operations. Add clear error messages.

---

## Sample State View

```text
Player: Ahmed
Balance: 1700
Last Operation: Transfer
Receiver: 2045
Amount: 300

1. Check Balance
2. Deposit
3. Withdraw
4. Transfer Money
5. Change PIN
6. Exit
```

---

## Watch For

* **Persistence:** The ATM should keep running after every operation — the menu should repeat until Exit is selected.
* **State Updates:** The balance must actually change after a successful deposit, withdrawal, or transfer.
* **Failure Safety:** A failed withdrawal or transfer must not change the balance.
* **Validation Order:** Input validation should happen before performing the operation.
* **Type Conversion:** `"500"` and `500` are not the same thing — understand why terminal input may need type conversion before arithmetic.
* **Modular Code:** The project should be divided into functions with clear responsibilities, not one giant function handling everything.

---

## Team Division

| Role | Owns | Hands off |
| :--- | :--- | :--- |
| **Authentication** | PIN login, login attempts, authentication | Login result |
| **Deposit & Withdrawal** | Balance, deposits, withdrawals, amount validation | Updated balance / operation result |
| **Money Transfer** | Receiver account, transfer amount, transfer validation | Transfer result / updated balance |
| **CLI & PIN Management** | Menu, program loop, change PIN, exit, integration | The finished game |

> **Note:** Before any code is shared, the team should agree on what represents the shared state (PIN, balance, etc.), what each function receives, and what each function returns. That agreement is the actual interface between the four parts.

---

## Stuck? Ask Better (Team Edition)

If an operation produces the wrong result, don't say *"the ATM is broken."*

**State:**
1. The starting balance
2. The operation performed
3. The input entered
4. The expected result
5. The actual result
6. Whether the problem happens only for one operation or across multiple operations

**Example:**
> *"The starting balance is 2000. The user deposits 500. The program displays 2500, but Check Balance still shows 2000."*
