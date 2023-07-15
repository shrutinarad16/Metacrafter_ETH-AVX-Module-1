# Metacrafter_ETH-AVX
## Explaination of Errorhandling_ETH+AVX Code
### Project Short Summary
This is Third Module of Metacrafter Course
We learnt Error Handling in Etherium.

# Code
### To run this code, you have to use ONLINE REMIX IDE Platform

// SPDX-License-Identifier: MIT

pragma solidity ^0.8.0;

contract ErrorHandlingExample {
    uint public totalValue;

    function deposit(uint _value) public {
        require(_value > 0, "Value must be greater than zero");
        totalValue += _value;

    }

    function withdraw(uint _value) public {
        require(_value > 0, "Value must be greater than zero");
        require(_value <= totalValue, "Insufficient balance");

        totalValue -= _value;
    }

    function divide(uint _numerator, uint _denominator) public pure returns (uint) {
        require(_denominator > 0, "Cannot divide by zero");

        uint result = _numerator / _denominator;
        return result;
    }

    function assertExample(uint _value) public pure returns (bool) {
        assert(_value > 0);

        // The following line will never be reached if the assertion fails
        return true;
    }

    function revertExample() public pure {
        revert("This is a revert example");
    }

    function assertWithMessage() public pure {
        uint a = 10;
        uint b = 5;

        assert(a > b);
        revert("This is an assert example with a revert statement");
    }
}

## Explaination of Each portion of Code

**This line indicates that, this code is compatible with 0.8.0 Version of Solodity or more advanced version.**

Code                                                                             pragma solidity ^0.8.0;


**Contract name is ErrorhandlingExample in which unsigned integer (uint) titalValue is used which is public variable
Public variable is accesseble for inside and outside the world**

code                                                                           
contract ErrorHandlingExample {                                                    uint public totalValue;


code                                                                           function deposit(uint _value) public {                                                   require(_value > 0, "Value must be greater than zero");                    totalValue += _value;                                                                  }

    Function name: deposite which takes the entry of unsigned integer value and this is also public variable
    here, require keyword is used for **errorhandling**.
    Require keyword has condition;
       if the condition under require keyword get satisfied then it wil add particular entered amount in totalValue.
       In case condituon fails then it will **revert** a error message.


  
  **function withdraw(uint _value) public {
        require(_value > 0, "Value must be greater than zero");
        require(_value <= totalValue, "Insufficient balance");

        totalValue -= _value;
    }**






