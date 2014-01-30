# Ramsey: the suburban commando for text files

Ramsey is a command-line tool for applying mustache templates to text files.

# Examples

## Using a file for variables

    $ cat file1.in
    I can call you {{name1}}
    And {{name1}} when you call me
    You can call me {{name2}}

    $ cat file1.json
    {
        "name1": "Betty",
        "name2": "Al"
    }

    $ ramsey -f file1.json file1.in file1.out

    $ cat file1.out
    I can call you Betty
    And Betty when you call me
    You can call me Al


## Using a directory for variables

    $ ls dir1
    line1 line2

    $ cat dir1/line1
    I'm going to Graceland

    $ cat dir1/line2
    And we are going to Graceland

    $ cat dir1.in
    {{line1}}
    Memphis, Tennessee
    {{line1}}
    Poor boys and pilgrims with families
    {{line2}}

    $ ramsey -d dir1 dir1.in dir1.out

    $ cat dir1.out
    I'm going to Graceland
    Memphis, Tennessee
    I'm going to Graceland
    Poor boys and pilgrims with families
    And we are going to Graceland


# Current Status

**This is still a dirty hack. Use at your own risk!**

