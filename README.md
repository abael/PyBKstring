# Py-BKString
A python wrapper for the BK String C project.

That project can be found at:
https://github.com/bcmackintosh/bk-string

# Usage

## Import the library

    import bkstring

*Note: This import expects py-bkstring's file structure, that has the shared library located at ./deps/libbkstring.so and the python module at ./bkstring.py*

## Initialize

    b = bkstring.bk_tree()

## Add words

    b.add("foo")

## Add a list of words

    arr = list(["foo", "bar"])
    b.add_list(arr)

## Search

    ls = b.search("foo", 1)
    assert(ls[0] == "foo")

# Close the BK tree

    b.close()

# Example usage all together now

    import bkstring

    b = bkstring.bk_tree()
    b.add("foo")
    arr = list(["bar", "baz"])
    ls = b.search("bar", 1)

    for i in ls:
        print i # bar, baz

    b.close()