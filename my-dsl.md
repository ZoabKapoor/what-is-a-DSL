# Language
_What is the name of the language? Link the name to its webpage 
(if appropriate)._

The language is called Scratch. Its webpage is [here](https://scratch.mit.edu/ "Scratch's Homepage")


# Domain
_Describe the language's domain in five words._

Game creation for CS education. 


# Computational model
_What is the underlying computational model of this language? To answer this 
question, provide a high-level description (no more than 100 words) of the 
computation that occurs when someone executes a program in this language._

Scratch is an event based programming language, so all computational logic is triggered by specific events, such as when the green flag (effectively the play button) is pressed, or when two sprites touch. When a particular event occurs, the code block connected to it runs. This could involve, for example, moving a sprite 10 units to the right, changing the sprite's costume (visual appearence), and then broadcasting "done moving". This broadcast (which I think of as similar to callbacks in JavaScript) can then trigger other events in the application. 

# DSL-ness
_Fowler writes about a spectrum of languages, from general-purpose languages to 
"purely" domain-specific. Where does the DSL you chose fall on this spectrum, 
and why?_ 

I would say this DSL falls somewhere in the middle of the spectrum. While Scratch has some features that make sense mostly in the context of game design - a "stage" which sprites move around on, event-based program logic, etc - it also has many of the features that are present in a general purpose programming language - object oriented programming, loops, conditionals, etc. 

Another feature that makes Scratch more like a pure DSL than a general purpose language is the way it's used - I've only ever seen Scratch used in 2 contexts: 
1. Education, particularly in the context of introducing kids to computer science. The programming content in Harvey Mudd's MYCS MOOC is entirely in Scratch.
2. Making games. I've seen implementations of 2048, Flappy Bird, and various other games in Scratch. 

# Internal or external?
_Is the language implemented as an internal or external DSL? 
Justify your answer._

Scratch is definitely implemented as an external DSL. Its custom syntax (of using blocks to define program logic) is not present in Squeak ([source](http://squeakbyexample.org//SBE.pdf)). Scratch presumably has a compiler that parses a user's program and compiles it to Squeak. 


# Host language
_What language(s) was (were) used to implement the DSL?_

Scratch is written in Squeak, which is an open source implementation of the Smalltalk-80 language ([source](http://wiki.scratch.mit.edu/wiki/Scratch_1.4_Source_Code)). Smalltalk-80 is an object-oriented, strongly typed, reflective programming language which was "is a computer language designed specifically for a wide range of humans rather than a narrow group of computer specialists." ([source](http://www.smalltalk.org/smalltalk/whatissmalltalk.html)) 

# Benefits
_Identify one potential benefit of the DSL: how is a programmer's life or a 
company's bottom line made easier by the existence of this language?_

One of the nice things about Scratch is that it's impossible to make syntax errors in it. In most text-based programming languages, you could write lines of code that are syntactically incorrect, which would cause the program to have a compile error. Example:
```if (4) {
	return;
}```

In Scratch, however, this is impossible. When two logic blocks shouldn't be put together, they will refuse to fit together. For example, an if block has a hexagonal space in it to insert the condition to check. Only hexagonal shaped blocks (whose evaluation returns a boolean) can be placed in that space; if you try to write, for example, `if (change volume by 10)`, the blocks will refuse to fit together. This is useful for people who are new to programming and don't necessarily know how to debug syntax errors, or understand why syntax errors occur.

# Drawbacks
_Identify one potential drawback of the DSL: what does a programmer or company 
lose by using this DSL instead of a general-purpose language?_

Scratch's way of organizing code makes it very hard to read. You can drag code blocks any part of the project editor, and it doesn't have support for importing other scripts aside from copying the script content onto your project editor ([source](http://wiki.scratch.mit.edu/wiki/Exporting_and_Importing#Scripts_2)). This makes it practically impossible to write, maintain, or read large projects in Scratch. 

In addition, Scratch doesn't have a very easy to use inline commenting system (partly because inline doesn't make sense in the context of Scratch), which is a nice feature of most general purpose programming languages.