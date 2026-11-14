# rexx-style-guide
Style guide for Rexx, ooRexx, NetRexx, and cRexx with input from the RexxLA 
community.

Rexx has always emphasized human-readable code. Communicating with your 
fellow programmers is just as important as communicating with the computer. 
After all, code is more often read than it is written. This style guide 
emphasizes readability for Rexx code to facilitate better collaboration 
among developers.

> "Enhancing readability enhances our ability to solve problems" — V. Anton 
> Spraul, *Think Like a Programmer*

## General

### Naming
| Element                 | Format     | Examples               |
|-------------------------|------------|------------------------|
| Keyword Instructions    | lowercase  | parse<br/>say          |
| Built-in Functions      | UPPERCASE  | RANDOM()<br/>CHAROUT() |
| Directives              | lowercase  | ::class<br/>::include  |
| Methods and Routines    | camelCase  | append<br/>appendAll   | 
| Variables               | camelCase  | myChapter              | 
| Classes                 | PascalCase | .DateTime<br/>RomanNum |
| Boolean and Nil         | lowercase  | .nil<br/>.true         | 
* #### Use the case convention above in a file and do not mix cases.

* #### Use English for identifiers
  ```rexx
  /* Good - Identifier is in English */
    salary = 1000
  
  /* Bad - Identifier is in Greek */
    μισθός = 1000
  
  /* Bad - Identifier is in Greek but spelled with Latin letters */
    misthos = 1000
  ```

* #### Use meaningful names for variables, routines, classes, and methods.
  ```rexx
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
  ```rexx
  /* Good */
    do count = 1 to max
  
  /* Bad */
    do c = 1 to m
  ```

* #### Avoid unnecessary abbreviation
  ```rexx
  /* Good */
    lineCount = 2
  
  /* Bad */
    lineCnt = 2
  ```

### Layout and Whitespace
* #### Prefer two spaces for indentation.
  ```rexx
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
  ```rexx
  /* Good */
    say 98 + (59872 % (13 * 8)) * 52
    x = 1, 2, 3
    min = 2; max = 4
  
  /* Bad */
    say 98+(59872%(13*8))*52
    x=1,2,3
    min=2;max=4
  ```
  
  *Exceptions:* Exponentiation, negative integers, and method send operator 
  (twiddle)  
  ```rexx
  /* Good */
    say -52 * 5**2
    say "!elloH"~reverse
  
  /* Bad */
    say - 52 * 5 ** 2
    say "!elloH" ~ reverse
  ```

* #### Align the elements of arrays spanning multiple lines
  ```rexx
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
  ```rexx
  /* Good */
    say "Hi"
    say "Bye"
  
    if someVar > 0 then 
      say "positive"
  
    if lineCount > 1000 then
      say "Warning: large file"

    
  /* Bad */
    say "Hi"; say "Bye"
    
    if someVar > 0 then say "positive"
  
    if lineCount > 1000 then say "Warning: large file"
  ```
  
* #### Separate logical sections with one blank line.
  ```rexx
  /* Good */
    price = 1 + 2
    total = price * 3
    
    taxRate = 0.08
    tax = total * taxRate
    
    say "Total: " || total
    say "Tax: " || tax
  
  /* Bad */
    price = 1 + 2
    total = price * 3
    taxRate = 0.08
    tax = total * taxRate
    say "Total:" total
    say "Tax:" tax
  ```

### Comments
* #### Comment styling
  ```rexx
  /* Good - Inline Comments */
  
    /* an inline comment (portable) */
    -- an inline comment (ooRexx/NetRexx/CREXX only)
  
  /* Good - Block Comments */
  
    /* 
    * This is a block style comment
    * for describing things in detail 
    * and grabbing attention
    */
  
  /* Bad - Block Comments */
  
    /************************************************/
    /* To the interpreter, these lines are all      */
    /* separate comments and could consume extra    */
    /* cycles, affecting performance. They eat      */
    /* up file space unnecessarily which could also */
    /* affect performance. Lastly, they are harder  */
    /* to write and thus harder to maintain.        */
    /************************************************/
  
    /***************************************
    * This is also bad. While the block is *
    * considered one comment now, it is    *
    * still just as hard to maintain       *
    * because of all the extra symbols.    *
    ***************************************/
  
  ```

* #### Use clear program headers

* #### Comment generously to explain your intent

### Structure
* #### Keep routines and methods short. 
  If it exceeds ten lines of code (empty lines excluded), ask "is this doing 
  more than one thing?"

* #### If you call code only once, don't make it a routine or a method.

* #### Use comment lines to separate ::routine and ::class blocks.

* #### Put directives after the main body of code

### Control Flow
* #### Avoid deeply nested if statements and keep them simple.
<!-- TODO -->

* #### If / Then / Else
<!-- TODO -->

* #### Select / When / Otherwise
<!-- TODO -->

### DO statements
* #### Keep "do" on the same line as its conditional statement
  ```rexx
  /* Good */
    do while num > 1
      ...some code
    end
    
  /* Bad */
    do
      while num > 1
      ...some code
    end
  ```

### String Concatenation
* #### Prefer explicit concatenation over implicit
  ```rexx
  /* Good */
  name = stdin~lineIn()
  say "My name is " || name || "."
  
  say 2 || "5"
  say "I like " || "apple pie."
  
  /* Bad */
  name = stdin~lineIn()
  say "My name is" name"."
  
  say 2"5"
  say "I like" "apple pie"
  ```

### Error Handling
<!-- TODO -->

### ADDRESS
<!-- TODO -->

## Rules Specific to Classic Rexx
<!-- TODO -->

## Rules Specific to ooRexx
* #### Prefer object methods over legacy functions
<!-- TODO -->

## Rules Specific to NetRexx
<!-- TODO -->

## Rules Specific to CREXX
<!-- TODO -->

## Rules for Portability
### USE ARG vs. PARSE ARG
<!-- TODO -->

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
