# alcruzProject-Types-of-Functions
This project is a custom ERC20 token built using the OpenZeppelin library. This token follows the ERC20 standard, ensuring compatibility with various wallets, exchanges, and others.

## Smart Contract code
```Solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract MyToken is ERC20 {
    constructor() ERC20("AltCz", "ALC") {
        _mint(msg.sender, 100 * 10 ** decimals());
    }
}
```

## Preconditions
You do not need any form of downloads or installations for this project. To deploy and interact with this contract, you only need the [Remix IDE](https://remix.ethereum.org/#lang=en&optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.26+commit.8a97fa7a.js).

## Setup Instructions
1. Open Remix IDE
2. Select the ERC20 environment in the dropdown menu.
3. Under the contracts folder, create a new file named `MyToken.sol` and paste the smart contract code into it.
4. In the "Solidity Compiler" tab, select the Solidity version 0.8.20 (or a compatible version).
5. Click on "Compile MyToken.sol".

## Deployment Instructions
1. Go to the "Deploy & Run Transactions" tab.
2. Select the MyToken contract from the dropdown menu.
3. Click on the "Deploy" button.
4. Confirm the transaction in the Remix simulator.
5. After deployment, you can interact with the contract using the following functions:
- balanceOf(address account): Returns the token balance of the specified address.
- transfer(address recipient, uint256 amount): Transfers tokens to the specified address.
- approve(address spender, uint256 amount): Approves the specified address to spend a certain amount of tokens on behalf of the message sender.
- allowance(address owner, address spender): Returns the remaining number of tokens that the spender is allowed to spend on behalf of the owner.
- transferFrom(address sender, address recipient, uint256 amount): Transfers tokens from one address to another using the allowance mechanism.

## Sample Interaction
1. Check Balance:
- In the "Deployed Contracts" section, click on the balanceOf function.
- Enter the address you want to check the balance of and click "Call".
2. Transfer Tokens:
- Click on the transfer function.
- Enter the recipient's address and the amount of tokens to transfer.
- Click "Transact" and confirm the transaction in MetaMask.
3. Approve Tokens:
- Click on the approve function.
- Enter the spender's address and the amount of tokens to approve.
- Click "Transact" and confirm the transaction in MetaMask.
4. Transfer Tokens Using Allowance:
- Click on the transferFrom function.
- Enter the sender's address, recipient's address, and the amount of tokens to transfer.
- Click "Transact" and confirm the transaction in MetaMask.

## Author
Althea Louise C. Cruz
