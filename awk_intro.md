# Genome tips and tricks

## Manipulating files with awk
### What is awk?

Invented in the 1970's, awk is a scripting language included in most Unix-like operating systems. It specializes in one-liner programs and manipulating text files.

In many cases, if you're parsing information from a text file (such as a BED file, FASTA file, etc.), you could write a Python script...or you could do it with awk in a single line!

### Syntax
awk scripts are organized as:

`pattern { action; other action }`

Meaning that every time that the pattern is true, awk will execute the action in the brackets. By default the pattern matches every line, so the action will be taken every line, e.g. the following command that prints every line:

`awk '{print}' input.txt`

The two most important patterns are `BEGIN` and `END`, which tell the action to take place before any lines are read and after the last line.

 `awk 'BEGIN{sum=0} {sum+=$3} END{print sum}'`

 The above line sets a variable at the start of the script, adds the value in the third column every line, then prints its value at the end.

 ---
### Input and output
Input to awk is split into **records** and **fields**.
- By default, **records** are separated by newline character, i.e # of records = # of lines in input file
- Each record is subdivided into **fields**, i.e. columns

There are several important built-in variable in awk. The fields (columns) of each record are referred to by `$number`, so the first column would be `$1`, second would be `$2`, etc. `$0` refers to the entire record.<br/>
So to print the fifth column of each line in the file, we'd use:

`awk '{print $5}'`

And if we wanted to print the first, third, and sixth:

`awk '{print $1,$3,$6}'`
<br/>
<br/>

awk has several other built-in variables that are useful for parsing text:

>FS: field separator (default: white space)<br/>
OFS: output field separator, i.e. what character separates fields when printing<br/>
RS: record separator, i.e. what character records are split on (default: new line)<br/>
NR: number of records in input (# lines by default)

---
### Practice
Using awk:<br/>
- Write a command to calculate that average of the third column of a tab-separated list and output it.


### Advanced examples
While awk is good for simple text parsing tasks, you can get quite fancy with it!
