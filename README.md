Progress-CPP
===

A flexible ASCII progress bar for your console based C++ projects.

### Usage
Progress is a header-only library and can be used by simply including the `progress_bar.h` header file.

The bar takes the following options at initialization
- Limit: the total number of ticks that need to be completed
- Width: width of the bar
- Complete Char: the character to indicate completion (defaults to `=`)
- Incomplete Char: the character to indicate pending. (defaults to ' ')

```c++
#include "progress_bar.h"

int main() {

    const int limit = 10000;

    // initialize the bar
    ProgressBar progressBar(limit, 70);

    for (int i = 0; i < limit; i++) {
        // record the tick
        ++progressBar;

        // display the bar
        progressBar.display();
    }

    // tell the bar to finish
    progressBar.done();
}
```
The above code results in the following output

```
[===================>                                                 ] 29% 0.821s
```

### Example
Refer to [main.cpp](main.cpp) file for an example usage. To run it,

```
$ mkdir build && cd build
$ cmake ..
$ make
$ ./ProgressBar
```

Or without `cmake`
```
$ g++ -O3 -I. main.cpp -Wall -std=c++11 -o ProgressBar
$ ./ProgressBar
```

### License
MIT
