contract that implements the require(), assert() and revert() statements.

This Solidity program is a simple program that demonstrates how to use the three methods of error handling. This code includes all the three statements(require,assert and revert).
## Description
This Solidity smart contract demonstrates various error handling techniques and ownership control in Ethereum smart contracts. It includes functions for setting data, asserting conditions, restricting access to only the contract owner, and demonstrating reverts based on conditions.

Features
Owner Management: The contract stores the address of the owner upon deployment and includes a function to restrict certain operations to only the owner.

Data Management: Provides a function (setData) to set a non-zero value to a public data variable, ensuring that the input data is valid before modification.

Error Handling: Includes an example of using assert for validating conditions (assertExp function) and revert for reverting transactions based on conditions (revertExample function).

Functions
setData(uint _data): Sets the data variable to the provided _data value, ensuring _data is non-zero.

assertExp(uint a, uint b): Performs an assertion to ensure a is not equal to b. This is a demonstration of using assert for runtime assertions.

onlyOwnerFunction(): Restricts access to certain operations (not specified in detail) to only the contract owner. Uses require to enforce this restriction.

revertExample(uint a, uint b): Checks if a is less than b and reverts the transaction with a message if true; otherwise, computes and returns a - b.

Usage
To use this contract, deploy it on an Ethereum-compatible blockchain network. After deployment:

Set data using setData(uint _data), ensuring _data is non-zero.
Use assertExp(uint a, uint b) to assert conditions during function execution.
Utilize onlyOwnerFunction() to restrict specific functionalities to the contract owner.
Explore revertExample(uint a, uint b) to understand how to handle conditions and revert transactions based on specific criteria.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension. Copy and paste the following code into the file:

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract errorhandlingexp {
    address public owner;
    uint public data;

    constructor() 
    {owner = msg.sender;
    }

    function setData(uint _data) public {
        require(_data != 0, "Data must be non-zero");
        
        data = _data;
    }

    function assertExp(uint a, uint b) public pure returns (uint) {
        assert(a != b);
        return a + b;
    }

    function onlyOwnerFunction() public view {
        require(msg.sender == owner, "Only owner can call this function"); 
        
    }

    function revertExample(uint a, uint b) public pure returns (uint) {
        if (a < b) {
            revert("Condition not met");
        }
        return a - b;
    }
}


To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.0" (or another compatible version), and then click on the compile button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the function.




## License

This project is licensed under the MIT License - see the LICENSE.md file for details
