## Debugging a function
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
