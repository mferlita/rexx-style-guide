# rexx-style-guide
Style guide for Rexx, ooRexx, NetRexx, and cRexx with input from the RexxLA community.

Rexx doesn't really have an official style guide. While learning ooRexx, I
thought I should figure something out. While Rexx emphasizes a "do it your own
way" approach, this might be detrimental in the open-source scene and larger
code bases where communicating with your fellow programmers is just as important
as talking to the computer. I've reviewed the official Rexx documentation,
other style guides, and styling recommendations from various RexxLA talks and
have come up with the following. 

Please note that at this point, this is a work
in progress.

## General


## Classic Rexx


## ooRexx


## NetRexx


## CREXX


## Portability Across Variants


### Case

| Element                 | Format                          | Examples                 |
|-------------------------|---------------------------------|--------------------------|
| Keyword Instructions    | lowercase                       | parse<br/>say            |
| Built-in Functions      | UPPERCASE                       | RANDOM()<br/>CHAROUT()   |
| Directives              | lowercase                       | ::class<br/>::include    |
| Methods and Routines    | camelCase                       | append<br/>appendAll     | 
| Variables               | camelCase                       | myChapter                | 
| Classes                 | PascalCase                      | .Array<br/>.DateTime     |
| Boolean and Nil         | lowercase                       | .nil<br/>.true           | 


### Write code that is clear, not clever.


### Different cases are used for identifiers. See table above.


### Use meaningful names for variables, routines, classes, and methods.


### Avoid single character names.


### Prefer two spaces for indentation.


### Prefer 80 character line length.


### One statement per line.


### Comment generously and explain your intent.


### Leave whitespace around operators (a = 1 + 1). This improves readability greatly.


### Keep routines and methods small.


### If you call code only once, don't make it a routine or a method.


### Align related code.


### Separate logical sections with one blank line.


### Prefer object methods over legacy functions.


### Avoid unnecessary abbreviation.


### Use clear program headers


### In the Directives section, use comment lines to separate ::routine and ::class blocks.


### Include Error Handling


### Put directives at the end of a file


### USE ARG vs. PARSE ARG


### The ADDRESS Statement

### Control Flow
#### Avoid deeply nested if statements and keep them simple.
#### If / Then / Else
#### Select / When / Otherwise

### DO Loops

### String Concatenation

### Rules for Portability

### Do not mix cases in a project, let alone a single file. Be consistent.


## Tools


## Sources of Inspiration
https://rubystyle.guide/
https://google.github.io/styleguide/javaguide.html
https://peps.python.org/pep-0008/
https://www.rexxla.org/presentations/2019/REXX%20Language%20Coding%20Techniques%20Rexx%20Symposium%2020191001.pdf
https://www.rexxla.org/presentations/2000/RexxHints.pdf
https://erroneousbee.github.io/Computers/RexxStyleGuide.html
https://www.rexxla.org/presentations/2024/Rosetta%20Pearls.pdf
https://www.rexxla.org/presentations/2026/Barcelona.pdf
https://www.oorexx.org/docs/index.rsp
https://www.netrexx.org/documentation.nsp
https://crexx.org/docs/crexx_language_reference.pdf
https://github.com/RexxLA/rexxetta

| ooRexx Element          | Format                          | Example                  |
|-------------------------|---------------------------------|--------------------------|
| Environment Directories | lowercase                       | .environment<br/>.local  |
| Runtime Values          | lowercase                       | .line<br/>.rs            |
| Runtime Collections     | lowercase                       | .methods<br/>.resources  |
| Standard Stream         | lowercase                       | .stdin<br/>.stdout       |
| Monitor Stream          | lowercase                       | .input<br/>.output       |
| Runtime Info            | PascalCase                      | .RexxInfo                |
| Runtime Context         | lowercase                       | .context                 |

