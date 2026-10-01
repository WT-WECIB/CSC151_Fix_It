# Java Arrays Debugging Lab

## Goal

This week you will debug **one Java program** that uses arrays.

The program contains several different errors. You will fix them **in stages**.

Do not skip ahead.

After each part, run the program and make sure that checkpoint works before moving to the next part.

You will submit **one corrected file** at the end:

```text
AnimeArrayDebug.java
```

---

# Starting Program

Create a Java file named:

```text
AnimeArrayDebug.java
```

Copy this code into the file exactly as shown.

```java
import java.util.Scanner;

public class AnimeArrayDebug {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        String[] sampleShows = {
            "Demon Slayer",
            "Black Clover",
            "Naruto",
            "One Piece"
        };

        System.out.println("Sample Anime Shows:");

        System.out.println(sampleShows[1]);
        System.out.println(sampleShows[2]);
        System.out.println(sampleShows[3]);
        System.out.println(sampleShows[4]);

        System.out.println();

        System.out.print("How many anime shows do you want to enter? ");
        int size = input.nextInt();

        String[] animeShows = new String[size];

        for (int i = 1; i <= animeShows.length; i++) {
            System.out.print("Enter anime show " + i + ": ");
            animeShows[i] = input.nextLine();
        }

        System.out.println("\nYour Anime Shows:");

        for (int i = 0; i < animeShows.length(); i++) {
            System.out.println(animeShows[i]);
        }

        System.out.print("\nEnter a show to search for: ");
        String target = input.nextLine();

        boolean isFound = false;

        for (int i = 0; i < animeShows.length; i++) {
            if (animeShows[i] == target) {
                System.out.println("Show found at index " + i);
                break;
            }
        }

        if (!isFound) {
            System.out.println("Show not found.");
        }

        input.close();
    }
}
```

---

# Part 1: Fix the Array Indexes

The first section of the program is supposed to print all four sample shows:

```text
Demon Slayer
Black Clover
Naruto
One Piece
```

Right now, the program uses the wrong array indexes.

## Your Task

Fix the four `System.out.println()` statements so they correctly print every element in `sampleShows`.

Remember:

- Array indexes begin at `0`.
- An array with 4 elements has valid indexes `0` through `3`.

## Checkpoint 1

Do not move on until this section prints:

```text
Sample Anime Shows:
Demon Slayer
Black Clover
Naruto
One Piece
```

---

# Part 2: Fix the Input Loop

The next section should ask the user how many anime shows they want to enter and then allow them to enter that many shows.

This loop currently contains multiple problems:

```java
for (int i = 1; i <= animeShows.length; i++) {
    System.out.print("Enter anime show " + i + ": ");
    animeShows[i] = input.nextLine();
}
```

## Your Task

Fix the loop so that:

- It begins at the correct array index.
- It does not go past the end of the array.
- Each show is stored in the correct array position.
- The prompt still displays `1`, `2`, `3`, and so on to the user.

## Checkpoint 2

If the user enters:

```text
3
```

the program should allow them to enter exactly three shows without crashing.

Example:

```text
How many anime shows do you want to enter? 3
Enter anime show 1: Demon Slayer
Enter anime show 2: Black Clover
Enter anime show 3: Naruto
```

If the first show is skipped, do **not** move on yet. That problem will be fixed in Part 3.

---

# Part 3: Fix the Scanner Input Problem

The program uses:

```java
int size = input.nextInt();
```

and then later uses:

```java
input.nextLine();
```

When `nextInt()` is followed by `nextLine()`, the first String input may be skipped.

## Your Task

Add the line needed to clear the leftover newline before the program begins reading anime titles.

## Checkpoint 3

Run the program again.

If the user enters:

```text
3
```

they should be able to type all three anime shows normally.

Example:

```text
How many anime shows do you want to enter? 3
Enter anime show 1: Demon Slayer
Enter anime show 2: Black Clover
Enter anime show 3: Naruto
```

---

# Part 4: Fix the Loop That Prints the Array

The program should print every anime show the user entered.

This loop contains an error:

```java
for (int i = 0; i < animeShows.length(); i++) {
    System.out.println(animeShows[i]);
}
```

## Your Task

Fix the array-length expression so the loop compiles and prints every element.

## Checkpoint 4

If the user entered:

```text
Demon Slayer
Black Clover
Naruto
```

the program should print:

```text
Your Anime Shows:
Demon Slayer
Black Clover
Naruto
```

---

# Part 5: Fix the Search

The final section asks the user for an anime show and searches the array.

The search currently contains **two problems**.

```java
for (int i = 0; i < animeShows.length; i++) {
    if (animeShows[i] == target) {
        System.out.println("Show found at index " + i);
        break;
    }
}
```

## Your Task

Fix the search so that:

- String values are compared correctly.
- `isFound` becomes `true` when a match is found.

## Checkpoint 5A: Search That Succeeds

If the array contains:

```text
Demon Slayer
Black Clover
Naruto
```

and the user searches for:

```text
Black Clover
```

the program should print:

```text
Show found at index 1
```

It should **not** also print:

```text
Show not found.
```

## Checkpoint 5B: Search That Fails

Run the program again and search for a show that is not in the array.

Example:

```text
One Piece
```

If it was not entered earlier, the program should print:

```text
Show not found.
```

---

# Final Test

Before submitting, run the complete program from beginning to end.

Test both of these cases:

## Test 1: Show Found

Example:

```text
Sample Anime Shows:
Demon Slayer
Black Clover
Naruto
One Piece

How many anime shows do you want to enter? 3
Enter anime show 1: Demon Slayer
Enter anime show 2: Black Clover
Enter anime show 3: Naruto

Your Anime Shows:
Demon Slayer
Black Clover
Naruto

Enter a show to search for: Black Clover
Show found at index 1
```

## Test 2: Show Not Found

Run the program again and search for a show that was not entered.

The program should print:

```text
Show not found.
```

---

# Submission

Submit **only** your corrected:

```text
AnimeArrayDebug.java
```

file to Blackboard.

Do **not** submit ZIP files, screenshots, Word documents, PDFs, or any other file type.

---

# Before You Submit

Make sure:

- Your program compiles.
- Your program runs without crashing.
- The sample array prints all four shows correctly.
- Your input loop uses valid array indexes.
- The user can enter every show without the first input being skipped.
- The program prints every value in the array.
- String values are compared correctly.
- A successful search prints the correct index.
- A failed search prints `Show not found.`
