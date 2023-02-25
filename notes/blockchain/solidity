pragma solidity ^0.4.24;


The contractor oriented language was basically means that the smart contracts are the main way that you organize code and like stored data in my audio programming life And the high level language for able to be smart contracts looks a lot like javascript and you know python and C++ And you see right here And it's used to run on your theory and virtual machine It was basically you know a thing that runs the codeso something is a statly type as opposed to type language And it supports it like inheritance libraries and what other stuff So enough I'm talking about solidity Let's actually jump in and start riding some solidity code This is a website that allows you to write solidity smart contracts in your browser

https://remix.ethereum.org/

install 2 plugins in vscode if uare usingvs code 

1)solidity by juan blanco (optional)
2)remix

you can also install remix in existing code editor such as vscode as a extension

first smart contract:

u will have some basic folders and files do use web ide for now folders are contractscripts test read me the text a JSM file etc etc

----------------------------code----------------------------------------------------------

pragma solidity ^0.4.24;
contract testcon{
    
    //declar global variables and function
    string value;
    
    //constructor declaration
    constructor() public{
        value="hello"; 
    }
    
    //function declaration
    function get() public view returns(string){ 
        return value;

    }
    
    function set(string _value)public{
        value = _value;
        //function local variable
    }
}

------------------------------------------------------------------------------------------

pragma solidity ^0.4.24; -- this is the version of the solidity used here ^ represents higher than 0.4.24

note: the smart contract which you are going to type is going to be fully online so anyone can read it anyone can use it and etc

contract testcon{
    string value;
}

in deploy section you can send the arguments for the constructor

contract is similar to class but here is called as contract and it is an object on its own

    string value;

datatype and variables solidity is a statically typed language so evey variable u create is stored in blockchain

the variables are not local it will be stored in blockchain and will repesent as the contract variable

to declar a function u can use the keyword function

eg:

    function get() public returns(string){ 
        return value;

    }
    function set(string _value)public{
        value = _value;
        //function local variable and the local variable is _value
    }

where get() and set() are function same as other languages function

public represents acceseblity public means anyone can access form any contract

returns(datatype) this represents what data type will it return

constructors:

they are automatically ran when the contract is called or the contract gets the scope constructor are called with constructor keyword

in web ide after typing the code select the compiler and compile it by selecting a sutable vm deploy after deploying u will see a new test node running click on it to access the fuctionality

to run in remix vscode extention dee the remic tutorial and ganache tutorial

for the solidity above the version 0.5.1 code :

------------------------------------------------------------------------------------------

pragma solidity 0.5.1;
contract testcon{
    
    //declar global variables and function
    string value;
    
    //constructor declaration
    constructor() public{
        value="hello"; 
    }
    
    //function declaration
    function get() public view returns(string memory){ 
        return value;

    }
    
    function set(string memory _value)public{
        value = _value;
        //function local variable
    }
}

------------------------------------------------------------------------------------------

note this may not work in new versions due to changes

if u declare your variables to be public then u can see the values directly

eg: this code can be replaced

    string value;
    
    //constructor declaration
    constructor() public{
        value="hello"; 
    }
    
    //function declaration
    function get() public view returns(string memory){ 
        return value;

    }

    with this

    string public value = "hello"

    this will create a new button by which u can access the value of value (variable)

    
declaration of different datatypes
_________________________________________________________________________________________

pragma solidity 0.5.1;

contract Mycont{
    string public stringv="string";
    bool public boolv=false;
    // int normal integer values can be stored
    // int8 only 8 bytes of integer can be stored
    // uint unsigned integer no + or - can be represented
    // uint122 etc only 122 bytes of unsigned integer can be stored
    int112 public intv=123;
}

_________________________________________________________________________________________

-----------------------------------enum program------------------------------------------
pragma solidity 0.5.1;

contract mycon{
    enum state{wait,ready,active}
    state public status;
    constructor()public{
        status=state.wait;//option 0 is assign
    }
    function activate() public{
        status=state.active;//assigning the 2nd option
    }
    function isactive()public view returns(bool){
        return status == state.active;
    }
}
-----------------------------------------------------------------------------------------
in this program u can see a key word called enum which is used for coustom user object and its states

here u can see 3 states wait ready active and run this to see the working

----------------------------------user data allocation using struct-----------------------

this struct is as same as in the c programing language used to declare the objects

simple usage is 

___________________________________________________________________________________________
pragma solidity 0.5.1;

contract mycontract{

    person[] public people; // declaration of object the length of the object is not assigned

    uint256 public peoplecount; //keeping track of number of items

    struct person{  //object structure declaration

        string firstname;
        string lastname;

    }

    function addperson(string memory firstname,string memory lastname)public{

        people.push(person(firstname,lastname)); // push is a method to add data in a array and that object is an array
        peoplecount ++;
        
    }

}

_______________________________________________________________________________________________

the above program can be also be returend as dynamic mapping using pointers :

__________________________________________________________________________________________
pragma solidity 0.5.1;

contract mycontract{

    uint256 public peoplecount;
    mapping(uint => person)public people; //creating a mapping functrion

    struct person{

        uint id;
        string firstname;
        string lastname;

    }

    function addperson(string memory firstname,string memory lastname)public{
        
        peoplecount ++;
        people[peoplecount]=(person(peoplecount,firstname,lastname));
        
    }

}
__________________________________________________________________________________________
note: the mapping code will not show any error it will show the default values with is nothing or zero
-----------------------------------------------------------------------------------------

now we are going to lok about the acess modifiers
 
types of acess 

1) external − External functions are meant to be called by other contracts. They cannot be used for internal call. To call external function within contract this.function_name() call is required. State variables cannot be marked as external.

2) public − Public functions/ Variables can be used both externally and internally. For public state variable, Solidity automatically creates a getter function.

3) internal − Internal functions/ Variables can only be used internally or by derived contracts.

4) private − Private functions/ Variables can only be used internally and not even by derived contracts.

there is a datatype called address where all address is stored

syntax:

address owner;

_________________________________________modifiers______________________________________________

Function modifier can be executed before or after the function executes its code. The modifiers can be used when there is a need to verify the condition automatically before executing a particular function. If the given condition is not satisfied, then the function will not get executed.

more on modifiers: https://medium.com/coinmonks/solidity-tutorial-all-about-modifiers-a86cf81c14cb

syntax:
modifier method_name() {
action block;
}

require() ------ this is like if in solidity but ot if it throws an error if the given condition is not matching

syntax:
require(msg.sender == owner);

msg is a built in variable which has the details of the user who is using the contract

for more msg details and how to get different details look this https://medium.com/upstate-interactive/what-you-need-to-know-about-msg-global-variables-in-solidity-566f1e83cc69

----------------------------------------code-----------------------------------------------

//sample snippet (part of code )

address owner;

modifier onlyOwner(){
    require(msg.sender == owner);
    -; // this is where the called function will join itself and "-;" represents that
}

constructor() public{
    owner=msg.sender;//this will store the first user's address and the onlyowner method will compare it
}

function addperson(string memory firstname,string memory lastname) public onlyOwner {
    peoplecount++;
}

-----------------------------------------------------------------------------------------------------------------------------

the above program takes the first person address who runs this program first time and each time compares it with the next transactions  

------------------------------------------------time in solidity----------------------------------

so the solidity uses the time stamp so only unix epoch time is stable and only we can represent time in seconds for clock or convertor use this epochconverter.com/clock

there is another global variable like msg called block where u can get the current block details for more information docs.soliditylang.org/en/v0.8.17/units-and-global-variables.html

to get the current block time stamp use 

#block.timestamp // this returns time stamp

payable - this is a keyword represented to a variable or function which can transfer funds from one wallet to another

syntax as eg:

address payable wallet;

(or)

function buytoken() public payable{

}

---------------------------------------making a contract for transaction--------------------------------

____________________________________program_______________________________________________

//this program here we will get the wallet address and increment a value in return we will dudect the amount from his wallet as much as the msg execution value 
//we will call msg.value for message prossing value deduction

pragma solidity 0.5.1;

contract mycontract {
    mapping(address => uint) public balance;
    address payable wallet;

    constructor(address payable _wallet)public{
        wallet=_wallet;
    }

    function buytoken()public payable{
        // buy a token eg not actuall token we are just incrementing a pointing value
        balance[msg.sender]+=1;
        // send ether to the wallet 
        //before deploying we need to assign the value in eather that is need to be transfered
        wallet.transfer(msg.value);
        //msg.value is got from value column from the ide
    }
}

//transfer is a built in function used to transfer coins from the current user
_________________________________________________________________________________________________

-----------------------------------event__________________________________________________

event is like a fuction that is used to produce temporovary variables that can be called and used only once and they cannot be modified or reused 

eg:cooment section in the youtube the data is only accessed once but u can create a new comment like that event is also 

syntax:

event <eventName>(parameters) ;    
//emit
emit <eventName>(parameters);

eg:

// Solidity program to demonstrate
// creating an event
pragma solidity ^0.4.21;

// Creating a contract
contract eventExample {

	// Declaring state variables
	uint256 public value = 0;

	// Declaring an event
	event Increment(address owner);

	// Defining a function for logging event
	function getValue(uint _a, uint _b) public {
		emit Increment(msg.sender);
		value = _a + _b;
	}
}

------------------------------------------------------------------------------------------

event logs :

logs [
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0xfc3a67c9f0b5967ae4041ed898b05ec1fa49d2a3c22336247201d71be6f97120",
		"event": "Increment",
		"args": {
			"0": "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4",
			"owner": "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4"
		}
	}
]

------------------------------------------------------------------------------------------

we can also index event based on name sno etc so that we can sort it when need or filter a specific event when required ,We can add atmost 3 indexes in one event. 

eg code with index in events:

// SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.7.0 <0.9.0;


contract IndexEvents {

	event NewTrade(
		uint256 indexed date,
		address from,
		address indexed to,
		uint256 indexed amount
	);

	function trade(address to, uint256 amount) external {
		emit NewTrade(block.timestamp, msg.sender, to,amount);
	}
}

-----------------------------------------------------------------------------------------

event logs on running :

logs [
	{
		"from": "0xcD6a42782d230D7c13A74ddec5dD140e55499Df9",
		"topic": "0xa6b5ddd331f9dc412a8c258207b1c66f53c1740c72628d9913aafcb6b28d8f73",
		"event": "NewTrade",
		"args": {
			"0": "1655406115",
			"1": "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4",
			"2": "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2",
			"3": "1234",
			"date": "1655406115",
			"from": "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4",
			"to": "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2",
			"amount": "1234"
		}
	}
]

//for more about about events : 

1)geeksforgeeks.org/what-are-events-in-solidity/
2)https://www.youtube.com/watch?v=nopo9KwwRg4
3)tutorialspoint.com/solidity/solidity_events.htm

//in order to use a event u need emit function and the usage can be seen in the above programs
_________________________________________________________________________________________

---------------------------------working with multiple smart contracts--------------------
to connect two or more smart contracts we will use the adress of those contracts 

eg linking of 2 contracts:

contract Counter {

    uint public number;

   

    function increment() external {

        number += 1;

    }

}

contract CounterCaller {





    constructor(address counterAddress) {

        //note while deploying the contract make sure that u provide the another contract address of deployment here

        Counter myCounter = Counter(address(counterAddress));
        
    }




    function counterIncrement() external {

        myCounter.increment();
        //u can also directly call the function without declaring it by 
        //Counter(address(counterAddress)).increment();

    }

}

//insted of msg.sender u can use tx.origin to find who intiated the smart contract
//tx. origin is a global variable in Solidity which returns the address of the account that sent the transaction. Using the variable for authorization could make a contract vulnerable if an authorized account calls into a malicious contract.

----------------------------------inheretance of smart contracts---------------------------

https://www.geeksforgeeks.org/solidity-inheritance/

eg :

// Solidity program to
// demonstrate
// Single Inheritance
pragma solidity >=0.4.22 <0.6.0;

// Defining contract
contract parent{

	// Declaring internal
	// state variable
	uint internal sum;
	
	// Defining external function
	// to set value of internal
	// state variable sum
	function setValue() external {
		uint a = 10;
		uint b = 20;
		sum = a + b;
	}
}

// Defining child contract
contract child is parent{
	
	// Defining external function
	// to return value of
	// internal state variable sum
	function getValue() external view returns(uint) {
		return sum;
	}
}

// Defining calling contract
contract caller {

	// Creating child contract object
	child cc = new child();
	
	// Defining function to call
	// setValue and getValue functions
	function testInheritance() public returns (uint) {
		cc.setValue();
		return cc.getValue();
	}
}

you can also inherete multiple contracts eg:

// Solidity program to
// demonstrate Multi-Level
// Inheritance
pragma solidity >=0.4.22 <0.6.0;

// Defining parent contract A
contract A {

	// Declaring state variables
	string internal x;
	string a = "Geeks" ;
	string b = "For";

	// Defining external function
	// to return concatenated string
	function getA() external{
		x = string(abi.encodePacked(a, b));
	}
}

// Defining child contract B
// inheriting parent contract A
contract B is A {

	// Declaring state variables
	// of child contract B
	string public y;
	string c = "Geeks";

	// Defining external function to
	// return concatenated string
	function getB() external payable returns(
	string memory){
		y = string(abi.encodePacked(x, c));
	}
}

// Defining child contract C
// inheriting parent contract A
contract C is B {
	
	// Defining external function
	// returning concatenated string
	// generated in child contract B
	function getC() external view returns(
	string memory){
		return y;
	}
}

// Defining calling contract
contract caller {

	// Creating object of child C
	C cc = new C();

	// Defining public function to
	// return final concatenated string
	function testInheritance(
	) public returns (
	string memory) {
		cc.getA();
		cc.getB();
		return cc.getC();
	}
}

other types of inheretance checkout https://www.geeksforgeeks.org/solidity-inheritance/

u can call the super class functions using the keyword super.function();

----------------------libraries and math functions-----------------------------------------

for more knowlege:https://coinsbench.com/solidity-101-introduction-to-libraries-in-solidity-b4555f2e0066#:~:text=A%20library%20in%20Solidity%20is,deploying%20a%20contract%20consumes%20gas.

mathutils.sol:

pragma solidity ^0.8.0;
library MathUtils {
    function add(uint a, uint b) public pure returns(uint) {
        return a + b;
    }
}

main.sol:

pragma solidity ^0.8.0;
import "./MathUtils.sol";
contract Calculator  {
    function getSum(uint firstNumber, uint secondNumber) public pure returns(uint) {
        // Invoke and return the library function here ...
    }
}

u can also use require to satisfy a particular type of condition if required returns false the library will kick out

if the library is in same file then remove ./

eg for divide non zero can be avoided by :

require(b>0);
uint c = a/ b;

for same maths operations use this git library:

https://github.com/OpenZeppelin/openzeppelin-contracts/blob/master/contracts/utils/math/SafeMath.sol

----------------using---------------

using is used for including a library within a contract in solidity. Check this following example:

pragma solidity ^0.4.15;
library SomeLibrary  {
 function add(uint self, uint b) returns (uint) {
   return self+b;
 }
}
contract SomeContract {
    
    using SomeLibrary for uint;
    
    function add3(uint number) returns (uint) {
        return number.add(3);    
        //here number will be taken as 1st aregument and 3 will be 2nd argument
    }
}

// u can directly call library for the particular datatype using keyword "using"



last seen finish https://www.youtube.com/watch?v=ipwxYa-F1uY




