```
---
aliases: [Hash Map, Hash Table]
---
```

Tags: 

# Hash Map
In [computing](https://en.wikipedia.org/wiki/Computing), a **hash table** (**hash map**) is a [data structure](https://en.wikipedia.org/wiki/Data_structure) that implements an [associative array](https://en.wikipedia.org/wiki/Associative_array "Associative array") [abstract data type](https://en.wikipedia.org/wiki/Abstract_data_type "Abstract data type"), a structure that can map [keys](https://en.wikipedia.org/wiki/Unique_key "Unique key") to [values](https://en.wikipedia.org/wiki/Value_(computer_science) "Value (computer science)"). A hash table uses a [hash function](https://en.wikipedia.org/wiki/Hash_function "Hash function") to compute an _index_, also called a _hash code_, into an array of _buckets_ or _slots_, from which the desired value can be found. During lookup, the key is hashed and the resulting hash indicates where the corresponding value is stored.

Ideally, the hash function will assign each key to a unique bucket, but most hash table designs employ an imperfect hash function, which might cause hash _[collisions](https://en.wikipedia.org/wiki/Hash_collision "Hash collision")_ where the hash function generates the same index for more than one key. Such collisions are typically accommodated in some way.

In a well-dimensioned hash table, the average cost (number of [instructions](https://en.wikipedia.org/wiki/Instruction_(computer_science) "Instruction (computer science)")) for each lookup is independent of the number of elements stored in the table. Many hash table designs also allow arbitrary insertions and deletions of [key–value pairs](https://en.wikipedia.org/wiki/Attribute%E2%80%93value_pair "Attribute–value pair"), at ([amortized](https://en.wikipedia.org/wiki/Amortized_analysis)) constant average cost per operation.

In many situations, hash tables turn out to be on average more efficient than [search trees](https://en.wikipedia.org/wiki/Search_tree "Search tree") or any other [table](https://en.wikipedia.org/wiki/Table_(computing) "Computing") lookup structure. For this reason, they are widely used in many kinds of computer [software](https://en.wikipedia.org/wiki/Software "Software"), particularly for [associative arrays](https://en.wikipedia.org/wiki/Associative_array "Associative array"), [database indexing](https://en.wikipedia.org/wiki/Database_index "Database index"), [caches](https://en.wikipedia.org/wiki/Cache_(computing) "Cache (computing)"), and [sets](https://en.wikipedia.org/wiki/Set_(abstract_data_type) "Amortized analysis").

## Time Complexity in [[Big O Notation|big O notation]]
Algorithm | Average | Worse case
---|---|---
Space | O(n) | O(n)
Search | O(1) | O(n)
Insert | O(1) | O(n)
Delete | O(1) | O(n)
