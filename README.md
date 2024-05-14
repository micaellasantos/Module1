# Smart conttracts
Solidity smart contract, AssertionContract, is a basic example demonstrating the use of require(), assert(), and revert() statements for error handling and validation within Ethereum smart contracts.

## Description
The statements are essential tools for ensuring the correctness and safety of smart contracts by enforcing preconditions, validating conditions, and handling exceptional situations gracefully.

## Getting Started

### Executing the Program

Using Remix IDE, a online development environment for Ethereum smart contracts, execute the provided Solidity smart contract by creating a new file, pasting the code, compiling it using the Solidity Compiler tab, deploying it to a chosen Ethereum network via the Deploy & Run Transactions tab, and subsequently interacting with its functions, allowing us to test and validate the contract's behavior comprehensively.

Code:

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract AssertionContract {
    uint256 public totalValue;

    function deposit(uint256 _value) public {
        require(_value > 0, "Value must be greater than 0");
        totalValue += _value;
    }

    function withdraw(uint256 _value) public {
        assert(totalValue >= _value);
        totalValue -= _value;
    }

    function transfer(address _to, uint256 _value) public {
        if (_value > totalValue) {revert("Insufficient balance"); 
    }    
        totalValue -= _value;
    }
}


### Author
Name: Mica Ella Gonzaga Santos

Email: 8213946@ntc.edu.ph
