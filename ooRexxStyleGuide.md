# Open Object Rexx Style Guide by Matt Ferlita
Rexx doesn't really have an official style guide. While learning ooRexx, I 
thought I should figure something out. While Rexx emphasizes a "do it your own 
way" approach, this might be detrimental in the open-source scene and larger 
code bases where communicating with your fellow programmers is just as important
as talking to the computer. I've reviewed the official ooRexx documentation, 
other style guides, and styling recommendations from various RexxLA talks and 
have come up with the following. Please note that at this point, this is a work 
in progress.

| Element                 | Format                          | Examples                 |
|-------------------------|---------------------------------|--------------------------|
| Keyword Instructions    | UPPERCASE                       | PARSE<br/>SAY            |
| Built-in Functions      | UPPERCASE                       | RANDOM()<br/>CHAROUT()   |
| Directives              | UPPERCASE                       | ::CLASS<br/>::INCLUDE    |
| Methods and Routines    | camelCase                       | append<br/>appendAll     | 
| Variables               | camelCase<br/>or<br/>snake_case | other_gems<br/>myChapter | 
| Classes                 | PascalCase                      | .Array<br/>.DateTime     |
| Boolean and Nil         | lowercase                       | .nil<br/>.true           | 
| Environment Directories | lowercase                       | .environment<br/>.local  | 
| Runtime Values          | lowercase                       | .line<br/>.rs            |
| Runtime Collections     | locercase                       | .methods<br/>.resources  |
| Standard Stream         | lowercase                       | .stdin<br/>.stdout       |
| Monitor Stream          | lowercase                       | .input<br/>.output       |
| Runtime Info            | PascalCase                      | .RexxInfo                |
| Runtime Context         | lowercase                       | .context                 |

1. Write code that is clear, not clever.
2. Different cases are used for identifiers. See table above.
3. Use meaningful names for variables, routines, classes, and methods.
4. Avoid single character names.
5. Prefer two spaces for indentation.
6. Prefer 80 character line length.
7. One statement per line.
8. Comment generously and explain your intent.
9. Leave whitespace around operators (a = 1 + 1). This improves readability greatly.
10. Keep routines and methods small.
11. If you call code only once, don't make it a routine or a method.
12. Avoid deeply nested if statements and keep them simple.
13. Align related code.
14. Separate logical sections with one blank line.
15. Prefer object methods over legacy functions.
16. Avoid unnecessary abbreviation.
17. Use clear program headers that explain what your program does.
18. In the Directives section, use comment lines to separate ::ROUTINE  
    and ::CLASS blocks.