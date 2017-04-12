# LEX - ( A Lexical Analyzer Generator )
+ Lex is a program generator designed for lexical processing of character input streams. It accepts a high-level, problem oriented specification for character string matching, and produces a program in a general purpose language which recognizes [regular expressions](https://en.wikipedia.org/wiki/Regular_expression). The regular expressions are specified by the user in the source specifications given to Lex. The Lex written code recognizes these expressions in an input stream and partitions the input stream into strings matching the expressions. At the boundaries between strings program sections provided by the user are executed. The Lex source file associates the regular expressions and the program fragments. As each expression appears in the input to the program written by Lex, the corresponding fragment is executed.
+ Although Lex is often used as a _front-end to a parser_, it has been designed such that it can be used stand-alone. Used in this fashion, Lex makes for a simple but very powerful text processing tool.
+ Lex is not a complete language, but rather a generator representing a new language feature which can be added to different programming languages, called ``host languages.'' Just as general purpose languages can produce code to run on different computer hardware, Lex can write code in different host languages. The host language is used for the output code generated by Lex and also for the program fragments added by the user. Compatible run-time libraries for the different host languages are also provided. This makes Lex adaptable to different environments and different users. Each application may be directed to the combination of hardware and host language appropriate to the task, the user's background, and the properties of local implementations. 
+ _At present, the only supported host language is C._

## Lex Program Structure
A lex program has the following basic structure:
``` 
%{
   C declarations and includes
%}
   Lex macro definitions and directives
%%
   Lex Specification
   in the form of pattern/action statements like this:
   keyword    { my_c_code(yytext); }
%%
   C language program (the rest)
```
However, the only mandatory part is the first %%
