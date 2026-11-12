# rexx-style-guide
Style guide for Rexx, ooRexx, NetRexx, and cRexx with input from the RexxLA community.

Rexx has always emphasized human-readable code. Communicating with your fellow programmers
is just as important as communicating with the computer. After all, code is more often read than it is
written. This style guide emphasizes readability for Rexx code to facilitate better 
collaboration among developers.

> "Enhancing readability enhances our ability to solve problems" — V. Anton Spraul, *Think Like a Programmer*

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
#### Do not mix cases for keywords, classes, methods, and routines in a project or file. Be consistent.

### Layout and Whitespace
#### Prefer two spaces for indentation.


#### Prefer 80 character line length.

#### No trailing whitespace

#### Leave whitespace around operators
Use spaces around operators, after commas, colons, and semicolons.
```
/* Good */
say 98 + (59872 % (13 * 8)) * 52
x = 1, 2, 3
do i to N by 1; end

/* Bad */
say 98+(59872%(13*8))*52
x=1,2,3
do i to N by 1;end
```
Exceptions:  
Exponentiation and negative integers  
```
/* Good */
say -52 * 5**2

/* Bad */
say - 52 * 5 ** 2
```

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
* [rexx-lint](https://github.com/shmuelmetz/rexx-lint)

## Sources of Inspiration
* [The Ruby Style Guide](https://rubystyle.guide/)
* [Google's Java Style Guide](https://google.github.io/styleguide/javaguide.html)
* [PEP 8 — Style Guide for Python Code](https://peps.python.org/pep-0008/)
* [Safe REXX](https://github.com/shmuelmetz/Safe-REXX/blob/7c8f3ee77756595dcfc26932caacb5eaba9ee08b/Safe-REXX-Desktop-Enterprise.md)
* [Rexx Language Coding Techniques](https://www.rexxla.org/presentations/2019/REXX%20Language%20Coding%20Techniques%20Rexx%20Symposium%2020191001.pdf)
* [Good Rexx Coding Practices](https://www.rexxla.org/presentations/2000/RexxHints.pdf)
* [Style Guide for Rexx](https://erroneousbee.github.io/Computers/RexxStyleGuide.html)
* [Rosetta Pearls](https://www.rexxla.org/presentations/2024/Rosetta%20Pearls.pdf)
* [Official ooRexx Documentation](https://www.oorexx.org/docs/index.rsp)
* [Official NetRexx Documentation](https://www.netrexx.org/documentation.nsp)
* [Official CREXX Documentation](https://crexx.org/#docs)
* [Rexxetta](https://github.com/RexxLA/rexxetta)
