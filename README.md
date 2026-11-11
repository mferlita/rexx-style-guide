# rexx-style-guide
Style guide for Rexx, ooRexx, NetRexx, and cRexx with input from the RexxLA community.

Rexx doesn't really have an official style guide. While learning ooRexx, I
thought I should figure something out. While Rexx emphasizes a "do it your own
way" approach, this might be detrimental in the open-source scene and larger
code bases where communicating with your fellow programmers is just as important
as talking to the computer. I've reviewed the official Rexx documentation,
other style guides, and styling recommendations from various RexxLA talks and
have come up with the following. 

### Write code that is clear, not clever.

Please note that at this point, this is a work
in progress.

## General

### Naming
| Element                 | Format                          | Examples                 |
|-------------------------|---------------------------------|--------------------------|
| Keyword Instructions    | lowercase                       | parse<br/>say            |
| Built-in Functions      | UPPERCASE                       | RANDOM()<br/>CHAROUT()   |
| Directives              | lowercase                       | ::class<br/>::include    |
| Methods and Routines    | camelCase                       | append<br/>appendAll     | 
| Variables               | camelCase                       | myChapter                | 
| Classes                 | PascalCase                      | .Array<br/>.DateTime     |
| Boolean and Nil         | lowercase                       | .nil<br/>.true           | 
#### Different cases are used for identifiers. See table above.
#### Use meaningful names for variables, routines, classes, and methods.
#### Avoid single character names.
#### Do not mix cases in a project or file. Be consistent.


### Layout and Whitespace
#### Prefer two spaces for indentation.
#### Prefer 80 character line length.
#### Leave whitespace around operators (a = 1 + 1). This improves readability greatly.
#### Avoid unnecessary abbreviation.
#### Align related code.
#### One statement per line.
#### Separate logical sections with one blank line.

### Comments
#### Comment generously and explain your intent.
#### Use clear program headers

### Structure
#### Keep routines and methods small.
#### If you call code only once, don't make it a routine or a method.
#### In the Directives section, use comment lines to separate ::routine and ::class blocks.
#### Put directives at the end of a file

### Control Flow
#### Avoid deeply nested if statements and keep them simple.
#### If / Then / Else
#### Select / When / Otherwise

### DO Loops


### String Concatenation


### Error Handling


### ADDRESS


### USE ARG vs. PARSE ARG


## Rules Specific to Classic Rexx


## Rules Specific to ooRexx
### Prefer object methods over legacy functions.

## Rules Specific to NetRexx


## Rules Specific to CREXX


## Portability Across Variants
### Rules for Portability


## Tools


## Sources of Inspiration
https://rubystyle.guide/
https://google.github.io/styleguide/javaguide.html
https://peps.python.org/pep-0008/
https://www.rexxla.org/presentations/2019/REXX%20Language%20Coding%20Techniques%20Rexx%20Symposium%2020191001.pdf
https://www.rexxla.org/presentations/2000/RexxHints.pdf
https://erroneousbee.github.io/Computers/RexxStyleGuide.html
https://www.rexxla.org/presentations/2024/Rosetta%20Pearls.pdf
https://www.oorexx.org/docs/index.rsp
https://www.netrexx.org/documentation.nsp
https://crexx.org/docs/crexx_language_reference.pdf
https://github.com/RexxLA/rexxetta
