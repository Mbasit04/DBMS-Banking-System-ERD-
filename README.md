CREATE DATABASE BankingSystem;
USE BankingSystem;

CREATE TABLE Bank (
    bank_id INT PRIMARY KEY,
    bank_name VARCHAR(50),
    city VARCHAR(50),
    address VARCHAR(100)
);

CREATE TABLE Branch (
    branch_id INT PRIMARY KEY,
    branch_name VARCHAR(50),
    branch_code VARCHAR(20),
    bank_id INT,
    FOREIGN KEY (bank_id) REFERENCES Bank(bank_id)
);

CREATE TABLE Customer (
    cust_id INT PRIMARY KEY,
    cust_name VARCHAR(100),
    mobile_no VARCHAR(15),
    address VARCHAR(100)
);

CREATE TABLE Account (
    account_no INT PRIMARY KEY,
    cust_id INT,
    branch_id INT,
    account_type VARCHAR(20),
    balance DECIMAL(10,2),
    FOREIGN KEY (cust_id) REFERENCES Customer(cust_id),
    FOREIGN KEY (branch_id) REFERENCES Branch(branch_id)
);

CREATE TABLE Employee (
    emp_id INT PRIMARY KEY,
    emp_name VARCHAR(100),
    branch_id INT,
    FOREIGN KEY (branch_id) REFERENCES Branch(branch_id)
);

CREATE TABLE Loan (
    loan_id INT PRIMARY KEY,
    cust_id INT,
    branch_id INT,
    amount DECIMAL(10,2),
    FOREIGN KEY (cust_id) REFERENCES Customer(cust_id),
    FOREIGN KEY (branch_id) REFERENCES Branch(branch_id)
);
