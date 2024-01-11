![image](https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/da4b07ab-0f1b-4ffd-ac32-4818ad1b84e6)
   
These are the three commands for `cd` `ls` and `cat` without any arguments. Shown in line 1, 2, and 3.

The working directory was originally /lecture1, but it changes to the root directory when `cd` is used because the command changes the directory to the root since no argument was provided. This output is not an error.

Then, `ls` outputted the folder lecture1 because the command is intended to print out the names of files within the working directory, which was just the root directory, and the only child folder beneath it is the lecture1 folder. This output is not an error.

Finally, the `cat` command printed nothing because there are no files to be read since no arguments were passed through. The current working directory is the root directory, and this output is not an error.

![image](https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/937703ad-93d3-4b18-844a-a4615574a2ea)
   
These are the three commands for `cd` `ls` and `cat` with the argument as a directory. Shown in line 1, 2, and 3.

The working directory was originally the root directory, but it changes to /lecture1 when the command is run because `cd` changed the directory to the child folder lecture1 as specified by the argument. This output is not an error.

Then, `ls` outputted the contents of the folder lecture1 because this command is intended to print out the names of files within the working directory, which was /lecture1. The 4 file names were then correctly outputted. This output is not an error.

Finally, the `cat` command gave an error stating that the 'messages' argument is a directory. This occured because the `cat` command expects the argument to be a file, not a directory, so that it can properly print out the contents of the file. Therefore, a directory argument gave an error. The current working directory is still /lecture1.

![image](https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/81fd36b7-c809-4a14-9ccb-eb855725b06a)
   
These are the three commands for `cd` `ls` and `cat` with the argument as a file. Shown in line 1, 2, and 3.

The working directory was originally /lecture1, and an error occurs because the `cd` command expects the argument to be a directory, not a file. However, because the file Hello.java is passed through the argument instead of a directory, the error states that Hello.java is not a directory.

Then, `ls` outputted the name of the Hello.java file itself because Hello.java is a file, not a directory. `ls` is intended to print out the names of files within the argument, but because Hello.java itself is a file, the only output is its own name. This output is not an error, and the current working directory is still /lecture1.

Finally, the `cat` command outputted the contents of the Hello.java file. This is because the `cat` command intends to print out the contents of a specified file, and it does so with Hello.java. The current working directory is still /lecture1, and the output is not an error.
