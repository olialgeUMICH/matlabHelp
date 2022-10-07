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

