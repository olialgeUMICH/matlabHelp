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
