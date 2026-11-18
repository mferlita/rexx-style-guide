# rexx-style-guide
Style guide for Rexx, ooRexx, NetRexx, and CREXX

This style guide is maintained by Matt Ferlita with input from the RexxLA 
community. It is viewable and printable at https://mferlita.github.io/rexx-style-guide/

This guide does not in any way prescribe a singular "correct" way to write 
Rexx. Rather, it gives suggestions on best practices to create readable and 
consistent code to facilitate better collaboration among developers. After all, 
communicating with your fellow programmers is just as important as 
communicating with the computer. 

> "Enhancing readability enhances our ability to solve problems" — V. Anton 
> Spraul, *Think Like a Programmer*

## General
### Naming

| Element                 | Format     |
|-------------------------|------------|
| Keyword Instructions    | lowercase  |
| Built-in Functions      | UPPERCASE  |
| Directives              | lowercase  |
| Methods and Routines    | camelCase  |
| Variables               | camelCase  |
| Classes                 | PascalCase |
| Boolean                 | lowercase  |

* #### Use the case convention above in a file and do not mix cases.

* #### Use English for identifiers
   ```
   /* Yes - Identifier is in English */
      salary = 1000
   
   /* No - Identifier is in Greek */
      μισθός = 1000
   
   /* No - Identifier is in Greek but spelled with Latin letters */
      misthos = 1000
   ```

* #### Use meaningful names for variables, routines, classes, and methods.
   ```
   /* Yes - descriptive, relevant */
      price = 1 + 2
      total = price * 3
      ::method calculateTotal
   
   /* No - generic, unclear */
      values = 1 + 2
      computed = values * 3
      ::method calc
   ```

* #### Avoid single character names.
   ```
   /* Yes */
      do count = 1 to max
   
   /* No */
      do c = 1 to m
   ```

* #### Avoid unnecessary abbreviation
   ```
   /* Yes */
      lineCount = 2
   
   /* No */
      lineCnt = 2
   ```
  
* #### Avoid keyword names as variables

### Layout and Whitespace
* #### Prefer three spaces for indentation.
   ```
   /* Yes - 3 spaces */ 
      do forever
         say "SPAM"
      end
   
   /* No - no indentation */
      do forever
      say "SPAM"
      end
   
   /* No - 5 spaces */
      do forever
           say "SPAM"
      end
   ```

* #### Prefer 80 character line length.

* #### No trailing whitespace

* #### Leave whitespace around operators
   Use spaces around operators, after commas, colons, and semicolons.
   ```
   /* Yes */
      say 98 + (59872 % (13 * 8)) * 52
      x = 1, 2, 3
      min = 2; max = 4
   
   /* No */
      say 98+(59872%(13*8))*52
      x=1,2,3
      min=2;max=4
   ```
  
   *Exceptions:* Exponentiation, negative integers, method send operator 
   (twiddle), and extended assignments  
   ```
   /* Yes */
      say -52 * 5**2
      say "!elloH"~reverse
      sum += 1
   
   /* No */
      say - 52 * 5 ** 2
      say "!elloH" ~ reverse
      sum + = sum
   ```
  
* #### Align the elements of arrays spanning multiple lines
   ```
   /* Yes */
      someArray = "Apples", "Oranges", "Persimmons", -
                  "Lemons", "Limes", "Bergamot", -
                  "Pears", "Cherries", "Plums"
     
   /* No */
      someArray = "Apples", "Oranges", "Persimmons", -
      "Lemons", "Limes", "Bergamot", -
      "Pears", "Cherries", "Plums"
   ```
  
* #### One statement per line.
  *Note:* "if...then" and "else if...then" count as one statement
   ```
   /* Yes */
      say "Hi"
      say "Bye"
      
      if someVar > 0 then 
         say "positive"
      
      if lineCount > 1000 then
         do
            say "Warning: large file"
         end
    
   /* No */
      say "Hi"; say "Bye"
      
      if someVar > 0 then say "positive"
      
      if lineCount > 1000 then do
         say "Warning: large file"
      end
  
      if lineCount > 1000
         then do
              say "Warning: large file"
              end
   ```
  
* #### Separate logical sections with one blank line.
   ```
   /* Yes */
      price = 1 + 2
      total = price * 3
      
      taxRate = 0.08
      tax = total * taxRate
      
      say "Total: " || total
      say "Tax: " || tax
   
   /* No */
      price = 1 + 2
      total = price * 3
      taxRate = 0.08
      tax = total * taxRate
      say "Total:" total
      say "Tax:" tax
   ```

### Comments
* #### Comment styling
   ```
   /* Yes - Inline Comments */
   
      -- an inline comment (ooRexx/NetRexx/CREXX only)
   
   /* Yes - Block Comments */
   
      /* 
      * This is a block style comment
      * for describing things in detail 
      * and grabbing attention
      */
      
      /* This is a single line block comment. */
   
   
   /* No - Block Comments */
   
      /************************************************/
      /* To the interpreter, these lines are all      */
      /* separate comments and could consume extra    */
      /* cycles, affecting performance. They eat      */
      /* up file space unnecessarily which could also */
      /* affect performance. Lastly, they are harder  */
      /* to write and thus harder to maintain.        */
      /************************************************/
      
      /****************************************
      * This is also a no. While the block is *
      * considered one comment now, it is     *
      * still just as hard to maintain        *
      * because of all the extra symbols.     *
      ****************************************/
   ```

* #### Use clear program headers

* #### Comment generously to explain your intent

* #### Do not nest comments

### Structure
* #### Routines and methods should do only one thing 
  
* #### If you call code only once, don't make it a routine or a method

* #### Use comment lines to separate ::routine and ::class blocks

* #### Put directives after the main body of code

* #### Keep variables close to where they are used

### Operators and Assignments
* #### Prefer shorthand for extended assignments
   ```
      /* Yes */
         sum += 1

      /* No */
         sum = sum + 1

   ```

* #### Prefer \\= (not equal) over <>, ><, and ¬= for clarity
   ```
      /* Yes */
         if x \= 12 then
  
      /* No */
         if x <> 12 then
         if x >< 12 then
         if x ¬= 12 then
   ```

### Control Flow
* #### No more than three levels of nesting.

* #### Don't use "signal" as "goto"
   Signal should only be used for error handling.

### DO/LOOP statements
* #### Use top-driven loops
   Prefer "do while" over "do until". 

* #### Use "leave" to leave a loop, not "exit"

### Block Formatting
* #### Keep "do" and "loop" on the same line as its condition
   ```
   /* Yes */
      do while num > 1
         ...stuff to do
      end
     
   /* No */
      do
         while num > 1
            ...stuff to do
      end
   ```

* #### Align "else/otherwise" with "if/when" respectively and align each "end" with "do/select"
   ```
      /* Yes */
         if num > 1000 then
            say "big"
         else if num < 1000 then
            say "small"
         else
            do
               say "One thousand"
               ...some other stuff to do
            end
  
         select
            when num > 1000 then
               say "big"
            when num < 1000 then
               say "small"
            otherwise
               do
                  say "One thousand"
                  ...some other stuff to do
               end
         end

         do while x > 100
            if y > 5 then 
               do
                  say "big"
                  x = x + 1
               end
         end
  
      /* No */
  
         if num > 1000 then
            say "big"
            else if num < 1000 then
            say "small"
            else
               do
                  say "One thousand"
                  ...some other stuff to do
                  end
  
         select
            when num > 1000 then
               say "big"
            when num < 1000 then
               say "small"
            otherwise
               do
                  say "One thousand"
                  ...some other stuff to do
                  end
            end
  
         do while x > 100
            if y > 5 then 
               do
                  say "big"
                  x = x + 1
                  end
            end
         
   ```

### String Concatenation
* #### Prefer explicit concatenation over implicit
   ```
   /* Yes */
      name = "Fred"
      say "My name is " || name || "."
      
      say 2 || "5"
      say "I like " || "apple pie."
   
   /* No */
      name = "Fred"
      say "My name is" name"."
      
      say 2"5"
      say "I like" "apple pie"
   ```

### PARSE
* #### End a parse with a variable named "." or "trash" to catch leftover input

### Error Handling
* #### Include error handling for programs with a cyclomatic complexity greater than ten
   Use "signal on syntax", "signal on error", and "signal on novalue" and their 
   appropriate labels.  
   Use error handling only as needed for simpler programs.

### ADDRESS
* #### Uppercase ADDRESS and the environment name being addressed
* #### Enclose in quotation marks
* #### Fully spell out the command, don't assume abbreviations

## Guidelines Specific to Classic Rexx
* #### Avoid special characters in variable names

## Guidelines Specific to ooRexx
* #### Prefer object methods over legacy functions

## Guidelines Specific to NetRexx
* #### When using Java classes, import them explicitly

## Guidelines Specific to CREXX
<!-- TODO -->

## Guidelines for Portability
* #### Avoid using " ¬ " as NOT. Use " \ " instead.
   Portability problem when transferring code to an ASCII platform.

## Tools
* [rexx-lint](https://github.com/shmuelmetz/rexx-lint)

## How to Contribute
This guide is a work in progress. Some guidelines don't have examples to 
illustrate them, others haven't been fleshed out, and still others have not been 
considered yet. As such, nothing is set in stone. If you'd like to contribute, 
feel free to open issues or send pull requests with improvements. See 
contributing.md for details.

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

## License
This guide is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
