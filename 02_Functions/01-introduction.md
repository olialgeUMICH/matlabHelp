# Functions

In Matlab, functions are used to apply processes to variables. Matlab's default functions can be searched in the documentation.

## Basic structure of a function
A function has three main components:
1. Input
2. Commands
3. Output

```matlab
function outputVar = simpleFunc(inputVar)
% DESCRIPTION
% Displays inputVar and multiplies it by 2
% REQUIRES
%    inputVar has a display method
% INPUT
%    inputVar: double, variable to display
% OUTPUT
%    outputVar: double, inputVar * 2
    outputVar = inputVar * 2;
    disp(inputVar);
    disp(outputVar);
end
```

In the example, `inputVar` is the input, `outputVar` and the displayed values are output, and the multiplication, variable assignment, and call to `disp()` are the commands.

## Function scope
A function is limited by scope. That is, a function can only access the variables that are directly passed to it via input, or the variables that are assigned within it.
The way that Matlab scripts are structured, a script must have a function that shares the same name as the file name. In the above example, `simpleFunc()` must exist in the script file `simpleFunc.m`.

A script can have more than one function within it. The main function, which has the same name as the script's file name, and any helper/sub-functions existing below the main function. These subfunctions can only be accessed by the main function of the script, and cannot be *directly* accessed by any other scripts.

Take the example below, which exists in the file `myNewFunc.m`:

```matlab
function outputVar = myNewFunc(inputVar)
% REQUIRES: inputVar is numeric
    outputVar = helperFunc(inputVar);
end

function helperOut = helperFunc(helperIn)
% REQUIRES: helperIn is numeric
    helperOut = helperIn .^ 2;
end
```
