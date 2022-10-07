## Structures
### Struct
Structured data types are helpful when you need to store multiple pieces of information about some element, but an array or matrix isn’t suitable. 
A common example is identification. 
Take the example of lab member. 
Some information you may want to include about a lab member are: name, number of years in the lab, how many projects they’re working on, whether or not the lab member is a student or faculty, their office address, and their email. 
One way of grouping this information together is to put it into a struct:

```matlab
labMember.name = "Alpha Bravo";
labMember.nYears = 4;
labMember.nProjects = 2;
labMember.isFaculty = true;
labMember.isStudent = false;
labMember.office = "Building A, Room 123";
labMember.email = "alpha_bravo@example.com";
>> labMember
  struct with fields:
     name: "Alpha Bravo"
     nYears: 4
     nProjects: 2
     isFaculty: 1
     isStudent: 0
     office: "Building A, Room 123"
     email: "alpha_bravo@example.com"
```

Creating another lab member with the same fields and then concatenating the two in an array is one method of creating a larger structure of structs.

```matlab
% Two structs must have the same fields to be concatenated
labMember1.name = "Charlie Delta";
labMember1.nYears = 1;
labMember1.nProjects = 1;
labMember1.isFaculty = false;
labMember1.isStudent = true;
labMember1.office = "Building A, Room 123-1";
labMember1.email = "cDelta@example.com";
structOfStructs = [labMember; labMember1]
>> structOfStructs = 
     2x1 struct array with fields:
     
     name
     nYears
     nProjects
     isFaculty
     isStudent
     office
     email
```

You access the fields of a struct by dot-indexing

```matlab
labMember1.name
>> ans = "Charlie Delta"

structOfStructs(1).name
>> ans = "Alpha Bravo"
```

### Table
A table is a different structured data type, with many customization options.
While structs are useful to get all the information about a particular entry, tables are useful to get multiple data pieces among multiple entries, similar to an Excel sheet. 
Tables can be initialized by grouping variables, like the following:
```matlab
names = ["Alpha Bravo"; "Charlie Delta"];
nYears = [4; 1];
nProjects = [2; 1];
isFaculty = [true; false];
isStudent = [false; true];
offices = ["A-123"; "A-123-1"];
emails = ["alpha_bravo@example.com"; "cDelta@example.com"];
labMemberTable = table(names, nYears, nProjects, isFaculty, isStudent, offices, emails)
>>labMemberTable =

  2×7 table

         names         nYears    nProjects    isFaculty    isStudent     offices         emails          
    _______________    ______    _________    _________    _________    _________    ______________

    "Alpha Bravo"        4           2          true         false      "A-123"      "alpha_bravo@example.com"
    "Charlie Delta"      1           1          false        true       "A-123-1"    "cDelta@example.com"     

```

You can add a new entry to the table by creating a smaller table and concatenating it:
```matlab
% Tables being concatenated need the same variable names
labMember2 = table("Echo Foxtrot", 3, 2, false, false, "B-1", "echo1990@example.com" , …
                   'VariableNames', labMemberTable.Properties.VariableNames);
labMemberTable = [labMemberTable; labMember2];
```

To add a new field to the table, you can use the dot operator:
```matlab
isPostdoc = [false; false; true];
labMemberTable.isPostdoc = isPostdoc;
```
To access a row or column of the table and have it retain table format, use parentheses. 
To obtain the values of the table and have them in their original format (cell, string, numeric, etc.), use curly braces or dot indexing.
```matlab
% Different ways of accessing table values
% Array
yearIndex = 2;  % Use variables, not magic numbers!
labMemberTable.nYears
labMemberTable{:, 'nYears'}
labMemberTable{:, yearIndex}

% Table
labMemberTable(:, 'nYears')
labMemberTable(:, yearIndex)
```

### Cells
Cells are similar to tables in how they can be indexed, buy curly braces are used instead of parentheses.
