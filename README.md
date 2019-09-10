# dart-cheat-sheet
A curated list of awesome stuff needed to get started with your flutter development journey

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) ![Branch master](https://img.shields.io/badge/branch-master-brightgreen.svg?style=flat-square)[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/temidtech/dart-cheat-sheet/master/LICENSE)

 ## Table of Contents

- [String interpolation](#string-interpolation)
- [Functions](#functions)
- [Parsing](#parsing)
- [List Arrays](#list-arrays)
- [Lambda Functions](#lambda-functions)
- [Null-aware Operators](#null-aware-operators)
- [Collections Literals](#collections-literals)
- [Arrow Syntax](#arrow-syntax)
- [Iterations](#iterations)
- [Map](#map)
- [Variables](#variables)
- [Class](#class)
- [Properties](#properties)
- [Getters and Setters](#getters-setters)
- [Optional Positional Parameters](#postional-parameters)
- [Redirecting Constructors](#redirecting-constructors)



## String interpolation

Every language has it's own way of interpolating two ore more words or characters. In dart, you can put value of an expression inside a string as follows:

###  Example

 ```dart
    int x=6;
    int y=2;
    String sum = '${x+y}';          // result is 8
    String subtraction = '${x-y}';  // result is 4
    String upperCase = '${"hello".toUpperCase()}'; // result is HELLO
    String concatXY = '$x$y'; // result is '62'
 ```

 ## Functions
Dart lang is an OOL(Object-oriented language), In this language, functions are objects and have a type, Function. This implies that functions can be assigned to 
variables or passed as args to other functions. Interestingly, you can also call an instance of a class as if it were a fuction. That's awesome right?

###  Example

 ```dart
    String fullName(){
        String firstName = "Temidayo";
        String lastName = "Adefioye";
        return '$firstName $lastName'; // returns 'Temidayo Adefioye'
    }
 ```

 ```dart
    int length(String text){
        return text.length; // returns length of text
    }
 ```

 The above function can be rewritten in a more concise way:

  ```dart
    int length(String text) => return text.length; // returns length of text
 ```

 The above approach is applicable where functions contain just ONE expression. This is also referred to as shorthand syntax.

 ## Parsing

Parsing a string to a number such as integer and double is very key. As a developer, often times I need to convert(parse) a string value
coming from a server-side to a number, tryParse method comes in handy. Take a look at this code snippet:

###  Example

 ```dart
    var a = "121";
    var b = "120.56";
    var c = "100.a12";         
    var d = "abc";
    String parseA = int.tryParse(a); // result is 121
    String parseB = double.tryParse(b); // result is 120.56
    String parseC = double.tryParse(c); // result is null (that string contains invalid number)
    String parseD = double.tryParse(d); // result is null (that string contains invalid number)
 ```

  ## List Arrays

Perhaps the most common collection in nearly every programming language is the array or ordered set of objects. Please note that Dart arrays are Lists.

###  Example

 ```dart
    var numList = [1,2,3,5,6,7];
    var countryList = ["Nigeria","United States","United Kingdom","Ghana","IreLand","Germany"];
    String numLength = numList.length; // result is 6
    String countryLength = countryList.length; // result is 6
    String countryIndex = countryList[1]; // result is 'United States'
    String numIndex = numList[0]; // result is 1

    countryList.add("Poland"); // Adds a new item to the list.

    var emailList = new List(3); // Set a fixed list size 
    var emailList = new List<String>(); // instance of a list of type String

 ```

 ## Lambda Functions

Lambda functions provide you with a short and concise way of representing small functions. They are also referred to as Arrow functions. In dart, if you need to write quick throw away functions without necessarily naming them, lambda fucntion is all you need. With the power of this function you can do the following and more:

###  Example

 ```dart
    var numList = new List<int>.generate(5,(i) => i);
    print(numList); //result: {0,1,2,3,4}
    var loans = numList.map( (n) => "\#$n").toList();
    print(loans); // result: {#0, #1, #3, #4}

    printMsg()=> print("Hello world");

    // You can declare a state function this way in flutter
     _DashboardState createState() => _DashboardState(); 

    // How about creating a widget using lambda?
    Card makeCard(Asset assetViewModel) => Card(
          elevation: 8.0,
          margin: new EdgeInsets.symmetric(horizontal: 10.0, vertical: 6.0),
          child: Container(
            decoration: BoxDecoration(color: Colors.white),
            child: makeListTile(assetViewModel), // where makeListTile is a custom widget created already
          ),
    ;


 ```