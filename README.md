# Create and mint Token

This Solidity program is a simple "Create and mint Token" program that demonstrates functionality of Create and mint Token in Solidity programming language. 
## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has a single function that returns the string "Hello World!". This program serves as a simple and straightforward introduction to Solidity programming, and can be used as a stepping stone for more complex projects in the future.

## Getting Started

### Executing program
// Requirements
// show the Functionality of :
// 1 Only contract owner should be able to mint tokens
// 2 Any user can transfer tokens
// 3 Any user can burn tokens

// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";


contract _MyTokenAjmeet is ERC20, Ownable {
    constructor(string memory initialOwner,string memory symbol)
        ERC20(initialOwner, symbol)
        Ownable(msg.sender)
    {}

    function _mintthetoken (address _sendto, uint256 _amount) public onlyOwner {
        require(_amount > 0, "Amount should be greater than zero");
        _mint(_sendto, _amount);
    }
      function _burnthegiventoken (address _toburn, uint256 _amount) public  {  
        require(_amount > 0, "Amount should be greater than zero");
        _burn(_toburn, _amount);
    }
      function _Transfertoken (address _toanother, uint256 _amounttransfer) public returns (bool) {
         require(_amounttransfer > 0, "Amount should be greater than zero");
        return super.transfer(_toanother, _amounttransfer);
        
    }               
}


To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.20" (or another compatible version), and then click on the "Compile create and mint token.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "_My tokenAjmeet" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the _mintthetoken, _burnthegiventoken, _Transfertoken function. Click on the "_My tokenAjmeet" contract in the left-hand sidebar, and then click on the  _mintthetoken, _burnthegiventoken, _Transfertoken  function. Finally, click on the "transact" button to execute the function and retrieve the message.

## Authors

Ajmeet kour @Ajmeetkour


## License

This project is licensed under the MIT License.
