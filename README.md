# Metacrafter_ETH-AVX
## Explaination of Errorhandling_ETH+AVX Code
### Project Short Summary
This is Third Module of Metacrafter Course
We learned Error Handling in Etherium.


## Knowledge of different keywords used in error handling
### require
This is one type of error handling
It has condition which must be satisfies for successfull execution of transaction
In case, this condition fails; it will displays a error message

### revert
This is another type of error handling
Any condition fails, it revert a default error message

### assert
This is third type of error handling
In this type, we uses asuumptions
If assumption is true then execution of next code line of program occurs
In case, our assumption is false, so it will not execute the next line and displays a running ststus of code which clearl states that there is error occured
In this way we encounter the errors.

### pure
pure: You can not read or modify the contract
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


### Code 
 pragma solidity ^0.8.0;


This line indicates that, this code is compatible with 0.8.0 Version of Solodity or more advanced version.


### code                                                                           
contract ErrorHandlingExample {
    uint public totalValue;

Contract name is ErrorhandlingExample in which unsigned integer (uint) titalValue 
is used which is public variable

Public variable is accesseble for inside and outside the world


### code
    function deposit(uint _value) public {
        require(_value > 0, "Value must be greater than zero");
        totalValue += _value;
    }


Function name: deposit which takes the entry of unsigned integer value and this 
is also public variable
here, require keyword is used for **errorhandling**.
Require keyword has condition;
       if the condition under require keyword get satisfied then it wil add particular entered amount in totalValue.
       In case condituon fails then it will **revert** a error message.


  ### code
    function withdraw(uint _value) public {
        require(_value > 0, "Value must be greater than zero");
        require(_value <= totalValue, "Insufficient balance");

        totalValue -= _value;
    }


This withdraw function is same as deposit function but works in opposite manner.
Withdraw takes input as unsigned integer and represent is as public variable
It has two require keywords which demonstrate two different conditions
1) Value must be greater than zero
2) value should be less than or equal to totalValue
Here value is entered amount
If both the coditions get satisfied then amount (value) will be deducted from totalValue.
In case, condition fails then it reverts an error message.


### code
    function divide(uint _numerator, uint _denominator) public pure returns (uint) {
        require(_denominator > 0, "Cannot divide by zero");

        uint result = _numerator / _denominator;
        return result;
    }

Function name: divide which takes input as numerator and denominator as undigned integers. This is public varible but in pure format
pure: You can not read or modify the contract
It has require condtion which states that denominator can not be zero; in case it becomes zero; it will revert as error message.
If this condtion satisfies then result will display as divison.

### code
    function assertExample(uint _value) public pure returns (bool) {
        assert(_value > 0);

        // The following line will never be reached if the assertion fails
        return true;
    }

function name: assertExample which uses assert type of error handling.
assert is assumption where we take a input as integer if this integer > 0 then it will display boolean value "True"
otherwise, it will not pass the value to further line of code and will display as running status of code
This clearly indicates that, there is error in entered value.


### code
    function revertExample() public pure {
        revert("This is a revert example");
    }

This is just an example of revert keyword where transactions will provode error message as _This is a revert example_


### code
    function assertWithMessage() public pure {
        uint a = 10;
        uint b = 5;

        assert(a > b);
        revert("This is an assert example with a revert statement");
    }
}

In this function, we used assert + revert keywords
In this function,
 a > b ; will give proper transaction as we used assert.
 In case our assumption fails then it will revert a error messsage: "This is an assert example with a revert statement"


 ## Author
 **Shruti Narad**
 https://www.linkedin.com/in/shruti-narad-108b08230







