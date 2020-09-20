# Anatomy of an IDE

In the form of a pro/con list, [as derived from @munificent](https://gist.github.com/munificent/9749671).  I'd wanted to start one of the these, and @munificent's is a good bootstrap.


## Platform

* [ ] cloud-hosted 
* [ ] locally installable 
* [ ] web-based 
* [ ] browser-based 
* [ ] language-agnostic
* [ ] language-specific IDE. 

Your IDE will not succeed. Here is why it will not succeed.

## Adoption misconceptions

* [ ] Syntax highlighting is what makes programming difficult
* [ ] Garbage collection is free
* [ ] Computers have infinite memory
* [ ] Nobody really needs:
    * [ ] a REPL
    * [ ] debugger support
    * [ ] a local filesystem
    * [ ] to interact with code not written in your IDE's preferred language
* [ ] The entire world speaks 7-bit ASCII
* [ ] Scaling up to large software projects will be easy
* [ ] Convincing programmers to adopt a new IDE will be easy
* [ ] Convincing programmers to adopt a language-specific IDE will be easy
* [ ] Programmers love learning new keybindings
* [ ] There is only one operating system and it is
    * [ ] OS X  
    * [ ] Windows  
    * [ ] Linux  
    * [ ] iOS  
    * [ ] Android  
    * [ ] the DOM

## Feature Opinionations, or Misses

* [ ] vi keybindings
* [ ] emacs keybindings
* [ ] Syntax highlighting
* [ ] User-configurable indentation
* [ ] Macros
   * [ ] Written in JavaScript
       * [ ] but only JSON
   * [ ] Written in a scripting language you made up
       * [ ] which is a Lisp
* [ ] A windowing system
* [ ] Version control
   * [ ] Only using git 
   * [ ] only using github.com 
   * [ ] not using git
   * [ ] using an RCS of your own devising
* [ ] Its own platform-independent look-and-feel
   * [ ] that was designed by a programmer
   * [ ] based on yesterday's design fads
   * [ ] applied inconsistently
* [ ] A look and feel specific to one operating system
   * [ ] that was last widely used in 1989
   * [ ] and was known to cause seizures

## Heuristic Dispositions

* [ ] Programmers should not need to understand CSS to change their font
* [ ] The most significant program written using your IDE is itself
* [ ] The most significant program written using your IDE isn't even itself
* [ ] Graphical programming presumes programmers can draw pictures better than they can type words
* [ ] The implementation is closed-source
    * [ ] covered by patents  
    * [ ] not owned by you
* [ ] The DOM is not an application framework
* [ ] The name of your IDE makes it impossible to find on Google
* [ ] Your IDE assumes JavaScript can be made infinitely fast
* [ ] You seem to think static analysis is worthless
* [ ] JavaScript is not faster than C, C++, or Java
* [ ] The DOM is not a windowing framework
* [ ] It crashes on any file larger than 32k
* [ ] You provide no way for users to run the program they are editing
* [ ] You require the user to check in code before it can be run
* [ ] The IDE crashes if you look at it funny
* [ ] You don't seem to understand basic optimization techniques
* [ ] You think a single string is an acceptable data type for a text editor

## Marketing Missteps

* [ ] Unsupported claims of increased productivity
* [ ] Unsupported claims of greater "ease of use"
* [ ] Obviously faked screenshots
* [ ] No one really believes that your IDE is faster than:
    * [ ] vi  
    * [ ] emacs  
    * [ ] Eclipse  
    * [ ] Visual Studio  
    * [ ] IntelliJ 
    * [ ] Notepad
* [ ] Rejection of orthodox user interface design without justification
* [ ] Rejection of usability principles without justification
* [ ] Rejection of established platform conventions without justification
* [ ] Rejection of basic user interaction without justification

## Comparisons

* [ ] Your example workflow would be one key command in: _______________________
* [ ] We already have an IDE in the browser
* [ ] We already have an IDE that can be scripted using
   * [ ] Python 
   * [ ] JavaScript 
   * [ ] A Lisp 
   * [ ] Lua
* [ ] You have reinvented vi but worse
* [ ] You have reinvented emacs but worse
* [ ] You have reinvented TextMate but worse
* [ ] You have reinvented Eclipse but worse
* [ ] You have reinvented Notepad but worse
* [ ] You have reinvented Notebad better, but that's still no justification
* [ ] You have reinvented ed but non-ironically

In conclusion, this is what I think of you:

* [ ] You have some interesting ideas, but this won't fly.
* [ ] This is a bad IDE, and you should feel bad for creating it.
* [ ] Programming in this IDE is an adequate punishment for inventing it.