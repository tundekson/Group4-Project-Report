# Group4-Project-Report

1st Weekend Project Report - Group 4 

--------------------------------------------------------------------------------------------------------

HelloWorld.sol Contract -Address: 0xde23104d2914a16053a549cb075bd8811231b2c8


--------------------------------------------------------------------------------------------------------
```
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
```


--------------------------------------------------------------------------------------------------------


REPORT

1 - Contract deployment (constructor call)
```

Etherscan: https://goerli.etherscan.io/tx/0x5c5283d9b01b09fb8771cf99297a10967e16f81c169b33fee201c6da91e024bc

Status: Success
Block: 8916705
From: 0xbc3a67ec1664d540c17aeb8f6bea5ba89adb9e15
To: 0xde23104d2914a16053a549cb075bd8811231b2c8

Value: 0
Transaction fee: 0.007613070040511416 ETH
Gas Price: 11.579928097 Gwei 
```

2 - helloWorld() function: 
```
Function that replies with text variable value:
Public view function 
It does not write to the blockchain,  so there is no transaction

Returns the last value set with setText() function, or the default value “Hello World!”
```

3 - setText() function: Functions that modifies the text variable with a new value:
```
Etherscan:
https://goerli.etherscan.io/tx/0x2edde07c4f33cc0487ab01b72f4b75988d4aa0d5f69fbb7f20dab982857b3881

Status: Success
Block: 8916741
From: 0x5ee85c2890c2201ff9e28dedb70f38aacc775eb4
To: 0xde23104d2914a16053a549cb075bd8811231b2c8

Value: 0
Transaction fee: 0.000346763374275856 ETH
Gas Price: 11.608307923 Gwei Gwei

Input data:
Function: setText(string _text) ***

MethodID: 0x5d3a1f9d
[0]:  0000000000000000000000000000000000000000000000000000000000000020
[1]:  000000000000000000000000000000000000000000000000000000000000000d
[2]:  48656c6c6f2047726f7570203400000000000000000000000000000000000000
```

4 - transferOwnership() function

```
Etherscan:
https://goerli.etherscan.io/tx/0x04d00d994e99356ffda46fb8d1098cec30184ad016fb44a0b7d19cbe09f91ace

Status: Success
From: 0xbc3a67ec1664d540c17aeb8f6bea5ba89adb9e15
To: 0xde23104d2914a16053a549cb075bd8811231b2c8

Value: 0
Transaction fee: 0.000280743776783668 ETH
Gas Price: 11.579928097 Gwei

Input data:
Function: transferOwnership(address _newOwner) ***

MethodID: 0xf2fde38b
[0]:  0000000000000000000000005ee85c2890c2201ff9e28dedb70f38aacc775eb4

```

