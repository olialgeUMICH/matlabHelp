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

Like an array, a matrix is created using square brackets and indexed using parentheses.
Rows of the matrix are divided by semicolons `;`, and columns are divided by commas `,` or spaces. 
An example of a matrix:
```matlab
% In matlab, spaces or commas can be used to differentiate the entries in a matrix row,
% so the following statements are equivalient
sample2dMat = [1 2; 3 4];
sample2dMat = [1, 2; 3, 4];
```
Indexing is similar to arrays.
```matlab
% Use '...' to separate lines while scripting. It can help make reading the code easier.
sample2dMat = [1, 2, 3; ...
               4, 5, 6; ...
               7, 8, 9];
sample2dMat(1)
>> ans = 1

sample2dMat(1, 3)
>> ans = 3

sample2dMat(:, 2)
>> ans = 
   2
   5
   8
```

Note, there is more than one operator for multiplication / division involving arrays.
Be sure you are using the correct operator!
For example:
```matlab
rowVec = [1, 2, 3];
colVec = [5; 10; 20];

% Dot product, the following are equivalent
rowVec * colVec;
dot(rowVec, colVec);

% Times/element-wise, the following are equivalent
rowVec .* colVec;
times(rowVec, colVec);
```

#### Exercises
1. Create a 3 x 5 matrix
2. Multiply your 3 x 5 matrix by a scalar
3. Create a 3 x 3 matrix where every value is the same
4. Create a 4 x 4 diagonal matrix
*Challenge*
5. Find three different ways to create the matrix 

| 1 | 0 | 0 |
|---|---|---|
| 0 | 1 | 0 |
| 0 | 0 | 1 |

6. Find three different ways to crate the matrix

| 0 | 0 | 0 |
|---|---|---|
| 0 | 0 | 0 |
| 0 | 0 | 0 |
