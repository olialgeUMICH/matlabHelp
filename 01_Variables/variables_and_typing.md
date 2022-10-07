# Variables and Typing
Unlike C++, you do not have to declare types in Matlab.
Like Python or R, types can change.
For example, it is valid (but unwise) to write and execute the following:

```matlab
a = "Something";
disp(a);
>> Something
a = 5;
disp(a);
>> 5
```

So do be careful if you are changing the type of a variable!

The most common types you will use in Matlab are:

* Numeric
  * Double
    * Array
    * Matrix
  * Integer
* Logical
* Text
  * String
  * Char
  * Cellstr
* Structures
  * Struct
  * Table
  * Cell

## Numeric
This is the variable type you will most often be using.
Occasionally, you may use integers, but doubles are what you will use the majority of the time.
A double is the defaut numeric variable for Matlab.
Initializing a double is as simple as calling:

```matlab
doubleVar = 1;
```
### Array
An array of doubles is created by using square brackets or a colon.
For example:

```matlab
doubleVal = [1, 2, 3]
>> doubleVal = 
   1  2  3
doubleVal = 1:3
>> doubleVal = 
   1  2  3
```
Note: Matlab arrays are 1-indexed, meaning that the first entry in an array is accessed using the value `1`. 

Using the colon `:` creates a range of values. 
You can add a step to the range by putting a value between the start and end of your range.

```matlab
doubleEvens = 0:2:10
>> doubleEvens = 
   0  2  4  6  8  10
```

Arrays are indexed using parentheses.
For example, if I want to select the first value of `doubleEvens`, I would call:
```matlab
doubleEvens(1)
>> ans = 
   0
```

### Matrix
