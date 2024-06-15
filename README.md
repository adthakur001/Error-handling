# ERROR HANDLING

A basic smart contract for handling deposits and withdrawals with error checking to ensure balance constraints, using require(), revert(), and assert() for robust error handling
## Description

This project involves developing a smart contract using Solidity to manage a simple balance system with robust error handling. The contract allows users to deposit and withdraw funds while ensuring that the balance constraints are respected. Users can deposit amounts into the contract, with a check to prevent the balance from exceeding a limit of 500 units, reverting the transaction if the limit is surpassed. Withdrawals are permitted only if the user has sufficient balance, enforced by a `require()` statement. Additionally, the contract includes a function to verify if the balance is zero using an `assert()` statement. This project illustrates key concepts of error handling in Solidity, making it an excellent foundational exercise for managing contract states and conditions.
## Getting Started
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., error.sol). Copy and paste the following code into the file:

     // SPDX-License-Identifier: MIT
     pragma solidity ^0.8.13;

    contract ErrorHandling {
    
    uint public balance = 0;

    // Function to withdraw funds
    function withdraw(uint amount) public {
        // Using require to ensure that the balance is sufficient for withdrawal
        require(balance >= amount, "Insufficient balance to withdraw!");
        balance -= amount;
    }

    // Function to deposit funds
    function deposit(uint amount) public {
        balance += amount;
        // Checking if the balance exceeds the limit using revert()
        if (balance > 200) {
            revert("Balance limit exceeded!");
        }
    }

    // Function to check if the balance is empty
    function isEmpty() public view returns (string memory) {
        // Using assert to ensure that the balance is zero
        assert(balance == 0);
        return "You have no funds available.";
    }}



To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile error.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "error" contract from the dropdown menu, and then click on the "Deploy" button.
Now just call the functions deposite to add amount  ,withdraw to withdraw the amount  and balance to check balance and isempty to check if the balance is zero.

You can check the error handling conditions by applying the conditions during the output(e.g try to exceed your balance by 200 to run revert statement)




## Authors

Aditya Thakur
