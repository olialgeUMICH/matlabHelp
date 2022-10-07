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
