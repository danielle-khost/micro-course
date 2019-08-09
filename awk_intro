# Genome tips and tricks

## Manipulating files with awk
### What is awk?

Invented in the 1970's, awk is a scripting language included in most Unix-like operating systems. It specializes in one-liner programs and manipulating text files.

In many cases, if you're parsing information from a text file (such as a BED file, FASTA file, etc.), you could write a Python script...or you could do it with awk in a single line!

### Syntax
awk scripts are organized as:

`pattern { action }`

Meaning that every time that the pattern is true, awk will execute the action in the brackets. By default the pattern matches every line, so the action will be taken every line, e.g. the following command that prints every line:

`awk '{print}' input.txt`

Input to awk is split into **records** and **fields**.
- By default, **records** are separated by newline character, i.e # of records = # of lines in input file
- Each record is subdivided into **fields**, i.e. columns


### Advanced examples
While awk is good for simple text parsing tasks, you can get quite fancy with it!
