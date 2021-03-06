# Python Data Types and Structures

## Deques
1. Fast inserts and pops from either side
2. Not sliceable, but can be sliced using `itertools.islice(iterable, start, end)`
3. maxlen property can be set upon instantion to restrict the length of the deque
4. `deque.rotate(n)` allows you to rotate the deque by n elements where if n greater than 0
shift it right, and if n less than 0 shift it left 
5. adds `appendleft`, `popleft`, `extendleft` to do operations to the left

## ChainMap
1. Relate dictionaries to one another by putting all dictionaries into one list
2. You can index any key from all dictionaries by indexing through the chainmap
3. You can also get a dictionary at i, by accessing the `maps` list attached to the chainmap
4. the chainmap will prioritize the key that comes first if the dictionaries that compose 
the chainmap have the same key
5. You can use `new_child` to create a child chainmap with modified properties
6. you can use `parents` to find the parents of a chainmap

## Counter
1. There are three ways to initiliaze a counter, through a sequential object, a dictionary, or tuple
2. the `update` method takes an iterable or dictionary to update the count of each item within the counter
3. The `update` method will not override values within the counter, rather add the count to previously existing keys
4. Counter objects return 0 for keys that aren't stored within
5. `Counter.elements()` returns an iterator where counts below one are not included and order isnt guaranteed
6. `Counter.subtract()` works exactly like the update method, except for subtracting values from keys

## Ordered Dictionaries
1. Remember the insertion order of items
2. When iterated over, the items will be returned in the order they were inserted
3. If two ordered dictionaries have the same insertion order, then they are equal in terms of value
Whereas order doesn't matter in non ordered dictionaries
4. The `update` function will maintain the same insertion order as the iterable passed in and the previous
5. Primarily used with creating sorted dictionaries
 
## defaultdict
1. It is a subclass of dict
2. Instead of throwing a key error when trying to access a key that doesn't exist,
it will instead return a default value generated by the function provided to it.
3. Accepts an argument, default_factory, being the function used for generating values
for keys that dont yet exist within the default dictionary
4. Can be provided a custom function to determine the dictionaries default values

## named tuples
1. Named tuple inherits from tuple, making it reverse compatible with tuples
2. namedtuples are instantiated with the first value being the name and the second value
being either a string consisting of white space/comma separated values 'x y z' / 'x, y, z'
or an iterable list containing elements to be used as the field names
3. named tuple provides `_asdict`, which returns an ordered dictionary in which the order
is dictated by the order of the fields upon creation of the named tuple object
4. namedtuple provides `_replace` which returns a new instance of the named tuple where
one or more of the values have been replaced 
5. namedtuple provides `_make`, which allows you to create a named tuple instance given an iterable

## Arrays
1. Operate very similiarily to lists, however their contents must be of a single type.
2. The type of array is determined at creation time, and is indicated by a type code provided as 
an argument to the array
3. Supports all normal sequence operations (indexing, slicing, concatenation, and multiplication)
4. Arrays are much much more efficient in terms of storing data than lists (for data of the same type)
5. An integer array of 1 million integers uses approximately 90% of the memory required to construct
an integer list of the same 1 million integers
6. It is recommended to operate on arrays in place using functions like `enumerate`, in order
to preserve the efficient memory storage and to only copy when absolutely necessary
7. the memory advantage of arrays is negated when using  operations on them that transform them into
lists, so using something like a generator would be maintain the memory efficieny while allowing
you to operate on the array.
8. Not suitable for performing operations on a matrix of vectors
