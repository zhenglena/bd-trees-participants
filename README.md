### Improving `ParticipantDirectory` Using Multiple `TreeMaps`

**Branch name:** trees-prework-participants

**RDE workfows:**
* `rde wflow run trees-prework-participants-participantdirectorytest`
* `rde wflow run trees-prework-participants-participanttest`

Expected time required: 10 min

In this exercise you will add functionality to the `ParticipantDirectory`
example to be able to:

* look up participants by ID number and
* obtain a roster of participants sorted by ID number.

This extra functionality will be accomplished by adding a second
`TreeMap` to the `ParticipantDirectory` class.

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

![Figure 1: Example showing multiple `TreeMaps` indexing the same
  objects.](../../../../../../../../../resources/trees/MultipleTreeMaps.png)

*Figure 1: Example showing multiple `TreeMaps` indexing the same objects.*

### `ParticipantDirectory` Example From Reading

Before we begin, examine the provided code and note the differences
from the code as it was presented in your reading:

* The `ParticipantDirectory` class has an `addParticipant` method that
accepts `String` parameters for the participant's username and full name.
This method then creates a new `Participant` object and stores it in the
`TreeMap`.

* The previous `printRosterByUsername` method has been re-written as
`getRosterByUsername` and instead of printing directly to `System.out`,
it builds and returns a `String` with the participant roster. This will
allow for more flexible use of the roster information by a client
application. (That is, it may still be printed to the console, or it
could be displayed in a GUI component, or it may be sent directly to a
file, to name just a few possibilities.)

* Some new test data is now loaded in the `main` method using `addParticipant`.

**Note**: Completing this exercise does ***not*** require making any
changes to the `Participant` class.

### Exercise

Your task for this exercise is as follows:

1. Add a second `TreeMap` to the `ParticipantDirectory` class to map
`Integer` keys to `Participant` values.

    A) Declare the second `TreeMap` as an instance variable, just under
    the declaration of the `participants` instance variable.
    
    B) Instantiate the new `TreeMap` in the `ParticipantDirectory()`
    constructor.

2. Add a line to the `addParticipant` method to add the newly created `Participant`
object to the new `TreeMap` using its `idNumber` as the key. **Note**: Be sure to
only create one `Participant` object and add that same object to both maps using
the appropriate key for each map.

3. Complete the `getParticipantByID` method that takes an `Integer` id number as a 
parameter and returns the `Participant` object associated with that id number
by the newly added `TreeMap`. **Note**: This method will be very similar to
the `getParticipantByUsername` method.

4.  Complete the `getRosterByID` method that builds and returns a string containing
the current roster of participants sorted by ID number. **Note**: This method
will be very similar to the `getRosterByUsername` method.

5. (*Optional*) Before running the unit tests, add some code to the `main`
method in the `ParticipantDirectory` class to test your new `TreeMap` similar
to the tests of `getParticipantByUsername` and `getRosterByUsername`.

HINTS:
* [Two separate `TreeMaps`?](./hints/hint_01.md)
