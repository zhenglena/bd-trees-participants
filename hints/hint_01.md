### Yes, two separate `TreeMap` objects!

There will be exactly one instance of the `Participant` class for each
participant. However, there can be more than one reference to a single
`Participant` object. Thus, creating two different `TreeMaps` that
will use different keys to map to the same participants allows
multiple ways of searching/sorting the participants.

Remember, a `TreeMap` associates a key with an object. The ***keys*** are
stored in a balanced binary search tree based on the sorted order of the
keys and provides efficient access using the keys. The values that are
associated with each key in a `TreeMap` are actually object references.
Multiple `TreeMaps` using different keys do ***not*** require multiple
copies of the objects. Thus, multiple `TreeMaps` can provide multiple ways
of efficiently accessing and organizing the same set of objects.

Figure 1 shows an example with three objects that each contain a character
attribute and an integer attribute. The objects are `A/2`, `B/3`, and `C/1`.
One `TreeMap` using the character attribute as the keys is shown on the left
with `B` as the root, `A` as the left child, and `C` as the right child.
A second `TreeMap` using the integer attribute as the keys is shown in the
right with `2` as the root, `1` as the left child, and `3` as the right child.

![Figure 1](../../../../../../../../../../resources/trees/MultipleTreeMaps.png)

*Figure 1. Example showing multiple `TreeMaps` indexing the same objects.*
