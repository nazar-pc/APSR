In most cases production server have \*nix-like OS, and even with Windows OS slash `/` as directory separator will work too, so, there is no real necessity
to use `DIRECTORY_SEPARATOR`.

Underscores are more likely part of class name that hierarchy separator, so, only namespace separator must be converted to directory separator.

As sequence - underscore is used for words separator. Words, `Class_name` is easier to read than `ClassName` or `className`, because words are really separated
from each other and underscore does not interfere to read words, as human eyes mostly use upper part of letters during reading.
