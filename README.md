# Functions And Errors

In this project I have demonstrated how to use functions like revert(),require() and assert().

## Description

In this project i have made a contract called "Transactions" in which I have made functions like withdraw, Transfer, balance and deposit.

## Getting Started


### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., transact.sol). Copy and paste the following code into the file:
```
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.7;

contract Transactions {
    mapping(address => uint256) public balances;

    function deposit(uint256 amount) public {
        require(amount > 0, "deposit amount needs to be greater than zero");
        balances[msg.sender] += amount;
    }

    function transfer(address recipient, uint256 amount) public {
        require(balances[msg.sender] >= amount, "Not enough balance");

         assert(balances[recipient] + amount >= balances[recipient]);

        
        balances[msg.sender] -= amount;
        balances[recipient] += amount;
    }

    function withdraw(uint256 amount) public {
       
        if (balances[msg.sender] < amount) {
           
            revert("Not enough balance to withdraw");
        }
        balances[msg.sender] -= amount;
    }
}


```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile transact.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "transact" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the sayHello function. Click on the "transact" contract in the left-hand sidebar, and then click on the "deposit,withdraw,blances or transfer functions. Finally, click on the "transact" button to execute the function and retrieve the function related message int the console.


## Authors

Contributors names and contact info

Akash  
Email: vermakash876@gmail.com


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
