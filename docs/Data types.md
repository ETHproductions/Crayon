#### Spec
- [**Data types**](https://github.com/ETHproductions/Crayon/blob/master/docs/Data%20types.md)
- [Operators](https://github.com/ETHproductions/Crayon/blob/master/docs/Operators.md)
- [Encoding](https://github.com/ETHproductions/Crayon/blob/master/docs/Encoding.md)

**Please note:** This spec is a draft; any detail may change without warning.

#### Data types

There are three main data types in Crayon:

- String/Pattern: Used like strings in most other languages, but have special properties when drawn to the canvas.
- Number: Floating-point numbers, handled as in JS.
- Array: An array of strings, numbers, and/or arrays. The stack is an array of sorts.

#### Patterns

Patterns are stored as ordinary strings. However, when drawing them on the canvas, there are a few specific changes made:

\- Newlines are not drawn onto the canvas as newlines; instead, the next line of the pattern is drawn direcly below the current one. For example:

    Drawing   on      at     becomes
    abc       #####   x:1    #####
	def       #####   y:1    #abc#
	          #####   d:E    #def#
    
\- Spaces are not drawn onto the canvas, either:

    Drawing   on      at     becomes
    ab        #####   x:1    #####
	 cd       #####   y:1    #ab##
	          #####   d:E    ##cd#
    
However, if you use a non-breaking space (`\x1F`), it will overwrite the character underneath it.

\- Patterns are drawn in the direction of the cursor. For example:

    Drawing   on      at     becomes
    abcd      ####    x:0    ###d
	          ####    y:3    ##c#
	          ####    d:NE   #b##
	          ####           a###

\- If the pattern goes off the edge of the canvas (even into negative coordinates), the canvas is extended in that direction. The origin stays where it was previously.

The crayon is then moved one space past the end of the pattern, to (x:4, y:-1).