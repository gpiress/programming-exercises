# Loops

## Review
Loop statements are a way to repeat a set of instructions in your program.
Every time you find a pattern that you are repeating multiple times, you should
think if it isn't more appropriate to use a Loop statement.

As a reminder, the loop statements are: `for`, `while` and `do-while`.

### `for`
This is most suited when you know the boundaries of your loop.
If you want to repeat some instructions exactly 10 times, for example:

```
int sum = 0;
for (int i = 0; i < 10; i++) {
  sum = sum + i;
}
printf("The sum of all integers from 0 to 9 is: %d", sum);
```

The `for` structure is
`for ([initial state]; [condition to run]; [increment step]) { [statements] }`.

### `while`
When you don't know the boundaries exactly, but you have one goal
on mind. For example, if you want to repeat something until a certain variable
is greater than 0:

```
int a = 20;
while (a > 0) {
  a = a / 2;
}
```

The `while` structure is `while([condition to run]) { [statements] }`.

### `do-while`
When you want to repeat something, but make sure it always one at least one time
in the beginning. This is the least used, but helpful when you want to get valid
user input. If you want to make sure the user gives you a number greater than 0:

```
int positiveNumber;
do {
  positiveNumber = get_int();
} while (positiveNumber < 0);
```

The `do-while` structure is `do { [statements] } while([condition to run]);`

## Exercises

Feel free to use any loop you like for these exercises, but try to think about
which to use and why.

I tried to sort the list is sorted by difficulty. So the first ones will be
easier, and the last ones will be closer to the problems you get in your labs.

1. Print all the integers between 0 and 10.
1. Print the sum of all integers between 1 and 10.
1. Print the product of all integers between 1 and 10.
1. Print all odd integers between 0 and 30.
1. Print all even integers between 0 and 30.
1. Print the sum of all even integers between 0 and 30.
1. Print a rectangle of asterisks (\*), of height 3 and width 6. The output of
your program should be (without the dots):
```
******.
******.
******.
```
1. Print a rectangle of asterisks again, but this time, ask the user for both
  the height and width.
1. Ask user for input until they type a positive integer.
1. Ask user for input until they type a negative integer.
1. Ask user for integer and print all its
  [numerical digits](https://en.wikipedia.org/wiki/Numerical_digit)
  (e.g: for input `32986`, your program should print `3`, `2`, `9`, `8`, `6`,
  in whichever order).
1. Ask user for integer and print the largest
  [numerical digit](https://en.wikipedia.org/wiki/Numerical_digit)
  (e.g: for input `3945`, your program should print `9`).
1. Ask user for integer and print the sum of all its
  [numerical digits](https://en.wikipedia.org/wiki/Numerical_digit)
  (e.g: for input `12345`, you should print `15`: `1 + 2 + 3 + 4 + 5`).
1. Ask user for integer and print every other
  [numerical digit](https://en.wikipedia.org/wiki/Numerical_digit)
  (e.g: for input `12345`, you should print `1`, `3` and `5`, in whichever
  order).
1. Ask user for integer and check if the sum of its digits is a multiple of 10
  (e.g: for input `32564`, your program should print `true`, because
  `3 + 2 + 5 + 6 + 4` is `20`, and `20 % 10` is `0`). Print `false` if the user
  input isn't a multiple of `10`.
