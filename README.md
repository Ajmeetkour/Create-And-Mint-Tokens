# Create and mint Token

This Solidity program is a simple "Create and mint Token" program that demonstrates functionality of Create and mint Token in Solidity programming language. 
## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has a single function that returns the string "Hello World!". This program serves as a simple and straightforward introduction to Solidity programming, and can be used as a stepping stone for more complex projects in the future.

## Getting Started

### Executing program

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract MyTokenAjmeet is ERC20, Ownable {
    constructor(string memory initialOwner,string memory symbol)
        ERC20(initialOwner, symbol)
        Ownable(msg.sender)
    {}

    function mintthetoken (address sendto, uint256 amount) public onlyOwner {
        require(sendto != address(0), "Invalid address");
        require(amount > 0, "Amount should be greater than zero");
        _mint(sendto, amount);
    }

      function burnthegiventoken (address toburn, uint256 amount) public  {   
        require(toburn != address(0), "Invalid address");
        require(amount > 0, "Amount should be greater than zero");
        _burn(toburn, amount);
    }
      function Transfertoken (address toanother, uint256 amounttransfer) public  returns (bool) {
        require(toanother != address(0), "Invalid address");
        require(amounttransfer > 0, "Amount should be greater than zero");
        return super.transfer(toanother, amounttransfer);
        
    }
}
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.20" (or another compatible version), and then click on the "Compile create and mint token.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "My tokenAjmeet" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mintthetoken, burnthegiventoken, Transfertoken function. Click on the "My tokenAjmeet" contract in the left-hand sidebar, and then click on the  mintthetoken, burnthegiventoken, Transfertoken  function. Finally, click on the "transact" button to execute the function and retrieve the message.

## Authors

Ajmeet kour @Ajmeetkour


## License

This project is licensed under the MIT License.
