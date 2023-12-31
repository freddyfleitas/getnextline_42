# Get Next Line - @42Born2Code

![Screenshoot](https://github.com/freddyfleitas/getnextline_42/blob/master/gnl.png)

**DISCLAIMER:** Consider my code as a reference; the bonus functions correctly, but the moulinette does not approve. There might be a double-free issue, so exercise caution. I'll provide an update if I manage to resolve it.

## Table of Contents

- [Project objective](#project-objective)
- [Project complexity](#project-complexity)
- [How to solve GNL?](#how-to-solve-gnl)
- [Graphical Example (BUFFER_SIZE = 4)](#graphical-example-buffer_size--4)
- [Recommendations](#recommendations)
- [Helpful Resources](#helpful-resources)

## Project objective

The "Get Next Line" project aims to create a function, **char *get_next_line(int fd)**, capable of reading a file descriptor and returning the line obtained up to the first newline character.

## Project complexity

The complexity lies in the specific approach we take to address the problem. The peculiarity is that the number of bytes to read until the newline is variable and depends on the BUFFER_SIZE value. The implementation involves using the read function, managing a static variable, and dynamic memory allocation, adding an additional challenge.

## ¿How to solved GNL?

**HINT: Get familiar with the project, make a main, from which obtain an fd through the open function. After this, try to print what is contained in the file ;)**

Before diving into implementation, it is crucial to understand how our program will work to obtain the line:

**STEP 1:** The program must read from the descriptor (fd) and store in a buffer as many times as BUFFER_SIZE allows, until encountering a newline character \n.

**STEP 2:** Extract from the buffer the portion stored up to the \n.

**STEP 3:** Modify the buffer to position ourselves after the \n. It's important to note that the function should be able to read an entire file if called repeatedly.

## Graphical Example (BUFFER_SIZE = 4):

Consider a file **EXAMPLE.txt** with the content:

```
Hello
How are
You
```

**STEP 1:** Read and store in the buffer.

Buffer: Hello\nHo

**STEP 2:** Extract line.

Line: Hello\n

**STEP 3:** Modify the buffer.

Buffer: Ho

## Recommendations:

- Structure each step as an independent function to facilitate development and debugging.
- Study the functions in the libft library and consider which ones might be useful for your implementation.
- Make necessary adjustments to functions; don't worry if implementing one results in a segfault—it's part of the process.

## Helpful Resources:

To achieve optimal implementation, understanding the workings of write, the data types used, and the purpose of static variables is essential. Here are some useful resources:

- [Read data from a file using read in C](https://www.educative.io/answers/read-data-from-a-file-using-read-in-c)
- [Static Variables in C](https://www.it.uc3m.es/pbasanta/asng/course_notes/variables_en.html#variables_static)
- [Explanation of the use of static variables in C](https://stackoverflow.com/questions/572547/what-does-static-mean-in-c)
