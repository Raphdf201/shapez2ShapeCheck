# Shapez 2 all possible shapes

This project lists all the possible shapes in Shapez 2 by bruteforce.
This fork changes little things to make the compiling process easier

### Credits

- [Original program](https://github.com/cpcp1998/shapez2)
- [Hash maps](https://github.com/skarupke/flat_hash_map)

## Requirements
1. A C++ compiler supporting C++23 (use -std=c++23 argument)
2. Enumerating all the shapes for Normal and Hard scenarios (4 layers, 4 parts per layer) takes ~32MB memory and ~1.5 minutes.
3. Enumerating all the shapes for Insane scenario (5 layers, 4 parts per layer) takes ~8GB memory and ~2 hours.

### Facultative requirements
make(makefile) or cmake >= 3.30

## Usage
1. Compile the search and lookup files

1.1. Manual method using g++
```
g++ -o search4 search.cpp -std=c++23 -O3
g++ -o lookup4 lookup.cpp -std=c++23 -O3
g++ -o search5 search.cpp -std=c++23 -O3 -DCONFIG_LAYER=5
g++ -o lookup5 lookup.cpp -std=c++23 -O3 -DCONFIG_LAYER=5
```

1.2. Use the make command (linux only)
```
make ALL
```

1.3. Use cmake
```
mkdir build
cd build
cmake ..
cmake --build .
```

2. Enumerate all the shapes and store in a binary file
```
$ ./search4 dump4.bin
...
# shapes: 349728289
# halves: 8148
# shapes whose halves aren't stable: 2002457
# quarters: 152
```

3. Check whether a shape can be made in the game
```
$ ./lookup4 dump4.bin P---P---:P-------:cRCu--Cu:--------
The shape is creatable
```

4. We can do similar things for 5 layers
```
$ ./search5 dump5.bin
...
# shapes: 26929624298
# halves: 67669
# shapes whose halves aren't stable: 251172538
# quarters: 476
$ ./lookup5 dump5.bin P-------:P---P---:P-------:cRCu--Cu:--------
The shape is not creatable
```
