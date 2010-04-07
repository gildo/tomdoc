TomDoc 1.0.0
============

TomDoc is a flexible code documentation specification with human readers in
mind.


Method Documentation
--------------------

A quick example will serve to best illustrate the TomDoc method documentation
format:

    # Duplicate some text an abitrary number of times.
    #
    # text  - The String to be duplicated.
    # count - The Integer number of times to duplicate the text.
    #
    # Examples
    #   multiplex('Tom', 4)
    #   # => 'TomTomTomTom'
    #
    # Returns the duplicated String.
    def multiplex(text, count)
      text * count
    end

TomDoc for a specific method consists of a block of single comment markers (#)
that appears directly above the method. There must not be a blank line between
the comment block and the method definition. A TomDoc method block consists of
a description section (required), an arguments section (required if the method
takes any arguments), an examples section (optional), and a returns section
(required). Lines that contain text should be separated from the comment
marker by a single space. Lines that do not contain text should consist of
just a comment marker (no trailing spaces).

### The Description Section

The description section should be in plain sentences. Each sentence should end
with a period. Good descriptions explain what the code does at a high level.
Make sure to explain any unexpected behavior that the method may have, or any
pitfalls that the user may experience. Lines should be wrapped at 80
characters.

### The Arguments Section

The arguments section consists of a list of arguments. Each list item should
be comprised of the name of the argument, a dash, and an explanation of the
argument in plain sentences. The expected type (or types) of each argument
should be clearly indicated in the explanation. When you specify a type, use
the proper classname of the type (for instance, use 'String' instead of
'string' to refer to a String type). The dashes following each argument name
should be lined up in a single column. Lines should be wrapped at 80 columns.
If an explanation is longer than that, it should be wrapped and indented to
match the indentation of the explanation. For example:

    # element - The Symbol representation of the element. The Symbol should
    #           contain only lowercase ASCII alpha characters.


### The Examples Section

The examples section should start with the word "Examples" on a line by
itself. The following lines should be indented by two spaces (three spaces
from the initial comment marker) and contain code that shows off how to call
the method and (optional) examples of what it returns. Everything under the
"Examples" line should be considered code, so make sure you comment out lines
that show return values. Separate examples should be separated by a blank
line. For example:

    # Examples
    #   multiplex('x', 4)
    #   # => 'xxxx'
    #
    #   multiplex('apple', 2)
    #   # => 'appleapple'

### The Returns Section

The returns section should explain in plain sentences what is returned from
the method. The line should begin with "Returns". If only a single thing is
returned, state the nature and type of the value. For example:

    # Returns the duplicated String.

If several different types may be returned, list all of them. For example:

    # Returns the given element Symbol or nil if none was found.

If the return value of the method is not intended to be used, then you should
simply state:

    # Returns nothing.

If the method raises exceptions that the caller may be interested in, add
additional "Raises" lines that explain each exception and under what
conditions it may be encountered. For example:

    # Returns nothing.
    # Raises Errno::ENOENT if the file cannot be found.
    # Raises Errno::EACCES if the file cannot be accessed.

Lines should be wrapped at 80 columns. Wrapped lines should be indented under
the above line by two spaces. For example:

    # Returns the atomic mass of the element as a Float. The value is in
    #   unified atomic mass units.