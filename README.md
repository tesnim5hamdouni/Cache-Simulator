# Cache-Simulator
This C code aims at simulating cache behvior. It takes a valgrind memory trace as input, simulates the hit/miss behavior of a cache memory on this trace, and outputs the total number of hits, misses, and evictions.

## Use
The simulator takes the following command-line arguments:

Usage: 

'./csim [-hv] -s _s_ -E _E_ -b _b_ -t _tracefile_'

-h: Optional help flag that prints usage info

-v: Optional verbose flag that displays trace info

-s: Number of set index bits (S = 2s is the number of sets)

-E: Associativity (number of lines per set)

-b: Number of block bits (B = 2b is the block size)

-t: Name of the valgrind trace to replay


## Output
The output should look somthing like this:
    linux> ./csim -s 4 -E 1 -b 4 -t traces/yi.trace
    hits:4 misses:5 evictions:3


## Notes on implementation
Feel free to generate your own trace files using valgrind! Note however that is this version of cache simulator we ignored 'I' ops and only dealt with L, S and M=(L+S - thus resulting in an additional hit!)
For evictions, we used Least Recently Used Policy
