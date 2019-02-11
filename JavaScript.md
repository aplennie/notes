### Javascript/ES6
Firstly, <br>
`var myVar = 'test';` this is called *declaring* a variable <br>
`myVar = 'test2';` this is called *updating* a variable

There are subtle differences between using var, let and const. https://wesbos.com/let-vs-const/

    Var: globally scoped, can be easily redeclared and updated, will never throw an error when being redeclared

    Let: block scoped, can only be declared once [within its scope], can be updated within its scope

    Const: block scoped, cannot be redeclared or updated (most stubborn of the 3!)
