# C# notes (for Unity)
#### These notes are a summary of how to use C# in a Unity context for designing games.

The biggest difference about C# if you're coming from a more high-level language is that _absolutely everything_ needs to be explicitly declared. Variable types, scopes, etc, are not implicitly determined by their values. Instead of saying var `myText = 'test';` you need to tell the program that `myText` is a string.

Let's start by looking at our typical code structure:

```c#
using System.Collections; // namespace
using UnityEngine; // namespace

public class DemoScript: MonoBehaviour {
  // Here we can declare variables and functions
  public String gameText;
  private Int gameScore;

  void Start () {
    // This is the code that runs only when we first run it
  }

  void Update () {
    // This code runs once per frame
  }
}
```
Now, let's break it down into chunks.

### Variables
```c#
  public String gameText;
  private Int gameScore;
```
These are our variables, named `gameText` and `gameScore`. To declare a variable, you need 3 pieces of information:
1. Scope/Visibility
2. Type
3. Name
So in our example above, the visibility would be `public`, the type is a `string`, and the name is `gameText`.

#### Public vs. Private
C# uses `public` and `private` identifiers for variables and classes. If the variable is `public`, it can be accessed from other classes and parts of the code as well. A `private` variable can only be accessed from within the class it belongs to.

### Functions
```c#
  void Start () {
    // This is the code that executes only when we first run it
  }

  void Update () {
    // This code runs once per frame... good for animations or something that needs to run continuously
  }
}
```
**_What the void?!_** These are functions. `void` is the type of the function. It basically just means that the function won't return anything. If you want the function to return an integer, you would use `int` instead of `void`. Other than that, functions are pretty straightforward... they need to be named using a first capital letter, and any parameters that they use go in the parentheses. Also, visibility is optional, so you could put in `public` if you want,  but by default the function is `private` if you don't declare visibility.

Besides `Start` and `Update`, other useful functions include `FixedUpdate` which is used for physics stuff, and `LateUpdate` which is called at the end of a frame. (I'll cover these in depth in another doc)

### Classes
```c#
public class DemoScript: MonoBehaviour {
  // Here we can declare variables
  public String gameText;
  private Int gameScore;
}
```
Classes contain variables and functions. Our class is named `DemoScript`, and it is derived from `MonoBehaviour`. 

`MonoBehaviour`	is the base class for Unity scripts.
, the MonoBehaviour reference provides you with a list of all the functions and events that are available to standard scripts attached to Game Objects. Start here if you’re looking for any kind of interaction or control over individual objects in your game.
Transform	Every Game Object has a position, rotation and scale in space (whether 3D or 2D), and this is represented by the Transform component. As well as providing this information, the transform component
 has many helpful functions which can be used to move, scale, rotate, reparent and manipulate objects, as well as converting coordinates from one space to another.
Rigidbody
 / Rigidbody2D	For most gameplay elements, the physics engine
 provides the easiest set of tools for moving objects around, detecting triggers and collisions
, and applying forces. The Rigidbody class (or its 2D equivalent, Rigidbody2D) provides all the properties and functions you’ll need to play with velocity, mass, drag, force, torque, collision and more.


### Namespaces
```c#
using System.Collections; // namespace
using UnityEngine; // namespace
```
These are our _Namespace Declarations_. Namespaces are useful because they can help us organize different sections of code by preventing clashes between script class names.
Let's say we have one designer working on programming movement of the Player. He uses a class name of `Controller`.
The other designer is tasked with programming Enemy movement. He also uses the class name `Controller`...

This could get very confusing as more and more scripts are added to the game. To keep everyone happy, the programmers should use separate Namespaces for each of their scripts.

```c#
namespace Player {
  public class Controller: MonoBehaviour {
  // variables and functions here belong to the Player namespace.
  }
}

namespace Enemy {
  public class Controller: MonoBehaviour {
  // variables and functions here belong to the Enemy namespace.
  }
}
```
Back to our original declarations:
```c#
using System.Collections; // namespace
using UnityEngine; // namespace
```
This is basically declaring what namespaces we are using. If we wanted to use the Player namespace, we could say `using Player;` or if we wanted a specific class, we'd say `using Enemy.Controller;`.
We just imported the `System.Collections` namespace, which helps define stuff such as lists and dictionaries, as well as the `UnityEngine` namespace, which contains all of the unity classes (eg. `MonoBehaviour`, `Rigidbody`, etc.)


