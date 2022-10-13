# Introduction

## Notes about MATLAB
Matlab is a scripting language, so if you’re more familiar with object-oriented programming, it may seem a bit off-putting at first. 
For example, MATLAB scripts do not need to be compiled, they can be run on-the-fly, which is especially convenient for debugging. 
Generally, you will be writing and running MATLAB code in the MATLAB integrated development environment (IDE), though in the future, you may run MATLAB code from the command line. 

One major thing to note about MATLAB is how it handles namespaces. 
If you’re familiar with C++, R, or Python, you’ve probably included packages or namespaces in a project before. 
MATLAB does allow you to integrate code from other projects/repositories by adding them to your Path, but it does not treat them as separate packages. 
For example, if you wrote a simple function in your working directory like `findMean.m` to compute an arithmetic mean, but another lab member created a `findMean.m` in BCIL-Shared to compute the geometric mean, you cannot directly specify `BCIL-Shared::findMean()` or `myCode::findMean()` if you want to use both functions in the same script. 
Instead, your current directory determines which `findMean()` gets called; if you’re in your personal directory, it’s the arithmetic version, and if your current directory is the BCIL-Shared repository, it’s the geometric. 
Keep this in mind when writing/editing.

## The MATLAB IDE
This is a view of how I have my editor set up:

<img src="https://github.com/olialgeUMICH/matlabHelp/blob/main/introduction/ide1.png" 
alt="Image of Matlab IDE" border="10" />

The editor is broken into several panels. There are the panels I use most often:

### Current Folder Panel
<img src="https://github.com/olialgeUMICH/matlabHelp/blob/main/introduction/ide2.png" 
alt="Image of Current Folder Panel" border="10" />
Shows the current working directory. 
If you select the view option “Indicate Files not on Path”, only the files in the current working directory and those directories added to the path will be highlighted.

### Command Window
<img src="https://github.com/olialgeUMICH/matlabHelp/blob/main/introduction/ide3.png" 
alt="Image of Matlab Command Window" border="10" />
Shows commands that are run.
Statements followed by a semicolon have their output suppressed.
If you want to run a line from the script panel, select the line and then press the F9 function key.

### Script Panel
<img src="https://github.com/olialgeUMICH/matlabHelp/blob/main/introduction/ide4.png" 
alt="Image of Matlab Script Panel" border="10" />
Shows the script you are currently editing, and allows you to mark breakpoints on lines for debugging.

### Workspace Panel
<img src="https://github.com/olialgeUMICH/matlabHelp/blob/main/introduction/ide5.png" 
alt="Image of Workspace Panel" border="10" />
Shows which variables are in your current environment.
Very helpful when stepping through code!

### Toolstrip / Command Ribbon
<img src="https://github.com/olialgeUMICH/matlabHelp/blob/main/introduction/ide6.png" 
alt="Image of Command Ribbon set to the Home tab" border="10" />
Quick access to command commands. The tabs I use most often are "Home", which I use for changing the layout, editing preferences, or installing Add-Ons, 

<img src="https://github.com/olialgeUMICH/matlabHelp/blob/main/introduction/ide7.png" 
alt="Image of Command Ribbon set to the Editor tab" border="10" />
and "Editor", which I use when editing or debugging.

### Documentation Window
<img src="https://github.com/olialgeUMICH/matlabHelp/blob/main/introduction/ide8.png" 
alt="Image of Documentation Window" border="10" />
By typing `doc` into the command window, you can open Matlab's documentation.
If you type `doc <term>`, this searches the documentation for the specified term.

#### Exercises
1. Get a feel for the IDE and arrange the panels in a way that feels comfortable to you.
2. Find where to change your editor window's font size.
3. Add and then remove a directory from your Matlab PATH
4. Find the MATLAB documentation for creating a bar plot
5. Using the MATLAB documentation, find two different ways to transpose a vector

*Challenge*

6. Find the Matlab documentation for the operator '==' (example: 2 + 2 == 4) 
7. Find the formula for a Support Vector Machine Classifier's box constraint using the Matlab documentation.
