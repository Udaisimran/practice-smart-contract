# practice-smart-contract
solidity smart contract

## Nested mapping practice
this is a nested mapping practice from address to string to bolean
```//SPDX-License-Identifier:MIT
pragma solidity ^0.8.26;

contract NestedMappingPractice {
    mapping (address => mapping (string => bool)) private attendanceSheet;//declare a state variabel as nested mapping datatype
    
    function setAttendance (address _addr, string memory _name, bool _isPresent) public {
        attendanceSheet[_addr][_name] = _isPresent; //set the value in nested mapping
    }//declare a function to set values for a student

    //declare a function to get the values for a student
    function getAttendance ( address _addr, string memory _name) public view returns (bool) {
        return attendanceSheet[_addr][_name];
    }

    //declare the delete function to toggle the value for a student
    function toggleAttendance (address _addr, string memory _name) public {
        attendanceSheet[_addr][_name] = !attendanceSheet[_addr][_name]; // ! is the sign of negation - to make it opposite
    }
}


```


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
