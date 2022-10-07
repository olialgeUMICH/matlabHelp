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

