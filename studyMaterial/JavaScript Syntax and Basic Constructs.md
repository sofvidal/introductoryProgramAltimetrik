# JavaScript Syntax and Basic Constructs

JavaScript is case-sensitive and uses the Unicode character set. 
Instructions are called statements and are separated by semicolons (;).
The syntax of comments is the same as in C++ and in many other languages:

// a one line comment 

/* this is a longer, 
 * multi-line comment
 */ 


JavaScript has three kinds of variable declarations.

var

Declares a variable, optionally initializing it to a value.

let

Declares a block-scoped, local variable, optionally initializing it to a value.

const

Declares a block-scoped, read-only named constant.

Variables are used as symbolic names for values in your application. The names of variables, called identifiers, conform to certain rules. A JavaScript identifier usually starts with a letter, underscore (_), or dollar sign ($). Subsequent characters can also be digits (0 – 9). Because JavaScript is case sensitive, letters include the characters A through Z (uppercase) as well as a through z (lowercase). Most of ISO 8859-1 or Unicode letters such as å and ü can be used in identifiers.

They can be declared in two ways:

With the keyword var. For example, var x = 42. This syntax can be used to declare both local and global variables, depending on the execution context.

With the keyword const or let. For example, let y = 13. This syntax can be used to declare a block-scope local variable. (See Variable scope below.)

Variables should always be declared before they are used. JavaScript used to allow assigning to undeclared variables, which creates an undeclared global variable. This is an error in strict mode and should be avoided altogether.

In a statement like let x = 42, the let x part is called a declaration, and the = 42 part is called an initializer. The declaration allows the variable to be accessed later in code without throwing a ReferenceError, while the initializer assigns a value to the variable. In var and let declarations, the initializer is optional. If a variable is declared without an initializer, it is assigned the value undefined.

const declarations always need an initializer, because they forbid any kind of assignment after declaration, and implicitly initializing it with undefined is likely a programmer mistake.

A variable may belong to one of the following scopes:
Global scope: The default scope for all code running in script mode.
Module scope: The scope for code running in module mode.
Function scope: The scope created with a function.
In addition, variables declared with let or const can belong to an additional scope:
Block scope: The scope created with a pair of curly braces (a block).
When you declare a variable outside of any function, it is called a global variable, because it is available to any other code in the current document. When you declare a variable within a function, it is called a local variable, because it is available only within that function.
let and const declarations can also be scoped to the block statement that they are declared in.
However, variables created with var are not block-scoped, but only local to the function (or global scope) that the block resides within.
var-declared variables are hoisted, meaning you can refer to the variable anywhere in its scope, even if its declaration isn't reached yet. You can see var declarations as being "lifted" to the top of its function or global scope. However, if you access a variable before it's declared, the value is always undefined, because only its declaration is hoisted, but not its initialization.
Because of hoisting, all var statements in a function should be placed as near to the top of the function as possible. This best practice increases the clarity of the code.

Whether let and const are hoisted is a matter of definition debate. Referencing the variable in the block before the variable declaration always results in a ReferenceError, because the variable is in a "temporal dead zone" from the start of the block until the declaration is processed.
Unlike var declarations, which only hoist the declaration but not its value, function declarations are hoisted entirely — you can safely call the function anywhere in its scope. See the hoisting glossary entry for more discussion.

You can create a read-only, named constant with the const keyword. The syntax of a constant identifier is the same as any variable identifier: it must start with a letter, underscore, or dollar sign ($), and can contain alphabetic, numeric, or underscore characters.
A constant cannot change value through assignment or be re-declared while the script is running. It must be initialized to a value. The scope rules for constants are the same as those for let block-scope variables.
You cannot declare a constant with the same name as a function or variable in the same scope. However, const only prevents re-assignments, but doesn't prevent mutations. 

Source: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types#basics


