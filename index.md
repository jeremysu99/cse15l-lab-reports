# Lab Report 5

## Part 1

## EdStem Post:

Hi! I'm having trouble with this method I wrote that is supposed to find the maximum value of two integer arrays. The symptom states that there is an `IndexOutOfBounds` error on my first test, but I'm not sure where it comes from. I'm guessing it has something to do with how I access the arrays, but I'm still confused.

Here's my code along with the tester and the terminal output:

<img width="448" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/0f73dce3-5668-47a0-85b3-40d3f869ea9f">

<img width="1164" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/b6077ca6-ae8c-4962-a10f-18007a7aa14a">

<img width="586" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/4155f613-5b97-4242-b058-6ff1f24eeecf">

## TA Response:

Could the bug be that your for loop causes an `IndexOutOfBounds` error when the two inputted arrays have different length? Maybe try first iterating over the first array and creating a second for loop for the second array to update `max` accordingly? For the second for loop, change the bounds for the loop accordingly too. Doing it this way will help break down your code into more digestable steps that you can combine later when it runs as planned.

## Student Response:

Thanks! My code works as expected now! I realized that the bug was that my initial for loop causes an `IndexOutOfBounds` error whenever the first array is longer, and when the second array is longer, it potentially returns a wrong value. This was because the loop only iterated through the length of the first array when simultaneously checking each array's corresponding value at index `i`, disregarding the length of the second array. This was evident in the terminal output when I first ran `bash test.sh`, where it stated that line 7 caused an error, which was where the second if statement was. By creating a second for loop, I could iterate through the second array separately to properly check each of its values to see when to update the `max`.

Updated Code:

<img width="487" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/f25f9d87-7a5f-4b77-b8e1-2de18b689cee">

Terminal Output:

<img width="391" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/1fb67895-db23-4648-897f-ddcde68b8c5a">

## File and Directory Structure:

<img width="163" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/f0d2353f-d488-462a-a58b-82064f443054">

Contents of each file before the fix:

`ListExample.java`:

<img width="448" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/0f73dce3-5668-47a0-85b3-40d3f869ea9f">

`Tester.java`:

<img width="1164" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/b6077ca6-ae8c-4962-a10f-18007a7aa14a">

`test.sh`:

<img width="751" alt="image" src="https://github.com/jeremysu99/cse15l-lab-reports/assets/116580698/47aa6bc2-4916-47c7-9d7a-b1cd5dfdce44">

## Commands Used to Trigger the Bug:
`bash test.sh`

## Description of What to Edit:

In the `ListExample.java` file, delete the entire second if statement block. Then, insert a second for loop underneath the first one and above the return statement that iterates through the second array and checks if each entry in the array exceeds the `max` value, in which case `max` should update to that new value (similar to the first for loop, just across the second array now). 

## Part 2

In the second half of this quarter, I learned a lot of interesting things about vim that I found through the previous lab report. For example, commands like `r` to replace text, `gg` to jump to a line, and `Ctrl + f and b` to quickly maneuver the cursor, were all pretty cool to use when I was learning vim. It made me feel professional navigating through files from the terminal just using a keyboard.
