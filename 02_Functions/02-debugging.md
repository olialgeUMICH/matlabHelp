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

