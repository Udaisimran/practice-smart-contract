# practice-smart-contract
solidity smart contract
## Mapping smart contract
```
//SPDX-License-Identifier:MIT
pragma solidity ^0.8.26;

contract MapContract {
    mapping ( address => string ) private students ; // Declare state variable to sace the value

    function setStudents (address _addr, string memory _name) public {
     //declare a function to set value for a student  
     students[_addr] = _name;
    }
    
    function getStudent (address _addr) public view returns (string memory) {
        return students[_addr];
    } // declare a function to show the value from state variable

    // function getAllStudents (address[] memory _addresses) public view returns (string[] memory) {
    //     string[] memory _names = new string[](_addresses.length);
    //     for (uint i = 0; i < _addresses.length; i++) {
    //         _names[i] = students[_addresses[i]];
    //     }
    //     return _names;

    function removeStudent (address _addr) public {
        delete students [_addr]; //declare a function to remove the student
    }
}


```



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
