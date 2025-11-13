Relationship Diagram) for the Banking Management System

Main Purpose

This ERD shows how different entities in a banking system (like bank, branch, customer, account, employee, and loan) are connected to each other — it represents data relationships in a banking database.


 Entities and Their Attributes

1. Bank

Attributes:

Code

City

Address


Relationships:

A Bank has many Customers.

A Bank has many Branches.

2. Branch

Attributes:

branch_code

branch_name


Relationship:

A Branch belongs to a Bank (through the “have” relationship).


3. Customer

Attributes:

Cust_id

cust_name

Mobile_no

Address


Relationships:

A Customer has one or more Accounts.

A Customer can avail one or more Loans.

4. Account

Attributes:

Account_no

Balance


Relationships:

A Customer has an Account.

An Employee manages an Account.

There is an "Is A" relationship meaning:

An Account can be a Saving Account or a Current Account (Inheritance / specialization).


5. Employee

Attributes:

emp_id

emp_name


Relationship:

Employee manages the Account of customers.


6. Loan

Attributes:

loan_no

Amount


Relationship:

A Customer avails a Loan.

A Loan has one or more Payments (through the “Loan Payment” relationship).

7. Payment

Attributes:

Payment_amount

Payment_date


Relationship:

A Payment belongs to a Loan (through “Loan Payment”).


Key Relationships Summary

Relationship Name	From Entity	To Entity	Meaning

has	Bank	Customer	Bank has many customers
have	Bank	Branch	Bank has many branches
have	Customer	Account	Customer owns account(s)
Manage	Employee	Account	Employee manages account
Avail	Customer	Loan	Customer takes loan
Loan Payment	Loan	Payment	Loan has payments
