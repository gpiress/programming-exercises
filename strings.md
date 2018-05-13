# Strings

Go straight to the [exercises](#exercises).

## Review

Strings are lists (arrays) of characters (`char` type in C)
in a given order. Strings can be user for *words*, *phrases* or
even *large numbers*.

### Declaring strings

You can declare a variable `a` of type string with value "abc"
and print it in the console by doing the following:

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string a = "abc";

    printf("%s\n", a);

    return 0;
}
```

### String inputs

You can ask your user for a string input by using the
`get_string` function. An example would be:

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string input;

    input = get_string("One string please: ");

    printf("%s\n", input);

    return 0;
}
```

### Size of a string

How do you figure out how long your string is? That is, how many
characters there are in a certain string? You can use the
function `strlen(string argument)` for that:

```c
#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    string a = "abc";

    int a_length = strlen(a);

    printf("The length of '%s' is: %i\n", a, a_length);

    return 0;
}
```

The output of the program above is: `The length of 'abc' is: 3`.

Note that we had to include the library `string.h` to be able
to use the `strlen` function.

### Looping through your string

Sometimes you want to loop through every letter on your string,
be it to make sure there are only alphabetical characters in it
(no numbers!) or because you want to make sure every word starts
with a capital letter or for whatever other reason.

From the previous set of exercises, you know that every time you
need to loop through something, you need a loop statement, like
a `for`. But what are the boundaries for your string?

Let's say you want want to print every character in a certain
string. You could do that by doing:

```c
#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    string a = "abc";

    int a_length = strlen(a);

    for (int i = 0; i < a_length; i++)
    {
        printf("%c\n", a[i]);
    }

    return 0;
}
```

The output is:

```
a
b
c
```

`a[i]` means we are looking at the i-th character of the string
a. Since `i` changes its value on every loop, this will access
all characters in string `a`.

### Shifting characters

If for some reason you want to shift the characters on your
string, you can do it by adding some `int` value to it.

Let's say we want to shift all characters in a string by 1.
That is, we want a string "abc" to become "bcd":

```c
#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    string a = get_string("A string, please: ");

    int a_length = strlen(a);
    for (int i = 0; i < a_length; i++)
    {
        a[i] = a[i] + 1;
    }

    printf("%s\n", a);
    return 0;
}
```


## Exercises

1. Ask the user for a string, and then print the length of that string.
1. Ask the user for a string, and then print the first character of that string.
1. Ask the user for a string, and then print the last character of that string.
1. Ask the user for a string, and then print that string in reverse order (input "abc", output "cba").
1. Ask the user for a string, and if that string contains the letter 'z', print `true`. Otherwise, print `false`.
1. Ask the user for a string, if that string length is greater than 7, print `Big word`. Otherwise, print `Small word`.
1. Ask the user for a string, if that string contains any non-alphabetical character, print `bad string`. Otherwise, print `good string`.

Harder:

1. Ask the user for a string. Your program should shift every alphabetical character in that string by 1, that is, change it to the next letter in the alphabet. `'z'` should become `'a'`. (input `abz`, output `bca`).
1. Ask the user for a string. Your program should shift every alphabetical character in that string by -1, that is, change it to the previous letter in the alphabet. `'a'` should become `'z'`. (input `abc`, output `zab`).
1. Ask the user for a string. Your program should flip the case
of every alphabetical character on the string. (input `Sven Svensson`, output `sVEN sVENSSON`).

## Problems

**Problem 1 - Help Sofia!**

Sofia's best friend is called Ana, and she really loves her name because it doesn't matter if you read it forwards or backwards, it's always the same -- `Ana`.

Words like that are called *palindromes*. Some
examples of palindromes in English are: `madam`, `civic`,
`level` and `Ana`. Can you help Sofia figure out if a word is
a palindrome or not?

You should write a program that asks the user for a string and,
if that word is a palindrome, print `Palindrome found!`. If the
word is not a palindrome, your program should print
`not palindrome :(`.

Tip: In the case of `Ana`'s name, you might be wondering if 'A'
is equal to 'a'. For this problem, the letter case doesn't
matter!

*Input*
```
madam
banana
Ana
Civic
```

*Output*
```
Palindrome found!
not palindrome :(
Palindrome found!
Palindrome found!
```

**Problem 2 - Movie Titles**

Sven is a Hollywood movie producer. And everyone knows that in
order for a movie to be successful, its title should be written
in "Title Case". That is, every word of the title should start
with an uppercase letter, and all other letters of the word
should be lowercase.

Unfortunately, not all directors and writers know that trick,
making Sven's life harder when submitting the titles of their
new movies for approval. Help Sven automate this process!

Write a program that, for a given movie title (string), convert
it to "Title Case".

*Input*
```
star wars: a new hope
THE lORD oF the rIngs: the fellowship of THE ring
harry POTTER
007
```

*Output*
```
Star Wards: A New Hope
The Lord of the Rings: The Fellowship of the Ring
Harry Potter
007
```
