# My Token

This Solidity program's primary goal is to develop a token contract that will let users create and burn tokens.

## Description

This application is a simple contract that uses a mapping data structure to keep track of how many tokens are owned by a certain address.
## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
        string public name = "PLEASE";
        string public abbrv = "PLS";
        uint public supply = 0;

    // mapping variable here
        mapping(address => uint) public blnc;

    // mint function
        function mint(address add, uint val) public{
            supply += val;
            blnc[add] += val;
        }

    // burn function
        function burn(address add, uint val) public{
            if(blnc[add] >= val){
                supply -= val;
                blnc[add] -= val;
            }
        }

}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "HelloWorld" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the sayHello function. Click on the "HelloWorld" contract in the left-hand sidebar, and then click on the "sayHello" function. Finally, click on the "transact" button to execute the function and retrieve the "Hello World!" message.

## Authors

Darla ysabel  
[https://academy.metacrafters.io/profile](https://discord.com/channels/@me))


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
