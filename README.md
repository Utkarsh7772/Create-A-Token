

**MyToken Solidity Contract**

**Description**
This Solidity program implements a basic ERC-20-like token contract named MyToken. It demonstrates fundamental concepts such as token minting, burning, and balance management. The contract allows users to mint new tokens and burn existing ones, ensuring that token balances and total supply are properly managed.

Getting Started
Executing Program
To run this program, you can use Remix, an online Solidity IDE. Follow these steps:

**Open Remix:** Visit the Remix website at https://remix.ethereum.org/.

**Create New File:** Click on the "+" icon in the left-hand sidebar of Remix. Save the file with a .sol extension (e.g., MyToken.sol).

**Copy and Paste Code:** Copy and paste the following Solidity code into the file:

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract MyToken {

    // Public variables
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // Mapping of address to token balances
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}

**Compile the Code:** Click on the "Solidity Compiler" tab in Remix. Ensure the "Compiler" option is set to "0.8.18" (or another compatible version). Click on "Compile MyToken.sol" to compile the code.

**Deploy the Contract:** Click on the "Deploy & Run Transactions" tab in Remix. Select the MyToken contract from the dropdown menu. Click on the "Deploy" button to deploy the contract to the Ethereum network.

**Interact with the Contract:** Once deployed, you can interact with the contract:

Use the mint function to create new tokens for an address.
Use the burn function to destroy existing tokens for an address.

**Functionality**
Mint Function: Increases the total supply and the balance of the specified address by a given amount.
Burn Function: Decreases the total supply and the balance of the specified address by a given amount, ensuring the address has enough tokens.

This contract serves as a foundation for understanding token management on the Ethereum blockchain, providing essential functionalities for creating and manipulating token supplies securely.
