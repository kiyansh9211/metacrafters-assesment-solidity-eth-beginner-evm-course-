# Create a Token

This is a simple project regarding how to create a token in solidity programming.

## Description

In this project I have deployed a custom token on the Ethereum blockchain using the Solidity programming language. This token will adhere to the ERC-20 standard, ensuring compatibility with a wide range of wallets and exchanges.

## Getting Started

### Executing program

Step 1: Open Remix IDE
1. Open your web browser and go to https://remix.ethereum.org/ .
2. You will see the Remix IDE interface, which is an online platform for Solidity development.

Step 2: Create a New File

Create a Workspace:

1. In the left sidebar, click on the "File Explorers" icon (first icon on the top left).
2. Click on the "+" icon to create a new workspace.
3. Name your workspace (e.g., MyTokenProject).

Create a Solidity File:

1. In the "File Explorers" panel, right-click on the contracts folder and select "New File".
2. Name your file (e.g., MyToken.sol).

Step 3: Write Your Solidity Code

1. Open the Created File:

Click on MyToken.sol in the contracts folder to open it in the editor.

2. Write the Code:

Copy and paste the following basic ERC-20 token code into MyToken.sol:

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
contract MyToken {

// public variables  
string public tokenName = "KIYANSH"; 
string public tokenAbbrv = "ABCD"; 
uint public totalSupply = 0;

// mapping variable  
mapping(address => uint) public balances;

// mint function 
function mint (address _address, uint _value) public { 
  totalSupply += _value; 
  balances[_address] += _value; 
}

// burn function 
function burn (address _address, uint _value) public { 
  if (balances[_address] >= _value) {
  totalSupply -= _value; 
  balances[_address] -= _value; 
  }
}
}


To compile the code, switch to the "Solidity Compiler" panel by clicking the third icon on the left sidebar. Ensure that the compiler version is set to match your Solidity version (e.g., 0.8.0 or higher), and then click the "Compile MyToken.sol" button. This action will compile your Solidity code, displaying any compilation errors or warnings that need addressing.

Once the code is successfully compiled, you can deploy it by navigating to the "Deploy & Run Transactions" panel, which is the fourth icon on the left sidebar. In this panel, set the environment to "JavaScript VM" to deploy on a local blockchain provided by Remix. Ensure your contract (e.g., MyToken) is selected in the "Contract" dropdown menu. If your contract constructor requires parameters, input them in the provided fields. Click the "Deploy" button to deploy your contract. After deployment, your contract instance will appear under the "Deployed Contracts" section. You can expand this section to interact with your contract’s functions, testing and verifying its behavior directly within Remix. This streamlined process in Remix IDE allows developers to efficiently compile, deploy, and interact with their smart contracts in a user-friendly environment.
