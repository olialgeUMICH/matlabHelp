## Debugging a function

### Breakpoints
Breakpoints can be set in a Matlab script. 

![Image of breakpoint on matlab script](https://github.com/olialgeUMICH/matlabHelp/blob/main/02_Functions/debug1.PNG "")

Copy the script below into your Matlab IDE, and save it as myNewFunc.m: 

```matlab
function outputVar = myNewFunc(inputVar)
% REQUIRES: inputVar is numeric
    disp('This is to practice with the debugger');
    outputVar = helperFunc(inputVar);
end

function helperOut = helperFunc(helperIn)
% REQUIRES: helperIn is numeric
    helperOut = helperIn .^ 2;
end
```

To set a breakpoint, click on the line number next to where you want the function to pause. For this exercise, set a breakpoint on the line 3, which says: `disp('This is to practice with the debugger');`

To see how the breakpoint works, in you Command Window, enter the command `myNewFunc(3)`. This should pause the script and create the screen shown below:

![Image of paused matlab script](https://github.com/olialgeUMICH/matlabHelp/blob/main/02_Functions/debug2.png "")

The green arrow is pointing to the line of code that has yet to be executed. You can use the Step button to step line-by-line through the current function's scope, Step In to enter any called functions, or Step Out to exit the current function's scope. 

In this example, Step once, then Step In on the next line, and you will enter the scope of `helperFunc`:

![Image of matlab script paused in subfunction](https://github.com/olialgeUMICH/matlabHelp/blob/main/02_Functions/debug3.png "")

The outline of an arrow on line 4 shows where you will return to once you have exited the subfunction.

### Try-catch blocks
It's important to be proactive when you're coding to try to prevent misuse of functions or errors. Adding the Requirement in the comments that inputVar be numeric is a good first step. Try running `myNewFunc("a")` to see what happens.

A next important step would be to "catch" a problem before it happens. Matlab uses try-catch blocks, where you can "try" to execute a set of statements, and if an error arises, Matlab will catch it. Here is `myNewFunc()` with a try/catch block added:

```matlab
function outputVar = myNewFunc(inputVar)
% REQUIRES: inputVar is numeric
    disp('This is to practice with the debugger');    
    try
        outputVar = helperFunc(inputVar);
    catch ME
        disp(ME.identifier)
    end
end

function helperOut = helperFunc(helperIn)
% REQUIRES: helperIn is numeric
    helperOut = helperIn .^ 2;
end
```

Here, `ME` is an exception-type variable. You can step through the code to see what the exception class looks like, and what its properties are.

Now, if you were to run `myNewFunc("a")`, tihs shows you that MATLAB raises the "UndefinedFunction" error, because it doesn't expect a string being input to the power operation `.^`. Using try-catch blocks is useful if you want to redirect unexpected inputs to different outputs. For example, you can produce custom error messages:

```matlab
function outputVar = myNewFunc(inputVar)
% REQUIRES: inputVar is numeric
    disp('This is to practice with the debugger');
    
    try
        outputVar = helperFunc(inputVar);
    catch ME
        if strcmp(ME.identifier, 'MATLAB:UndefinedFunction')
            error('myNewFunc expects numeric input')
        end
    end
end

function helperOut = helperFunc(helperIn)
% REQUIRES: helperIn is numeric
    helperOut = helperIn .^ 2;
end
```

This is now a good way to catch string inputs to the function. But what happens if you pass a char input to myNewFunc, such as `myNewFunc('a')`?

Somehow, the try-catch block doesn't catch this error. For this, we can run a different type of test. For example, we can first check that `inputVar` is numeric before we proceed to the try-catch block.

```matlab
function outputVar = myNewFunc(inputVar)
% REQUIRES: inputVar is numeric
    disp('This is to practice with the debugger');
    
    if ~isnumeric(inputVar)
        error('inputVar must be numeric')
    end
    
    try
        outputVar = helperFunc(inputVar);
    catch ME
        if strcmp(ME.identifier, 'MATLAB:UndefinedFunction')
            error('myNewFunc expects numeric input')
        end
    end
end

function helperOut = helperFunc(helperIn)
% REQUIRES: helperIn is numeric
    helperOut = helperIn .^ 2;
end
```
