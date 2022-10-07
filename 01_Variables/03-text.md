## Text 
There are three main types of text used in MATLAB. 
These are strings, which are assigned using double quotes (“this is a string”), character vectors or char which are assigned using single quotes (‘this is a char’), and cellstring or cellstr, which are a subset of the cell structure and are assigned using curly braces and single quotes ({‘this is a cellstr’}). 
When dealing with text in MATLAB, it’s good practice to limit how many different text types you’re using. 

Each text type has different properties. Cellstrings and strings can be concatenated into arrays, while chars will add whitespsace when concatenated, for example. 
On the other hand, it’s easier to access the individual characters in a char than cellstr or string. 
Experiment with this sample code:
```matlab
aChar = 'a';
bString = "string";
cCell = {'cellstr'};

% Indexing
aChar(1)
bString(1)
cCell(1)

% Addition
aChar + aChar
bString + bString
cCell + cCell  % this raises an error -- think about why

% Brackets / Appending
% Notice how the text types cast when they're joined!
[aChar, aChar]
[bString, bString]
[cCell, cCell]
[aChar, bString]
[aChar, cCell]
[bString, cCell]

% Cell Structure
{cCell, bString, aChar}

```
