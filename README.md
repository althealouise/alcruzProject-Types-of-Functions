# alcruzProject-Types-of-Functions
This project is a custom ERC20 token built using the OpenZeppelin library. This token follows the ERC20 standard, ensuring compatibility with various wallets, exchanges, and others. Additionally, it includes mint, burn, and transfer functionalities to manage the token supply.

## Project Submission Requirements
- "For this project, you will write a smart contract to create your own ERC20 token and deploy it using HardHat or Remix. Once deployed, you should be able to interact with it for your walk-through video. From your chosen tool, the contract owner should be able to mint tokens to a provided address and any user should be able to burn and transfer tokens."

## Smart Contract code
```Solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract MyToken is ERC20, Ownable {
    constructor() ERC20("AltCz", "ALC") Ownable(msg.sender) {
        _mint(msg.sender, 100 * 10 ** decimals());
    }

    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }

    function burn(uint256 amount) public {
        _burn(msg.sender, amount);
    }

    function transfer(address recipient, uint256 amount) public override returns (bool) {
        return super.transfer(recipient, amount);
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
- transfer(address recipient, uint256 amount): Transfers tokens from the caller's address to the recipient's address.
- mint(address to, uint256 amount) public onlyOwner: Mints new tokens and assigns them to the specified address. Can only be called by the contract owner.
- burn(uint256 amount) public: Burns a specific amount of tokens from the caller's balance.

## Sample Interaction
1. **Check Balance**: Use the `balanceOf` function to check the token balance of an address.
2. **Mint Tokens**: Call the `mint` function with the recipient's address and the amount of tokens to mint. Only the contract owner can call this function.
3. **Burn Tokens**: Call the `burn` function with the amount of tokens to burn from the caller's balance.
4. **Transfer Tokens**: Call the `transfer` function with the recipient's address and the amount of tokens to transfer from the caller's balance.

## Author
Althea Louise C. Cruz
