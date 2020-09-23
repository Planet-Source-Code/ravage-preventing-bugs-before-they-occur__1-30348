<div align="center">

## Preventing Bugs Before They Occur


</div>

### Description

Wow, I'm writing another tutorial for Beginner, Intermediate, and Advanced. I hope that this tutorial will help like all my others did. In this tutorial, I will attempt to explain how to prevent bugs before they occur. How, you may ask? Well, I will explain to you bug preventing techniques like using Option Explicit, applying the KISS and SMILE principles, taking advantage of Object-Oriented Programming, using Comments and Coding Conventions, and following Coding Conventions by using Variable and Routine names and avoiding certain statements. I will also throw in what I call the Ten Commandments of being a Lazy Programmer. Is being a 'Lazy Programmer' good? Well, yes it is and you'll find that out soon enough! Maybe some of you are already 'Lazy Programmers'. So, without further eddo, lets begin!
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |2002-01-03 12:05:58
**By**             |[Ravage](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/ravage.md)
**Level**          |Beginner
**User Rating**    |4.3 (51 globes from 12 users)
**Compatibility**  |VB 6\.0
**Category**       |[Debugging and Error Handling](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/debugging-and-error-handling__1-26.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[Preventing46089132002\.zip](https://github.com/Planet-Source-Code/ravage-preventing-bugs-before-they-occur__1-30348/archive/master.zip)





### Source Code

<html>
<head>
<meta http-equiv="Content-Language" content="en-us">
<meta http-equiv="Content-Type" content="text/html; charset=windows-1252">
<meta name="GENERATOR" content="Microsoft FrontPage 4.0">
<meta name="ProgId" content="FrontPage.Editor.Document">
<title>PREVENTING BUGS BEFORE THEY OCCUR</title>
</head>
<body>
<p><font size="4"><b>PREVENTING BUGS BEFORE THEY OCCUR</b></font></p>
<p>   <font size="4"><b> </b></font><font size="3">Perhaps the
best way to fix a bug is to keep the bug from happening in the first
place.  For the most part, the techniques for preventing bugs are common
sense things (or would be common sense if common sense were common) that most
programmers would do if they took the time to think about it.  But let's
face it, with increasing demands on our time, we don't always have the time we
need to pay such attention to detail!</font></p>
<p><font size="4"><b>USING OPTION EXPLICIT</b></font></p>
<p style="line-height: 100%">   <font size="4"><b> </b></font><font size="3">Most
programming languages in use today require that you declare a variable before
you use it.  In some languages, declaring variables is done to make it
easier to write the compiler.  With other languages, programmers declare
variables just for documentation purposes; others do it simply because it was
always done that way.  But I've found that declaring a variable does two
things: it ensures that you get the variable type you want, and it prevents you
from misspelling the variable's name.  Sometimes, finding a misspelled
variable can be very difficult, since <i>Clock </i>and<i> C1ock </i>look the
same to you and me but not to the compiler.  By default, Visual Basic will
create a variable automatically the first time you use it.  To disable this
feature, you need to include Option Explicit at the top of each module in you
program.  For new projects, you can set the Visual Basic IDE option Require
Variable Declaration (in the Options dialog box).  For existing projects,
you can simply enter Option Explicit into the Global Declaration section of any
module.  The big limitation of Option Explicit is that it applies only to a
given module, not to the entire project.  So in a complex project with a
lot of forms and classes, you need to ensure that each module has Option
Explicit included.  </font></p>
<p style="line-height: 100%"><b><font size="4">APPLYING THE KISS PRINCIPLE</font></b></p>
<p style="line-height: 100%">   <font size="4"><b> </b></font><font size="3">A
long time ago, I learned about the old KISS (Keep It Simple, Stu--pid)
principle.  In the case of Visual Basic, the idea is that, in the long run,
an overly complex program will cause more problems than a simple program. 
A simple program is easier to understand, thus making later modifications and
debugging a whole lot easier (especially if someone else is doing those
modifications).  A simple program may even be more efficient, since it is
not carrying around a lot of baggage caused by extra features that aren't
used.  The simple-is-better philosophy does not always work, however. 
A heap sort is more complex than a bubble sort, but the results are often worth
it.  Yet, true believers in the KISS principle will say that using a
prepackaged sort routine will give you even better results with less code to go
wrong.</font></p>
<p style="line-height: 100%"><b><font size="4">APPLYING THE SMILE PRINCIPLE</font></b></p>
<p style="line-height: 100%">   <font size="4"> </font><font size="3">Like
very complex programs, large blocks of code can also lead to problems. 
Someone once told me that if you can't see an entire subroutine or function,
then it's too large.  I call this the SMILE (Simple Makes It Lots Easier)
principle.  Typically, I'll try to fit the entire routine in about 30
lines.  So, if I can't fit the code into that 30 lines, I'll divide the
code into a few private subroutines and call them from the original. 
Occasionally, I find that I want to use a large subroutine.  This usually
happens when I have many assignment statements or subroutine calls, or I have a
Select Case statement or If ... Then ... ElseIf statement with many individual
conditions.  In the first situation, I try to group the statements into
meaningful chunks.  In the second situation, I try to limit myself to less
than a dozen statements in each of the individual cases.  </font></p>
<p style="line-height: 100%"><b><font size="4">TAKING ADVANTAGE OF OBJECT-ORIENTED
PROGRAMMING</font></b></p>
<p style="line-height: 100%">   <font size="4"><b> </b></font><font size="3">Object-oriented
programming means many things to many people (especially those in the marketing
department).  The answer to the question "Is Visual Basic
object-oriented?" doesn't really matter.  What matters is that when
you break your program into chunks, you programs become more reliable.  By
using well-defined interfaces, you are forced to think about how the chunk will
be used.  Since you can't cross boundaries and change a particular value
inside a chunk even though you think it's safe, you may need to include an
additional interface in the future.  But at least you will know all of the
code that could possibly modify the chunk's data.  So if the chunk's data
gets corrupted, this approach simplifies the debugging process
considerably.  The other advantage of chunks is that they are easy to build
and easy to test by themselves.  Once they have been tested, you can build
other components using these chunks.  Since your chunks communicate through
well defined interfaces, you can check for invalid parameters and trap more
errors before they occur.  Of course, you also get the fundamental
advantage of object-oriented programming.  When you need to change an
object's architecture, your existing program will continue to work without
changes, as long as the interfaces continue to work the same way.  Also,
you can use the object in more than one place, which will help to reduce your
overall programming effort.  </font></p>
<p style="line-height: 100%"><b><font size="4">USING COMMENTS AND CODING
CONVENTIONS</font></b></p>
<p style="line-height: 100%">   <font size="4"> </font><font size="3">Comments
and coding conventions are also important to minimizing problems in you
code.  While these things may not prevent bugs per se, they will help the
next person who comes along to understand what you did and why you did it. 
Then if something should go wrong, it will be easier for that next person to
rectify the problem.  There is more to writing comments than simply
repeating what is obvious from reading the code.  Writing good comments
takes a little time and some thought, but the end result should be useful to
anyone (including yourself) who may read those comments in the
future.  </font></p>
<p style="line-height: 100%"><b><font size="4">FOLLOWING CODING CONVENTIONS</font></b></p>
<p style="line-height: 100%">   <font size="4"> </font><font size="3">Coding
conventions are another useful tool for preventing bugs.  Coding
conventions come in a couple of forms: they provide rules for naming variables
and routines, and they identify which statements you want to avoid while
programming.  Both forms combine to create a style that must be comfortable
for you to use.  </font></p>
<p style="line-height: 100%"><font size="3">   <b> VARIABLE AND
ROUTINE NAMES</b></font></p>
<p style="line-height: 100%"><font size="4">    </font><font size="3">Microsoft
recommends a rather complex way to prefix variables.  While this convention
conveys a lot of information about your variables, it makes them somewhat
unreadable and definitely difficult to remember.  Even though Microsoft
makes this suggestion, you might notice that the properties for things like the
TextBox and ListBox controls refer to the Text property rather than the strText
property.  The same goes for the rest of the properties and methods for the
other controls and objects.  I suggest that you use meaningful names but
leave the type information off the variable name.  Subroutines and
functions are two places where the more descriptive you make the name, the less
likely you are to use the wrong one.  Properties, methods, and events in
your own user controls should also be descriptive.  After all, when you
compile your program into machine code, it doesn't matter in the least whether
you used two characters or twenty characters!   </font></p>
<p style="line-height: 100%"><font size="3">   <b> STATEMENTS TO
AVOID</b></font></p>
<p style="line-height: 100%">   <font size="4"> </font><font size="3">Visual
Basic includes a variety of different statements, many of which overlap other
statements in terms of functionality.  I strongly suggest that you choose a
subset of these statements and use them, while ignoring the others.  This
means you'll need to remember the syntax for fewer statements, and you'll become
more comfortable with the ways that you use those statements.  For
instance, you can use For/Next, Do Until/Loop, Do While/Loop, and While/Wend to
perform loops in your code.  There is no reason to use all four.  I
suggest you pick one style and use it consistently.  Personally, I prefer
the Do While/Loop structure, but I find myself using the For/Next anytime I'm
dealing with a collection of objects (For Each), or when I need to perform a
process a fixed number of times (For I = 1 to 10).  I never use the Do
Until/Loop or the While/Wend statements.  I also recommend avoiding the
Gosub/Return statement and the GoTo statement.  Both are holdovers from
BASIC's early days.  Gosub/Return isn't really needed in Visual Basic,
where you can declare real subroutines, and GoTo is against every structured
programming rule ever written.  I've debugged many programs written by
various programmers who used the GoTo statement, and I've frequently found it
faster to rewrite the entire program rather that try to fix it.  </font></p>
<p style="line-height: 100%"><b><font size="4">BEING A LAZY PROGRAMMER</font></b></p>
<p style="line-height: 100%">   <font size="3"> After reading
about the KISS and SMILE principles, object-oriented programming, and comments
and coding conventions, you may be wondering, "What does this have to do
with debugging my programs?"  The answer is that following good, solid
programming practices is key to creating programs that require less debugging
and that can more easily be debugged.  As long as I'm on my soapbox, I'm
going to suggest a general philosophy that will help you eliminate bugs before
they become bugs.  I call it the Lazy Programmer approach.  Here are
the Ten Commandments of a Lazy Programmer:</font></p>
<p style="line-height: 100%">   <font size="3"> 1.)  Think
about what you want to do before you write any code.</font></p>
<p style="line-height: 100%">   <font size="3"> 2.)  Make it
work the first time - you prefer not to do it again.</font></p>
<p style="line-height: 100%">   <font size="3"> 3.)  Don't
make a program more complicated than necessary because this may introduce more
problems into the program in the long run.</font></p>
<p style="line-height: 100%">   <font size="3"> 4.)  Write
modular programs because they are easier to test and debug.</font></p>
<p style="line-height: 100%">   <font size="3"> 5.)  Use a
wide variety of tools to reduce the amount of work required to create the program
and to increase the reliability of the final product.</font></p>
<p style="line-height: 100%">   <font size="3"> 6.)  Reuse code
where possible, since the code has already been written and is known to work
properly.</font></p>
<p style="line-height: 100%">   <font size="3"> 7.)  Write the
least amount of code to solve the problem.</font></p>
<p style="line-height: 100%">   <font size="3"> 8.)  Use a lot of
comments for complex code, and make sure that you provide a good overview of how
the program functions.</font></p>
<p style="line-height: 100%">   <font size="3"> 9.)  Use good
coding conventions so that comments aren't necessary for simple tasks.</font></p>
<p style="line-height: 100%">   <font size="3"> 10.)  Use Visual
Basic to write Windows programs.  </font></p>
</body>
</html>

