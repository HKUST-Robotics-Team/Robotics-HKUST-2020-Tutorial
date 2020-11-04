# General Feedback on HW1
1. Make sure your code can be compiled, some of you fail to do it before submission.
2.	Make sure you will not access any out-of-bound data. This causes [undefined behaviour](https://en.wikipedia.org/wiki/Undefined_behavior) and may crash the program. Most of you get this error due to storing a string in an array which does not have enough size.  
    * For example, if you have an array `char str[10]` and use `scanf("%s", str)` to read input `01/01/2000`, there will be out-of-bounds access. This is because the `01/01/2000` contains 11 characters, the last char being `'\0'` which is written out-of-bounds at `str[10]`.
    * Your program may seem to run fine on your machine because sometime it will not access something critical. But sometimes it will, and of course, an error occurs. Most of you get a low mark because of this. This is your responsibility to avoid the error. You can try compiling with `gcc -fsanitize=address,undefined *.c -std=c18 -o main && ./main` (mac) to compile and check this error. On Windows, I don't know whether it works, if not, Google is your friend.
    * Use `scanf(" %s")` instead of `scanf("%s")`. The space at the front will eat up any previous whitespace (including newlines).
3.	A number of you used `fopen()` with a wrong file access mode. You may refer to [online documentation](https://en.wikibooks.org/wiki/C_Programming/stdio.h/fopen).
4.	I think we have told your under the FAQ of HW1 that you cannot modify i_give_you.h but still, some of you are doing this. This time we let you go but also, this is your responsibility to read all the description of the HW1
5.	Some of you did not follow the input format said in the description of the HW1. This time we let you go but again, it is your responsibility to read the entire description of the homework.
6.	Please remove your own debug messages before submission.
7.	Many of you did not handle the `'\n'` produced  when pressing the enter key. For example, on the menu page, if I type 'D' and press enter, many of you will output something like `Please input a date (DD/MM/YYYY):` followed by the invalid input message. This time we let you go, but it is your responsibility to handle this case next time.
8.	Please do not rely on compiler-specific variables or functions in our homework (e.g. `errno_t`, `strcpy_s`). E.g. if you're using Windows API, it won't compile on other machines.

I want to tell the marks from HW are not the only criteria we consider when deciding who passes on to the next stage. We inspect your code while grading. A low mark in HW does not mean that you have no chance in entering the next stage.
