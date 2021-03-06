# µunit
Minimal, freestanding unit testing for C.

µunit has three simple goals in mind:
 1. Lightweight and freestanding; no memory allocator necessary.
 2. Tiny and simple; it's just a single .h file.
 3. Easy to use.

Show me
-------

Here's a little contrived example of how to set up a couple of tests.

```c
# include <assert.h>
# include <stdio.h>
# include "uunit.h"

extern int myVar;
extern int myOtherVar;

unittest {
    printf("Testing myVar.\n");
    assert(myVar == SOME_VALUE);
}

unittest {
    printf("Testing myOtherVar.\n");
    assert(myOtherVar == SOME_OTHER_VALUE);
}

 . . .

```

µunit consists of just a single header, so including `"uunit.h"` is all that's needed to set it up. It doesn't need a standard library, and doesn't use a memory allocator.

Can I disable unit testing?
---------------------------

Yes. Defining either `NDEBUG` or `NUNITTEST` will stop unit tests from being generated entirely. When disabled `unittest` will expand to an unused function which is discarded by the compiler.

License
-------

µunit is available under the MIT license.
