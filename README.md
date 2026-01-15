# practice-smart-contract
hashing solidity smart contract

## First smart contract practice
```solidity
//SPDX-License-Identifier: MIT
pragma solidity ^0.8.26;

//this is the contract to has strings using keccak256
contract HashString{
    bytes32 private mystring;

    function hashing (string memory _str) public {
        mystring = keccak256(bytes(_str));//hashing the string
    }
        function getDigest () public view returns (bytes32) {
            return mystring;//get the digest of the hashing process
        }
    
}

```
