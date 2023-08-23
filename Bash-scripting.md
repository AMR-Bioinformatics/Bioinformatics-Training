

**This is a continuation of the slides**
[LINK TO SLIDES](https://github.com/Natasha-Adongo/Bioinformatics-Training/blob/main/Slides/INTRODUCTION%20TO%20SHELL%20SCRIPTING.pptx)

 ### PIPES AND FILTERS

**WC**

1. Navigate to the following directory ``cd shell-lesson-data/exercise-data/alkanes``
2. Check the contents of the directory ``ls``
3. Run the following command ``wc ethane.pdb`` -The wc command is the word count command it counts the number of lines,words and characters in a file.
4. Wc can be paired with different flags to get specific outputs eg; ``wc -l *.pdb``
5. The -m and -w can also be used to show the number of charachters and words repectively.
6. You can take your code further and redirect your output to specific file eg ``wc -l *.pdb >lengthsF.txt``
   
_ASSIGNMENT_

Use the wc -m and -w to get the total number of charchers and words and save the output in the file lengthsF.txt(the one you had creatd above)

*NB* Do not loose the initial contents of the file lengthsF.txt


**SORT**

The sort command in bash is used to arrange records in a particular order.

It uses the following features when sorting;

1. Lines starting with a number will appear before lines starting with a letter.
2. Lines starting with a letter that appears earlier in the alphabet will appear before lines starting with a letter that appears later in the alphabet.
3. Lines starting with a uppercase letter will appear before lines starting with the same letter in lowercase.

Run the following:-
1. ``sort lengthsF.txt`` When you use the sort function without any flag it sorts in alphanumeric order
2. ``sort -n lengthsF.txt > sorted_Lengths.txt`` This allows you to sort in numerical oder
3. ``head -n 1 sorted_Lengths.txt``  Gives the first records of the sorted file
4.  ``sort -o sorted_Lengths.txt newSorted_lengths.txt`` Unix also gives you an option to sort and redirect your output to a new file.



_ASSIGNMENT_

Use the -r flag to sort you file in reverse order and then use the -c to check if the file is sorted 




**PIPE FUNCTION**

A pipe allows the transfer of one command output to another command for further processing (The stdout of one command can be the stdin of another command) .In bash ``|`` this the pipe function.

1. In our above example we could have done sort and head at the same time, ``sort -n lengths.txt | head -n 1``
2. Or we could have listed the number of lines in our alkanes folder that end with .pdb and pipe this to the wc command ie;- `` ls -l *.pdb | wc -l ``

_ASSIGNMENT_

Use the word count command on the .pdb files to count the lines, then pipe you output to the sort command based on the numerical order and then pipe this into the
head command to give you the first 3 rows/records and save it in a file called my_sortedOut.txt




This tutorial is called pipes and filters we have already looked at the pipe function and the filtering option involves programs like _wc_ or _sort_ that transforms your input into a desired output. In scripting the unix shell reads lines of  programs from the standard input to lines of programs on the standard output.

**THE CUT COMMAND**

The cut command is used to remove or cut out a certain section of each line, this can be byte position, charachter, field etc. cut uses tab as a default field delimiter, but it can also work with other delimiter when specified with the ``-d`` option 

```
_NB_: This is different from the ``cat`` command, this command gets its name from the word concatenate, ie join together my output and print it out on the screen
Lets try it out cd /shell-lesson-data/exercise-data/alkanes
cat length.txt
```

Lets try the same code with the ``cut`` command: ``cut length.txt`` - what is the error message you get?

```
cut: you must specify a list of bytes, characters, or fields
Try 'cut --help' for more information.
```

- Let us now explore how the cut command works, in this lesson we will explore cut with the -f (field) flag/option
- ``cd ../animal-counts``
- ``ls``
- ``cat animals.csv``
- ``cut -d "," -f 2 animals.csv`` 


**THE ECHO COMMAND**

This is an in built bash command that allows the users to display lines of texts or strings that are passed as arguments.It is commonly used in shell scripts and batch files to output status text to the screen or desired files.

Type in the following:

- ``echo geeks for geeks is good to learn scripting with``
- Redirecting the echo output  ``echo use geeks4geeks >> test.txt``



**LOOPS**

This is a programming construct that allows the repeation of a command or a set of commands for a given number of items in a list.In bash scripting there are a total of 3 looping statements that can be used :-
1. While loop statement
2. For loop statement
3. Until statement

   To alter the flow of a loop statement two commands are used :- Continue
                                                                - Break

   The most commonly used loops in bash are the for and while loops.
   
    _For Loop_
   
 The for loop operates on lists of items. It repeats a set of commands for every item in a list.

   Syntax

   ```

   for <var> in <value1 value2 ... valuen>
   do
    <command 1>
    <command 2>
    <etc>
   done
   
   ```

 
  ```

# The word "for" indicates the start of a "For-loop" command
for thing in list_of_things 
#The word "do" indicates the start of job execution list
do 
    # Indentation within the loop is not required, but aids legibility
    operation_using/command $thing 
# The word "done" indicates the end of a loop
done

```

Let us apply this,

- cd to the directory /exercise-data/creatures.
- Check the contents of the files
- We want to create a for loop that filters out the classification of the species that is in the second line of each file: *what commands do you think we will use?*

```

for filename in basilisk.dat minotaur.dat unicorn.dat
do
     echo $filename
     head -n 2 $filename | tail -n 1
done

```

Lets create another loop that and implement the break statement

```
#Start of for loop
for a in 1 2 3 4 5 6 7 8 9 10
do
        # if a is equal to 5 break the loop
        if [ $a == 5 ]
        then
                break
        fi
        # Print the value
        echo "Iteration no $a"
done

```


_ASSIGNMENT_
1. Can you try this same loop but implement the ``continue`` statement
2. Write a for loop that echoes numbers 0 to 9

##### NB

If the shell prints > or $ then it expects you to type something, and the symbol is a prompt.

If you type > or $ yourself, it is an instruction from you that the shell should redirect output or get the value of a variable.




_While Loop_

A while loop is a statement that iterates over a block of code till the condition specified is evaluated to false. If the condition is true then the commands inside the while block are executed and are iterated again after checking the condition. Also if the condition is false the statements inside the while block are skipped and the statements after the while block are executed. 

While loop syntax

```
while [condition]
do
    # Code to be executed repeatedly
done
```
- The loop continues executing the code within the do block as long as the specified condition evaluates to true
- The condition is an expression that is checked before each iteration of the loop. If the condition is true, the loop continues; otherwise, it terminates.
- Common operators used include :- ``-eq`` -equal, ``-ne``- not equal, ``-lt`` -less than, ``-le`` - less than or equal to , ``-gt`` -greater than or  ``-ge``- greater than or equal to.

  ```
  #!/usr/bin/bash 

  a=7
  while [ $a -gt 4 ];
  do
    echo $a
    ((a--))
  done

  echo "Out of the loop"
  ```


Read more on the while loop and train on it  use [Geeks4Geeks](https://www.geeksforgeeks.org/bash-scripting-while-loop/)






   
