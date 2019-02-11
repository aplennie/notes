# C# notes (for Unity)
#### These notes are a summary of how to use C# in a Unity context for designing games.

Let's start by looking at our typical code structure:

```c#
using System.Collections; // namespace
using UnityEngine; // namespace

public class DemoScript: MonoBehaviour {
  // Here we can declare variables
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
We just imported the System.Collections namespace, which helps define stuff such as lists and dictionaries, as well as the UnityEngine namespace, which contains all of the unity classes (eg. MonoBehaviour, Rigidbody, etc.)

### Classes
```c#
public class DemoScript: MonoBehaviour {
  // Here we can declare variables
  public String gameText;
  private Int gameScore;
}
```

