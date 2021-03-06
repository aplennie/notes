# C-sharp Notes

#### These are notes that I took while going through a beginner C# course on Lynda.com (https://www.lynda.com/C-tutorials/Learning-C/651201-2.html)
Note: I didn't take notes on most of the basic stuff as I felt it's kinda redundant, also see my other notes (C-sharp-Unity)
## Basics
```c#
Console.WriteLine("I will be outputted to the console");
Console.ReadLine(); // reads a value from user input in console.

// to convert a string to an integer:
var myVar = int.Parse("5");
// this is useful because user input from the console will always arrive in string form.
```

### Arrays:
To initialize an array and fill it with values, we can write:
```c#
var myArray = new int[10] { 1,2,3,4,5,6,7,8,9,10 }; // it is a new array of 10 integers.
```
We don't need to specify that the array will have 10 values. It's actually better to leave the `[]` blank in case you want to add more values to the array.

#### Foreach loops:
These are useful for looping over arrays, and they are easier to use than for or while loops.
```c#
foreach (var item in collection)
{
 // do something here
}
```
#### Switch statements:
```c#
switch(years) // years is the variable we are checking
{
 case 0:
  Console.WriteLine("Inexperienced");
  break; // let our program know we want to move to the next case
 case 1:
  Console.WriteLine("Junior");
  break;
 case 2:
  Console.WriteLine("Intermediate");
  break;
 case 3:
  Console.WriteLine("Advanced");
  break;
 default:
  Console.WriteLine("Senior");
  break;
}
```
