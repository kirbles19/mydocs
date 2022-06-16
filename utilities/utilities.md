Intro text of what role utility steps play in Torq.

## Array utilities
Use these utilities to work with arrays.

### Append to array
Adds an object (string, integer, etc.) to the end of an existing array or instantiates an array to which objects will later be added. If no array is given, or the given array does not exist, the member will be added to an empty array.

**Input**

`["joe", "jane", "jill"]`

**New_Member**

"bob"

Output

["joe", "jane", "jill", "bob"]

Chunk array
Divides an existing array into smaller arrays.

Input

["joe", "jane", "jill", "bob", "doug", "mary"]

Chunk_Size

3

Output

[ [ "joe", "jane", "jill"], [ "bob", "doug","mary" ] ]

Concat arrays
Combines 2 arrays into a single array. Objects that appear in both arrays are duplicated in the concatenated result.

Input

["joe", "jane", "jill"]

Second_Array

["bob", "doug", "mary", "jill", "joe"]

Output

["joe", "jane", "jill","bob", "doug","mary", "jill", "joe"]
