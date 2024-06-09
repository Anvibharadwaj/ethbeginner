# Creatin a Token using Solidity

This Solidity program is a simple program that demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how it works.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has a mainly 2 function the 1st one is used to ncreases the total supply by given value and 2nd is to increases the balance of the “sender” address by that value. This program serves as a simple and straightforward introduction to Solidity programming, and can be used as a stepping stone for more complex projects in the future.

## Getting Started
### Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., finalassementtoken.sol). Copy and paste the following code into the file:

```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;
contract AssementToken {

    // public variables Token_name,totalabbrv is going to store the name of coins and total supply will store number of supply of coin.
    string public Token_name = "Zerion";
    string public Token_abbr = "ze";
    //totalsupply can't be negative so we will use unsigned datatype.
    uint public Totalsupply = 0;

    // mapping variable
    //by the help of mapping, the address is associated to uint i.e. unsigned integer and it will return the token amount when we will pass the address.
    mapping(address => uint) public balances;

    // mint function has 2 parameters:- address and values that will increases the total supply by given value and increases the balance 
    //of the “sender” address by that value
    function mint (address _address,uint _values) public {
        //increasing the totalsupply by the amount passing
        Totalsupply += _values;
        balances[_address] += _values;
    }

    // burn function
     function burn (address _address,uint _values) public {
        if (balances[_address] >= _values){
            //will deduct the value from the total supply 
            Totalsupply -= _values;
            //will deduct the value from the balance of sender 
            balances[_address] -= _values;
        }
     }

}

```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.26" (or another compatible version), and then click on the "Compile finalassementtoken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "AssementToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint and burn function. Click on the "AssementToken" contract in the left-hand sidebar, and then click on the "mint" function.After that add address and value Finally, click on the "transact" button to execute the function and retrieve the message Similar for burn as well.

## Authors
Anvi Bharadwaj


