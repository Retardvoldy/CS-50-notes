[scratch main func]: https://github.com/WHKcoderox/CS-50-notes/blob/master/images/Screenshot-2016-fall-lectures-1-at-1m48s.png "Damnit Scratch"
[scratch while loops]: https://github.com/WHKcoderox/CS-50-notes/blob/master/images/Screenshot-2016-fall-lectures-1-at-3m35s.png "Scratch while true loops"
[scratch for loops]: https://github.com/WHKcoderox/CS-50-notes/blob/master/images/Screenshot-2016-fall-lectures-1-at-4m9s.png "Scratch for loops"
[scratch variables]: https://github.com/WHKcoderox/CS-50-notes/blob/master/images/Screenshot-2016-fall-lectures-1-at-4m50s.png "Scratch Variables"
[scratch boolean]: https://github.com/WHKcoderox/CS-50-notes/blob/master/images/Screenshot-2016-fall-lectures-1-at-6m3s.png "Scratch Booleans"
[scratch ifelse]: https://github.com/WHKcoderox/CS-50-notes/blob/master/images/Screenshot-2016-fall-lectures-1-at-7m21s.png "Scratch Conditioning"
[scratch arrs]: https://github.com/WHKcoderox/CS-50-notes/blob/master/images/Screenshot-2016-fall-lectures-1-at-8m50s.png "Scratch Arrays"
[cs50 ide]: https://github.com/WHKcoderox/CS-50-notes/blob/master/images/Screenshot-2016-fall-lectures-1-at-20m14s.png "The CS50 Ide"
[integers]: https://github.com/WHKcoderox/CS-50-notes/blob/master/images/Screenshot-2016-fall-lectures-1-at-50m27s.png "Integer Operators"
[sizeofs]: https://github.com/WHKcoderox/CS-50-notes/blob/master/images/Screenshot-2016-fall-lectures-1-at-57m9s.png "Variable memory allocations"
[specialchars]: https://github.com/WHKcoderox/CS-50-notes/blob/master/images/Screenshot-2016-fall-lectures-1-at-58m36s%20(1).png "Special Characters"
[placeholders]: https://github.com/WHKcoderox/CS-50-notes/blob/master/images/Screenshot-2016-fall-lectures-1-at-58m36s.png "Placeholders"

# Video Lesson 1 Notes

### 'Scratch vs. C', 'Loops', 'Arrays', 'Hello, C' - From Scratch to C
While true loops indirectly imply that there are more sophisticated terminating conditions to be handled within the loop body, and that the loop by default should not break.
Scratch:
![Scratch Main Function][scratch main func]
![Scratch Forever][scratch while loops]
![Scratch Repeat][scratch for loops]
![Scratch Variables][scratch variables]
![Scratch Boolean][scratch boolean]
![Scratch If-Else][scratch ifelse]
![Scratch Lists][scratch arrs]
___
C Syntax:
```C
#include <stdio.h> // including C's standard input/output library (stdio) as header file (holding all the declarations of emepty member funcs (abstract classes) which are defined i.e. coded elsewhere to make the code neat) 

int main (void) { // no arguments, the main function is the function that runs every time the file is executed

  while (true) {
    // while (true) loops
  }
  
  for (int i = 0; i < limit; i++){
    // for loops
  }
  
  printf("Hello World\n"); // formatted print, this prints Hello World followed by a newline character (\n)
  
  if (condition) {
    // if condition, do this
  }
  else if (another_condition) {
    // if not condition but another_condition (preferably), do this
  }
  else {
    // if neither of the above, do this
  }
  
  /* arrays */
  // either
  type arr_name[max_size];
  // or
  type arr_name[optional_max_size_n] = {item_1, item_2, item_3... item_n}; // maximum n-sized array
  
  // Incrementing
  int C = 0;
  C++; // yearh!
  C += 1; // same as above, but not as cool.
  C = C + 1 // same-o lame-tho
}
```
***

### 'Compiling' - Behind the 'C'enes
- C's code needs to be compiled into machine code (virtually unreadable bytecode) before it is able to run
- C's language philosophy is that the code can compile anywhere that has a specialised compiler for the hardware and so making the code usable for different things. **:D** *(However, this also means you need to recompile your code for every edit you make :()*
- Compilers are made for future users to leverage as tools to have a more convenient time developing (thus supporting the developers).
- C compilers are **platform specific**, in the sense that *it only runs for one specific configuration*. Thus it is a build once, compile anywhere kind of language.

### 'The CS50 IDE' - Harvard software for CS50
![cs50.io][cs50 ide]
An Integrated Development Environment or IDE for short is a program that bundles certain features together and creates a more seamless development experience (thus the name).

Harvard made a webbased application built on top of *Open Source Platform Cloud 9* for CS50 which supports languages C, Python & Javascript etc. that CS50 students will use to write softwares in for the online projects (projects not using C).
Harvard also built a CS50 library for the course. (Added functionality for free)

### 'The Command Line', 'Clang' - Running C files in cs50.io
- This is because the environment is in Linux OS, a remninscient of Unix, known particularly for its Command Line Interface (or CLI for short)

Using a Linux flavour of Ubuntu, where flavours are just the different distributions of something. Linux has many other flavours like Debian or Kali Linux.

- This command below uses the default clang C compiler on Ubuntu (or perhaps the cs50.io default) to compile the file 'helloworld.c'
```.sh
~/directory $ clang helloworld.c
```
Note that the filetype must be specified as *.c*. Also, what is known as the *prompt* is the '~/directory $' bit which is automatically generated each time you press enter in the CLI.
- a.out is the default program name (short for assembly outputs) produced from after compiling the file (it runs after being compiled), and this may be run just by using *./*, which means run this file from this directory (/, or in this case the current directory) and together running it looks like this in the CLI.
```.sh
~/directory $ ./a.out
```
Note that this only happens when you don't specify a program name for when you compile the code.
- CLI arguments in the form of flags (set flags like configuration toggles for whatever tool you use like Clang in this case)
- The '-o' flag can be used in this case to allow program name specifiers. An example would be where
```.sh
~/directory $ clang -o helloworld helloworld.c
~/directory $ ./helloworld
```
Note that after the -o flag the name 'helloworld' is specified, thereafter allowing the ./ *operator*, codename for action (run this) to run the program as helloworld. Neat!
More CLI commands
```.sh
~/directory $ cd [path]            # change directory, navigate to a specified directory.
~/directory $ ls                   # list the files and folders under the current directory.
~/directory $ rm [filename]        # remove a specific file (possibly through a specified directory).
~/directory $ rmdir [foldername]   # remove dir, remove a specific folder (possibly through a specified directory).
~/directory $ mkdir [foldername]   # make dir, make a named folder (possibly through a specified directory).
~/directory $ make [specifiedname] # convenient way to run clang -o, assumes that the source code is the specifiedname.c. Also is not a compiler.
```
Note the [] brackets do not have to be typed into the CLI. They are just there so signpost that you can put whatever you want to replace the entire [] bracket, based on how you intend on varying the behaviour of the evoked command.

### 'The CS50 Library' - Harvard's convenient library
- Placeholders, the reason printf is a formatted print. (there's also scanf which is a formatted scan but never mind)
![placeholders][placeholders]

P.S. more Special Characters:
![specialchars][specialchars]
```C
# include <stdio.h>
# include <cs50.h> // all the hax.

int main (void) {
  string string_variable_name = get_string(); 
  // CS50 library function get_string() to receive input and return that received value and assign it into a variable of class string.
  // the class string comes also from the CS50 library. Typical string declaration in C requires the <string.h> library and are in the form of char arrays as follows
  char std_C_string [max_size] = "blablabla"; // fixed values too :o
  strcat(std_C_string, std_C_string); // the library provides functions like this and strlen(), strcopy() etc. This one concatenates
                                      // the string we just declared (ie. chaining them together)
  
  printf("Hello, %s!\n", string_variable_name); 
  /* 
  * %s in formatted print means I want to insert a string here. 
  * And when the variable string_variable_name is passed in as 
  * an additional argument, %s is where it will get inserted into.
  * Other placeholders may include %d for integer (decimal)
  */
}
```
You may improve the UX or User Experience with more printf()'s to tell the user more about the program.

Layering, as in build simpler smaller things and testing them before moving on, is how coding should be done since the more you code at one go, the more mistakes you make.

Variable Assignment operator **=** shifts value from left to right into that variable. Intuitively.
Proximity & usage frequency of variables determine whether or not you actually need them.
- Proximity: is the definition of the variable found just a few lines above? If so, then by proximity the variable is not needed.
- Usage frequency: how many times is this variable used? If only once, don't bother!

### 'ints.c' - Exploring integer use cases
![Integer operators][integers]
Integer operations only support integer values, without decimal points etc. Also, the int simply ignores the decimals because they do not mean anything within the context of an integer, which is a whole number (effectively discarded)

### 'floats.c' - Exploring variable types
Variable types like *float* and *double* support decimals.
##### Variable types:
- bool: true/false
- char: single character ''
- float
- double: extension of maximum value used to store floats (for bigger decimal point numbers)
- int
- long: extension of maximum value used to store ints (for bigger numbers)
- long long: when long ain't long enough (same size as double, 64 bits of memory)
- string: although in this case it's cs50 hax. Similarly in C++ there's a string library needed to include before you can use strings directly.
...
About sizes...
![Size of][sizeofs]
Note that the sizes are in bytes, which are 8 bits.
**RAM is the place where programs live in, where temporary memory is allocated to things like storing variables etc.**
Storing things that require more than the specified memory size leads to Overflow!
**Some Examples**
- *Lego World* money capping at 4 billion because of choice of integer and not long long
- *Civilisation*'s Ghandi has a 1 on the aggressiveness index which decrements by 2 if adopting democracy leading to the usage of unsigned ints which do not take to negative signs properly to turn the -1 value to 255, making Ghandi maximum aggressive.
- 2015 Article on the Boeing 787 Dreamliner reporting that FAA officials warn software vulnerability caused pilots to lose control of the plane possibly midflight. Also, the plane will lose all power if powered straight for 248 days since **all control units, GCUs simultaneously go into fail safe mode.** The reported cause was that an internal counter to the generator control overflows after 248 days of continuous power. This means that the counter inside runs into memory errors which then cause the plane to reboot, which may happen midflight.

### 'imprecision.c' - Floating point arithmetic
- Floats aren't precise. There's a limit to it, since the arithmetic is basically using integers and then putting the extras behind a decimal point.
- '%.xf' where x is any integer VALUE(hardcoded) allows the placeholder to specify the number of decimal places to print.
- 



