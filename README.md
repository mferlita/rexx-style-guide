# rexx-style-guide
Style guide for Rexx, ooRexx, NetRexx, and cRexx with input from the RexxLA community.

Rexx has always emphasized human-readable code. Communicating with your fellow programmers
is just as important as communicating with the computer. After all, code is more often read than it is
written. This style guide emphasizes readability for Rexx code to facilitate better 
collaboration among developers.

> "Enhancing readability enhances our ability to solve problems" — V. Anton Spraul, *Think Like a Programmer*

## General

### Naming
| Element                 | Format                          | Examples               |
|-------------------------|---------------------------------|------------------------|
| Keyword Instructions    | lowercase                       | parse<br/>say          |
| Built-in Functions      | UPPERCASE                       | RANDOM()<br/>CHAROUT() |
| Directives              | lowercase                       | ::class<br/>::include  |
| Methods and Routines    | camelCase                       | append<br/>appendAll   | 
| Variables               | camelCase                       | myChapter              | 
| Classes                 | PascalCase                      | .DateTime<br/>RomanNum |
| Boolean and Nil         | lowercase                       | .nil<br/>.true         | 
* #### Different cases are used for identifiers. See table above.

* #### Use English for identifiers
  ```
  /* Good - Identifier is in English */
  salary = 1000
  
  /* Bad - Indentifier is in Greek */
  μισθός = 1000
  
  /* Bad - Identifier is in Greek but spelled with Latin letters */
  misthos = 1000
  ```

* #### Use meaningful names for variables, routines, classes, and methods.
  ```
  /* Good - descriptive, relevant */
  price = 1 + 2
  total = price * 3
  ::method calculateTotal
  
  /* Bad - generic, unclear */
  values = 1 + 2
  computed = values * 3
  ::method calc
  ```

* #### Avoid single character names.
  ```
  /* Good */
  do count = 1 to max
  
  /* Bad */
  do c = 1 to m
  ```

* #### Avoid unnecessary abbreviation
  ```
  /* Good */
  lineCount = 2
  
  /* Bad */
  lineCnt = 2
  ```

### Layout and Whitespace
* #### Prefer two spaces for indentation.
  ```
  /* Good - 2 spaces */ 
  do forever
    say "SPAM"
  end
  
  /* Bad - no indentation */
  do forever
  say "SPAM"
  end
  
  /* Bad - 4 spaces */
  do forever
      say "SPAM"
  end
  ```

* #### Prefer 80 character line length.

* #### No trailing whitespace

* #### Leave whitespace around operators
  Use spaces around operators, after commas, colons, and semicolons.
  ```
  /* Good */
  say 98 + (59872 % (13 * 8)) * 52
  x = 1, 2, 3
  min = 2; max = 4
  
  /* Bad */
  say 98+(59872%(13*8))*52
  x=1,2,3
  min=2;max=4
  ```
  
  *Exceptions:* Exponentiation, negative integers, and method send operator (twiddle)  
  ```
  /* Good */
  say -52 * 5**2
  say "!elloH"~reverse
  
  /* Bad */
  say - 52 * 5 ** 2
  say "!elloH" ~ reverse
  ```

* #### Align the elements of arrays spanning multiple lines
  ```
  /* Good */
  someArray = "Apples", -
              "Oranges", -
              "Persimmons"
  
  /* Bad */
  someArray = "Apples", -
  "Oranges", -
  "Persimmons"
  
  ```
  
* #### One statement per line.
  One-liners may be written in the case of "if/then" statements that do not 
  contain "else" or "do/end" and the full line is no more than 40 characters 
  long.
  ```
  /* Good */
  say "Hi"
  say "Bye"
  
  if someVar > 0 then say "postiive"
  
  if lineCount > 100 then
    say "Warning: large file (" || lineCount " || "lines)"
  
  /* Bad */
  say "Hi"; say "Bye"
  
  if someVar > 0 then; say "positive"
  
  if lineCount > 100 then say "Warning: large file (" || lineCount " || "lines)"
  ```
  
* #### Separate logical sections with one blank line.
  ```
  /* Good */
  price = 1 + 2
  total = price * 3
  
  taxRate = 0.08
  tax = total * taxRate
  
  say "Total:" total
  say "Tax:" tax
  
  /* Bad */
  price = 1 + 2
  total = price * 3
  taxRate = 0.08
  tax = total * taxRate
  say "Total:" total
  say "Tax:" tax
  ```

### Comments
#### Comment generously and explain your intent.
#### Use clear program headers
#### Comment styling

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
