#C
#C++
#lang
#lib

# Simple C library

https://github.com/nothings/stb

## Compiling:

```bash
gcc stb_example.c -o stb_example
./stb_example
```

### Example:

```C
#define STB_DS_IMPLEMENTATION
#include "stb_ds.h"
#include <stdio.h>
int main() {
    // Hash map: string keys, int values
    struct { char *key; int value; } *map = NULL;

    // Insert key-value pairs
    hmput(map, "apple", 5);
    hmput(map, "banana", 10);
    hmput(map, "orange", 15);

    // Look up a value
    int banana_value = hmget(map, "banana");
    printf("Value for 'banana': %d\n", banana_value);

    // Iterate over the hash map
    printf("All key-value pairs:\n");
    for (int i = 0; i < hmlen(map); i++) {
        printf("Key: %s, Value: %d\n", map[i].key, map[i].value);
    }

    // Dynamic array of strings
    char **strings = NULL;
    arrput(strings, "hello");
    arrput(strings, "world");

    // Print the array
    printf("Dynamic array contents:\n");
    for (int i = 0; i < arrlen(strings); i++) {
        printf("%s\n", strings[i]);
    }

    // Clean up
    hmfree(map);
    arrfree(strings);

    return 0;
}
```
