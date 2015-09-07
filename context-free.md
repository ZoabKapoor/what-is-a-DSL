# Context Free

##  Who is this programming language for?

I think the ideal target audience would be a computer scientist who's interested in art. This is because the output of the program can be very artistic in nature, which appeals to artists, but knowing about context free grammars (which most computer scientists do) enables one to understand how the language works and thus pick it up quickly.  

## What is easy to do in this language? Why is it easy?

It's easy to create images using recursion, like fractals. This is easy because ContextFree programs are (unsurprisingly) structured like the specification of a context-free grammar, with a start symbol that can call other rules recursively. 

## What is hard to do in this language? Why is it hard?

It's hard to specify complex shapes that aren't recursively defined. This is hard because you'd have to actually specify the shape line by line - consider, for example, the amount of code needed to create the "Welcome" image. It's also hard to visualize what your programs are going to look like without actually compiling them, because it's hard to visualize what the recursion will look like. 

## How did you learn how to program in this language?

I went through and read the tutorials, then modified the code in the tutorials to see what effects that had on the rendered image. Whenever I wanted to do something but wasn't sure how, I looked it up in the CDFG HOWTO wiki. 

## What is the underlying _computational model_ for this programming language? 
_We don't yet have a great definition of the term "computational model". 
For now, try to come up with the clearest, most concise explanation of what 
happens when a ContextFree program runs._

As stated above, the programming language is evaluated like a context-free grammar. The parser evaluates the startshape by either drawing the shape or, if it references another rule, substituting in the rule it references. It then evaluates that rule, substituting recursively as relevant. If a rule has multiple subrules, it picks one to use at random. 

One thing I'm not sure about is how it decides to stop making substitutions and just attempt to draw the shape specified by the program - you could certainly imagine a Context Free program where a rule referencing itself (like a fractal) takes forever to evaluate. Presumably the compiler has some way to know when the shape it draws will be smaller than a pixel and then stops evaluating the program then, which is pretty neat. 


## What do you think is interesting about the ContextFree program you wrote?

The ContextFree program I wrote is a modification of the first fractal-generating code ([here](https://web.archive.org/web/20100620122031/http://contextfreeart.org/mediawiki/index.php/Tutorials/Fractals)). I was interested to see what would happen if I changed the base shape for the Serpinski triangle from a TRIANGLE to CIRCLE or SQUARE. I expected this to vastly change what the final image looked like. To my great surprise, the resulting rendered image *still* looked like a Serpinski triangle, just slightly different - for instance, rounder when I made the base image CIRCLE, which is the image I'm submitting with this assignment. 

I also played around with different colours and saturations for a bit, which you can also see in the image I'm submitting. I think changing the saturations for the 3 subtriangles created an interesting visual effect, though it's very subtle when the brightness is turned down.
When the brightness is increased the effect is more prominent, but then the triangles aren't as well defined and so don't look as cool.
