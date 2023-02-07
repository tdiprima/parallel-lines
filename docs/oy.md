## Oy.

"Then build the programs and test them: `make test`"

An error on something I know nothing about.  How nice...


### But it said build the programs first.  So...
```sh
mkdir output
gcc *.c -o output
```

OK. That's a little bit better.


```sh
gcc "*.c" -o "output"

# linked.c:3:10: fatal error: 'omp.h' file not found
# #include <omp.h>
#         ^~~~~~~
```

So we're back to square 1.  It's installed, but it can't find the darn thing.  Fabulous.

### Compile all C files in a directory

[Compile .c files](https://stackoverflow.com/questions/19765536/compile-all-c-files-in-a-directory-using-gcc-compiler-in-cmd)

[commandlinefu.com](https://www.commandlinefu.com/commands/view/3230/compile-all-c-files-in-a-directory)

```sh
ls *.c | while read F; do gcc -Wall -o `echo $F | cut -d . -f 1 - ` $F; done
```

```sh
# OR
for F in *.c; do gcc -Wall -o ${F%.c} $F; done
```

<br>

![](../docs/commandlinefu.jpg)

### Resources

[Developing C programs on Mac OS](https://www.cs.auckland.ac.nz/~paul/C/Mac/)

[CMake by Example](https://mirkokiefer.com/cmake-by-example-f95eb47d45b1)