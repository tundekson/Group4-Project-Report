# Group4-Project-Report

1st Weekend Project Report - Group 4 

--------------------------------------------------------------------------------------------------------

HelloWorld.sol Contract -Address: 0xbF09320746353c9E74e4D3DBB7396d6A87AAA61e


--------------------------------------------------------------------------------------------------------

//SMART CONTRACT

// SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.7.0 <0.9.0;


contract HelloWorld {

      string private text;
   
      address public owner;


       constructor(){
            text = "Hello World!";
       
            //owner is set to the deploy account address
       
            owner = msg.sender;
       }


      function helloWorld() public view returns (string memory){
   
            return text;
      }
  
      modifier onlyOwner(){
   
            require(msg.sender == owner, "Wrong address. Not the owner!");
       
            _;
       
      }


      function setText(string calldata newText) public onlyOwner{
   
            text = newText;
       
      }


      function transferOwnership(address newOwner) public onlyOwner {
   
            owner == newOwner;
       
      }
   
}



--------------------------------------------------------------------------------------------------------


REPORT

1 - Contract deployment (constructor call)

Etherscan: https://goerli.etherscan.io/tx/0x8bcedf7493c3fcabc13a03090a6ca02ac5df74487e75d03da484b4bedd0863f1

Status: Success
Block: 8916705
From: 0xbc3a67ec1664d540c17aeb8f6bea5ba89adb9e15
To: 0xbf09320746353c9e74e4d3dbb7396d6a87aaa61e

Value: 0
Transaction fee: 0.001581639407378085 ETH
Gas Price: 2.659321445 Gwei 

2 - helloWorld() function: Function that replies with text variable value:
Public view function 
It does not write to the blockchain,  so there is no transaction

Returns the last value set with setText() function, or the default value “Hello World!”

3 - setText() function: Functions that modifies the text variable with a new value:

Etherscan:
https://goerli.etherscan.io/tx/0x2edde07c4f33cc0487ab01b72f4b75988d4aa0d5f69fbb7f20dab982857b3881

Status: Success
Block: 8916741
From: 0xbc3a67ec1664d540c17aeb8f6bea5ba89adb9e15
To: 0xbf09320746353c9e74e4d3dbb7396d6a87aaa61e

Value: 0
Transaction fee: 0.000136805846817584 ETH
Gas Price: 4.579735097 Gwei

4 - transferOwnership() function

https://goerli.etherscan.io/tx/0x80845c91a6a6c8568c8f945d4a4f9751e67dd135d4323ab059d04200c7769bfa


--------------------------------------------------------------------------------------------------------
