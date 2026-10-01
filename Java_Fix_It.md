# Java Arrays Debugging Lab

## Goal

This week you will practice **reading, testing, and debugging Java programs that use arrays**.

Each program below contains one or more errors. Your job is to:

1. Read the code carefully.
2. Run the program.
3. Identify the problem(s).
4. Fix the code.
5. Run it again and confirm that it works as described.

The short practice problems are there to help you prepare for the final challenge.

---

## Part 1: Array Indexes

The program below should print all four anime shows.

```java
public class ArrayDebug1 {
    public static void main(String[] args) {

        String[] animeShows = {
            "Demon Slayer",
            "Black Clover",
            "Naruto",
            "One Piece"
        };

        System.out.println(animeShows[1]);
        System.out.println(animeShows[2]);
        System.out.println(animeShows[3]);
        System.out.println(animeShows[4]);
    }
}
```

### Expected Output

```text
Demon Slayer
Black Clover
Naruto
One Piece
```

Fix the program so it produces the expected output.

---

## Part 2: Array Length and Looping

The program below should print every show in the array exactly once.

```java
public class ArrayDebug2 {
    public static void main(String[] args) {

        String[] animeShows = {
            "Demon Slayer",
            "Black Clover",
            "Naruto",
            "One Piece"
        };

        for (int i = 0; i <= animeShows.length(); i++) {
            System.out.println(animeShows[i]);
        }
    }
}
```

### Expected Output

```text
Demon Slayer
Black Clover
Naruto
One Piece
```

Fix the program so the loop correctly processes the array.

---

## Part 3: Filling an Array

The program below should ask the user to enter three anime shows and then print all three shows.

```java
import java.util.Scanner;

public class ArrayDebug3 {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        String[] animeShows = new String[3];

        for (int i = 0; i < animeShows.length; i++) {
            System.out.print("Enter anime show " + (i + 1) + ": ");
            animeShows[i + 1] = input.nextLine();
        }

        System.out.println("\nAnime Shows:");

        for (String show : animeShows) {
            System.out.println(show);
        }

        input.close();
    }
}
```

### Example Run

```text
Enter anime show 1: Demon Slayer
Enter anime show 2: Black Clover
Enter anime show 3: Naruto

Anime Shows:
Demon Slayer
Black Clover
Naruto
```

Fix the program so all three values are stored correctly.

---

## Part 4: User-Selected Array Size

The program below should:

1. Ask the user how many anime shows they want to enter.
2. Create an array of that size.
3. Ask the user to enter each show.

```java
import java.util.Scanner;

public class ArrayDebug4 {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.print("How many anime shows do you want to enter? ");
        int size = input.nextInt();

        String[] animeShows = new String[size];

        for (int i = 0; i < animeShows.length; i++) {
            System.out.print("Enter anime show " + (i + 1) + ": ");
            animeShows[i] = input.nextLine();
        }

        System.out.println("\nAnime Shows:");

        for (String show : animeShows) {
            System.out.println(show);
        }

        input.close();
    }
}
```

### Example Run

```text
How many anime shows do you want to enter? 3
Enter anime show 1: Demon Slayer
Enter anime show 2: Black Clover
Enter anime show 3: Naruto

Anime Shows:
Demon Slayer
Black Clover
Naruto
```

Fix the program so the user can enter every show correctly.

---

## Part 5: Searching an Array

The program below should search the array for `Black Clover`.

If the show is found, the program should print the index where it was found.

If the show is not found, the program should print:

```text
Show not found.
```

```java
public class ArrayDebug5 {
    public static void main(String[] args) {

        String[] animeShows = {
            "Demon Slayer",
            "Black Clover",
            "Naruto",
            "One Piece"
        };

        String target = "Black Clover";
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
    }
}
```

### Expected Output

```text
Show found at index 1
```

Fix the program so the search works correctly.

---

# Final Debugging Challenge

The program below combines the same kinds of errors you worked on above.

The finished program should:

1. Ask how many anime shows the user wants to enter.
2. Create an array of that size.
3. Ask the user to enter each anime show.
4. Print all of the shows.
5. Ask the user for a show to search for.
6. Tell the user whether the show was found.
7. If the show was found, print its index.

The program contains **multiple errors**, including errors like the ones from the earlier practice problems.

```java
import java.util.Scanner;

public class AnimeArrayDebug {
    public static void main(String[] args) {

        Scanner input = new Scanner(System.in);

        System.out.print("How many anime shows do you want to enter? ");
        int size = input.nextInt();

        String[] animeShows = new String[size];

        for (int i = 1; i <= animeShows.length; i++) {
            System.out.print("Enter anime show " + i + ": ");
            animeShows[i] = input.nextLine();
        }

        System.out.println("\nAnime Shows:");

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

## Your Job

Find and correct every error so the program works properly.

### Example Run

```text
How many anime shows do you want to enter? 4
Enter anime show 1: Demon Slayer
Enter anime show 2: Black Clover
Enter anime show 3: Naruto
Enter anime show 4: One Piece

Anime Shows:
Demon Slayer
Black Clover
Naruto
One Piece

Enter a show to search for: Black Clover
Show found at index 1
```

---

## Submission

Submit **only** your corrected `AnimeArrayDebug.java` file to Blackboard.

Do **not** submit ZIP files, screenshots, Word documents, PDFs, or any other file type.

---

## Before You Submit

Make sure:

- Your program compiles.
- Your program runs without crashing.
- Every array index is valid.
- Your loops process every element exactly once.
- You use the correct way to compare `String` values.
- The program correctly handles a search that succeeds.
- The program correctly handles a search that fails.
- Your program output matches the required behavior.
