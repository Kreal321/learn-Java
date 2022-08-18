# Learning Java OCA Notes

## Comments
Multiline comment: anteater, elephant. 
Single line comment: bear, cat, dog. 
Compiler error: ferret

```Java
/*
* // anteater
*/

// bear

// // cat

// /* dog */

/* elephant */

/*
* /* ferret */
*/
```
Explanation: 

anteater is in a multiline comment. Everything between /*
and */ is part of a multiline comment—even if it includes a single-line comment within it! bear is your basic single-line comment. cat and dog are also single-line comments.

Everything from // to the end of the line is part of the comment, even if it is another type of comment. elephant is your basic multiline comment.
The line with ferret is interesting in that it doesn’t compile. Everything from the fi rst /* to the fi rst */ is part of the comment, which means the compiler sees something like this: /* */ */