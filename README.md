# Implementation of Join Algorithm for SPARQL Query Processing

## Sort-Merge Join Algorithm:

    The Sort-Merge Join algorithm is a type of join algorithm used in database systems to combine data from two tables efficiently.
    It involves two main steps. First, both tables are sorted based on the join keys. Then, the sorted tables are merged
    together, comparing the values of the join keys. When the join keys match, the algorithm combines the corresponding rows to
    form the result set. Sort-Merge Join is particularly effective when the tables are already sorted or when the available memory
    is limited, as it requires scanning the data only once in both tables.

## Hash Join Algorithm:

    The Hash Join algorithm is another type of join algorithm used in database systems to combine data from two tables.
    It involves two main steps. First, a hash table is constructed using one of the input tables based on the join key.
    Then, the other table is scanned, and its join key values are used to probe the hash table for matches. When matching
    keys are found, the algorithm combines the corresponding rows to create the result set. Hash Join is efficient for large
    datasets and works well when the available memory can accommodate the hash table size. It minimizes disk I/O and is
    commonly used in modern database systems for join operations.

## Dataset Description:

    The datasets consists of rows of triplets that arbitrary connects objects to subjects by predicts.
    The dataset that has 10M rows needed to pre-processed so that the useful data can be extracted from html type of tags.
    The dataset that has 100K rows needed to pre-processed and split from ":" so that the triplets can become useful.

## Experiment and Analysis:

    For the experiments we have pre-processed the triplets from files and created a dictionary that has predicates as keys and
    values as objects and subjects.

    Then we have created two functions for each join algorithm and run them for each dataset, while recording the time to run them.

    Recorded times are as follows;
    - hash_join 10M: 35.072656869888306
    - hash_join 100K: 0.3001863956451416

    - sortMergeJoin 10M: 18.016406774520874
    - sortMergeJoin 100K: 0.0920555591583252

    As we can see the sort merge algorithm works almost 2 times faster then the hash join algorithm in our implementations.


## Improved Sort-Merge Join

    this function uses almost the same code as SortMergeJoin function
    difference is it uses ids instead of strings for the join columns
    also experiments shown in place sort is faster than using sorted function in Pyhton
    so replaced sorted function with sort function
    this function is faster than the other one

    Got 19sec execution time comparing to the original sort merge which was 5 seconds faster.
