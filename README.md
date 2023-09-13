# ![java](java-logo.png) Java solutions for [Codewars](https://www.codewars.com/) katas

## Challenges

| Kyu | Title                                                                         |
|:---:|:------------------------------------------------------------------------------|
|  6  | [Stop gninnipS My sdroW!](#stop-gninnips-my-sdrow)                            |
|  7  | [Reverse words](#reverse-words)                                               |
|  7  | [String ends with?](#string-ends-with)                                        |
|  6  | [Find the odd int](#find-the-odd-int)                                         |
|  6  | [Build a pile of Cubes](#build-a-pile-of-cubes)                               |
|  7  | [Growth of a Population](#growth-of-a-population)                             |
|  7  | [Odd or Even?](#odd-or-even)                                                  |
|  5  | [RGB To Hex Conversion](#rgb-to-hex-conversion)                               |
|  6  | [Convert string to camel case](#convert-string-to-camel-case)                 |
|  6  | [Array diff](#array-diff)                                                     |
|  6  | [Create Phone Number](#create-phone-number)                                   |
|  5  | [Product of consecutive Fib numbers](#product-of-consecutive-fib-numbers)     |
|  4  | [Snail Sort](#snail-sort)                                                     |
|  5  | [Tic-Tac-Toe Checker](#tic-tac-toe-checker)                                   |
|  6  | [Decode the Morse code](#decode-the-morse-code)                               |
|  4  | [Decode the Morse code, advanced](#decode-the-morse-code-advanced)            |
|  4  | [Sum by Factors](#sum-by-factors)                                             |
|  4  | [Most frequently used words in a text](#most-frequently-used-words-in-a-text) |

  
---

## Stop gninnipS My sdroW!

Write a function that takes in a string of one or more words, and returns the same string, but with all five or more letter words reversed (Just like the name of this Kata). Strings passed in will consist of only letters and spaces. Spaces will be included only when more than one word is present.

Examples:

```
spinWords( "Hey fellow warriors" ) => returns "Hey wollef sroirraw" 
spinWords( "This is a test") => returns "This is a test" 
spinWords( "This is another test" )=> returns "This is rehtona test"
```

```java
public class SpinWords {
    public String spinWords(String sentence) {
        //TODO: Code stuff here
    }
}
```

<details><summary>Solution</summary>

```java
public class SpinWords {
    public String spinWords(String sentence) {
        String[] arr = sentence.split(" ");
        StringBuilder result = new StringBuilder();
        for(int i=0; i < arr.length; i++) {
            if(arr[i].length() >= 5) {
                result.append(new StringBuilder(arr[i]).reverse() + " ");
            } else {
                result.append(arr[i] + " ");
            }
        }
        return result.toString().trim();
    }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Reverse words

Complete the function that accepts a string parameter, and reverses each word in the string. All spaces in the string should be retained.

Examples:

```
"This is an example!" ==> "sihT si na !elpmaxe"
"double  spaces"      ==> "elbuod  secaps"
```

```java
public class Kata
{
    public static String reverseWords(final String original)
    {
        // Have at it
    }
}
```

<details><summary>Solution</summary>

```java
import java.util.Arrays;
import java.util.stream.Collectors;

public class Kata
{
    public static String reverseWords(final String original)
    {
        if(original.isBlank()) {
            return original;
        }
        return Arrays.stream(original.split(" "))
                .map(word -> word.length() > 1
                        ? new StringBuilder(word).reverse()
                        : word)
                .collect(Collectors.joining(" "));
    }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## String ends with?

Complete the solution so that it returns true if the first argument(string) passed in ends with the 2nd argument (also a string).

Examples:

```
solution('abc', 'bc') // returns true
solution('abc', 'd') // returns false
```

```java
public class Kata {
  public static boolean solution(String str, String ending) {
    return false;
  }
}
```

<details><summary>Solution</summary>

```java
public class Kata {
  public static boolean solution(String str, String ending) {
    return str.endsWith(ending);
  }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Find the odd int

Given an array of integers, find the one that appears an odd number of times.
There will always be only one integer that appears an odd number of times.

Examples:

```
[7] should return 7, because it occurs 1 time (which is odd).
[0] should return 0, because it occurs 1 time (which is odd).
[1,1,2] should return 2, because it occurs 1 time (which is odd).
[0,1,0,1,0] should return 0, because it occurs 3 times (which is odd).
[1,2,2,3,3,3,4,3,3,3,2,2,1] should return 4, because it appears 1 time (which is odd).
```

```java
public class FindOdd {
	public static int findIt(int[] a) {
  	return odd;
  }
}
```

<details><summary>Solution</summary>

```java
import java.util.Map.Entry;
import java.util.HashMap;

public class FindOdd {
	public static int findIt(int[] a) {
    HashMap<Integer, Integer> numberCounter = new HashMap<>();
    for (int number : a) {
      Integer value = numberCounter.get(number);
      numberCounter.put(number, value == null ? 1 : ++value);
    }
    int desiredNumber = 0;
    for (Entry<Integer, Integer> entry : numberCounter.entrySet()) {
      if(entry.getValue() % 2 == 1) {
        desiredNumber = entry.getKey();
        break;
      }
    }
  	return desiredNumber;
//    return Arrays.stream(a).reduce(0, (a1, a2) -> a1 ^ a2);
  }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Build a pile of Cubes

Your task is to construct a building which will be a pile of n cubes. The cube at the bottom will have a volume of $n^3$, the cube above will have volume of $(n - 1)^3$ and so on until the top which will have a volume of $1^3$.

You are given the total volume m of the building. Being given m can you find the number n of cubes you will have to build?

The parameter of the function findNb (find_nb, find-nb, findNb, ...) will be an integer m and you have to return the integer n such as
$n^3 + (n - 1)^3 + (n − 2)^3 + ... + 1^3 = m$ if such a n exists or -1 if there is no such n.

Examples:

```
findNb(1071225) --> 45

findNb(91716553919377) --> -1
```

```java
public class ASum {
	public static long findNb(long m) {
		// your code
	}	
}
```

<details><summary>Solution</summary>

```java
public class ASum {

    public static long findNb(long m) {
        long n = 1L;
        long sum = 1L;
        while(sum < m) {
            sum += (long) Math.pow(++n, 3);
        }
        return sum == m ? n : -1;
    }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Growth of a Population

In a small town the population is p0 = 1000 at the beginning of a year. The population regularly increases by 2 percent per year and moreover 50 new inhabitants per year come to live in the town. How many years does the town need to see its population greater or equal to p = 1200 inhabitants?
```
At the end of the first year there will be: 
1000 + 1000 * 0.02 + 50 => 1070 inhabitants

At the end of the 2nd year there will be: 
1070 + 1070 * 0.02 + 50 => 1141 inhabitants (** number of inhabitants is an integer **)

At the end of the 3rd year there will be:
1141 + 1141 * 0.02 + 50 => 1213

It will need 3 entire years.
```
More generally given parameters:

p0, percent, aug (inhabitants coming or leaving each year), p (population to equal or surpass)

the function nb_year should return n number of entire years needed to get a population greater or equal to p.

aug is an integer, percent a positive or null floating number, p0 and p are positive integers (> 0)

Note:
Don't forget to convert the percent parameter as a percentage in the body of your function: if the parameter percent is 2 you have to convert it to 0.02.

Examples:

```
nb_year(1500, 5, 100, 5000) -> 15
nb_year(1500000, 2.5, 10000, 2000000) -> 10
```

```java
class Arge {
    public static int nbYear(int p0, double percent, int aug, int p) {
        // your code
    }
}
```

<details><summary>Solution</summary>

```java
class Arge {
    
    public static int nbYear(int p0, double percent, int aug, int p) {
      int years = 0;
      while (p0 < p) {
        years++;
        p0 += p0 * percent / 100 + aug;
      }
      return years;
    }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Odd or Even?

Given a list of integers, determine whether the sum of its elements is odd or even.

Give your answer as a string matching "odd" or "even".

If the input array is empty consider it as: [0] (array with a zero).

Examples:

```
Input: [0]
Output: "even"

Input: [0, 1, 4]
Output: "odd"

Input: [0, -1, -5]
Output: "even"
```

```java
public class Codewars {
  public static String oddOrEven (int[] array) {
  // your code
  }
}
```

<details><summary>Solution</summary>

```java
import java.util.Arrays;

public class Codewars {
  public static String oddOrEven (int[] array) {
    int sum = Arrays.stream(array).sum();
    return sum % 2 == 0 ? "even" : "odd";
  }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## RGB To Hex Conversion

The rgb function is incomplete. Complete it so that passing in RGB decimal values will result in a hexadecimal representation being returned. Valid decimal values for RGB are 0 - 255. Any values that fall out of that range must be rounded to the closest valid value.

Note: Your answer should always be 6 characters long, the shorthand with 3 will not work here.

Examples:

```
RgbToHex.rgb(255, 255, 255) // returns FFFFFF
RgbToHex.rgb(255, 255, 300) // returns FFFFFF
RgbToHex.rgb(0, 0, 0)       // returns 000000
RgbToHex.rgb(148, 0, 211)   // returns 9400D3
```

```java
public class RgbToHex {
    public static String rgb(int r, int g, int b) {
        return null;
    }
}
```

<details><summary>Solution</summary>

```java
public class RgbToHex {

    public static String rgb(int r, int g, int b) {
//      int result = (validate(r) << 16) + (validate(g) << 8) + validate(b);
//      return String.format("%06X", result);
      return String.format("%02X%02X%02X", validate(r), validate(g), validate(b));
    }
  
    private static int validate(int x) {
      if(x < 0) return 0;
      else if(x > 255) return 255;
      return x;
    }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Convert string to camel case

Complete the method/function so that it converts dash/underscore delimited words into camel casing. The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case). The next words should be always capitalized.

Examples:

```
"the-stealth-warrior" gets converted to "theStealthWarrior"

"The_Stealth_Warrior" gets converted to "TheStealthWarrior"

"The_Stealth-Warrior" gets converted to "TheStealthWarrior"
```

```java
import java.lang.StringBuilder;
class Solution{
  static String toCamelCase(String s){
    return "";
  }
}
```

<details><summary>Solution</summary>

```java
class Solution{

    static String toCamelCase(String s){
        String[] words = s.split("[-_]");
        StringBuilder result = new StringBuilder(words[0]);
        for(int i = 1; i < words.length; i++) {
            result.append(words[i].substring(0, 1).toUpperCase());
            result.append(words[i].substring(1));
        }
        return result.toString();
    }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Array diff

Your goal in this kata is to implement a difference function, which subtracts one list from another and returns the result.

It should remove all values from list a, which are present in list b keeping their order.

```
Kata.arrayDiff(new int[] {1, 2}, new int[] {1}) => new int[] {2}
```
If a value is present in b, all of its occurrences must be removed from the other:
```
Kata.arrayDiff(new int[] {1, 2, 2, 2, 3}, new int[] {2}) => new int[] {1, 3}
```


```java
public class Kata {

  public static int[] arrayDiff(int[] a, int[] b) {
    // Your code here
    return a;
  }
}
```

<details><summary>Solution</summary>

```java
import java.util.List;
import java.util.Arrays;
import java.util.stream.Collectors;

public class Kata {

    public static int[] arrayDiff(int[] a, int[] b) {
        if (a.length == 0 || b.length == 0) return a;
        List<Integer> listA = Arrays.stream(a).boxed().collect(Collectors.toList());
        List<Integer> listB = Arrays.stream(b).boxed().toList();
        return listA.removeAll(listB)
                ? listA.stream().mapToInt(Integer::intValue).toArray()
                : a;
    }

}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Create Phone Number

Write a function that accepts an array of 10 integers (between 0 and 9), that returns a string of those numbers in the form of a phone number.  
The returned format must be correct in order to complete this challenge.  
Don't forget the space after the closing parentheses!

Examples:

```
Kata.createPhoneNumber(new int[] {1, 2, 3, 4, 5, 6, 7, 8, 9, 0}) // => returns "(123) 456-7890"
```

```java
public class Kata {
  public static String createPhoneNumber(int[] numbers) {
    // Your code here!
  }
}
```

<details><summary>Solution</summary>

```java
public class Kata {
  public static String createPhoneNumber(int[] numbers) {
    StringBuilder phoneNumber = new StringBuilder(14);
    phoneNumber.append("(");
    for(int i = 0; i < 10; i++) {
      phoneNumber.append(numbers[i]);
      if (i == 2) phoneNumber.append(") ");
      if (i == 5) phoneNumber.append("-");
    }
    return phoneNumber.toString();
  }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Product of consecutive Fib numbers

The Fibonacci numbers are the numbers in the following integer sequence (Fn):

> 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, ...

such as

> F(n) = F(n-1) + F(n-2) with F(0) = 0 and F(1) = 1.

Given a number, say prod (for product), we search two Fibonacci numbers F(n) and F(n+1) verifying

> F(n) * F(n+1) = prod.

Your function productFib takes an integer (prod) and returns an array: `{F(n), F(n+1), 1}` if `F(n) * F(n+1) = prod`.

If you don't find two consecutive F(n) verifying` F(n) * F(n+1) = prod` you will return `{F(n), F(n+1), 0}`  
F(n) being the smallest one such as `F(n) * F(n+1) > prod`.

Examples:

```
productFib(714) # should return {21, 34, 1}
productFib(800) # should return {34, 55, 0}
```

```java
public class ProdFib { // must be public for codewars	

    public static long[] productFib(long prod) {
        // your code
        return null;
    }
}
```

<details><summary>Solution</summary>

```java
public class ProdFib {

    public static long[] productFib(long prod) {
        long n1 = 0;
        long n2 = 1;
        long temp = 0;
        while(temp <= prod) {
            if (temp == prod) return new long[]{n1, n2, 1};
            temp = n1 + n2;
            n1 = n2;
            n2 = temp;
            temp = n1 * n2;
        }
        return new long[]{n1, n2, 0};
    }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Snail Sort

Given an n x n array, return the array elements arranged from outermost elements to the middle element, traveling clockwise.  

NOTE: The idea is not sort the elements from the lowest value to the highest; the idea is to traverse the 2-d array in a clockwise snailshell pattern.  
NOTE 2: The 0x0 (empty matrix) is represented as en empty array inside an array [[]].

Examples:

```
array = [[1,2,3],
         [4,5,6],
         [7,8,9]]
snail(array) #=> [1,2,3,6,9,8,7,4,5]
```

```java
public class Snail {

    public static int[] snail(int[][] array) {
     // enjoy
   } 
}
```

<details><summary>Solution</summary>

```java
public class Snail {

    public static int[] snail(int[][] array) {
        if (array.length == 0 || array[0].length == 0) return new int[0];
        int[] snail = new int[array.length * array.length];
        int x = -1, y = 0;
        byte delta = 1;
        int index = 0;
        int count = array.length;

        while (index < snail.length) {
            for (int i = 0; i < count; i++) {
                x += delta;
                snail[index++] = array[y][x];
            }
            count--;
            for (int i = 0; i < count; i++) {
                y += delta;
                snail[index++] = array[y][x];
            }
            delta = (byte) -delta;
        }

        return snail;
    }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Tic-Tac-Toe Checker

If we were to set up a Tic-Tac-Toe game, we would want to know whether the board's current state is solved, wouldn't we? Our goal is to create a function that will check that for us!

Assume that the board comes in the form of a 3x3 array, where the value is 0 if a spot is empty, 1 if it is an "X", or 2 if it is an "O", like so:

```
[[0, 0, 1],
 [0, 1, 2],
 [2, 1, 0]]
```
We want our function to return:

- -1 if the board is not yet finished AND no one has won yet (there are empty spots),
- 1 if "X" won,
- 2 if "O" won,
- 0 if it's a cat's game (i.e. a draw).

You may assume that the board passed in is valid in the context of a game of Tic-Tac-Toe.

```java
public class Solution {
    public static int isSolved(int[][] board) {
        // your code here
        return 0;
    }
}
```

<details><summary>Solution</summary>

```java
import java.util.List;
import java.util.ArrayList;

public class Solution {

    public static int isSolved(int[][] board) {
      boolean draw = true;
      List<List<Integer>> lines = new ArrayList<>(8);

      for (int i = 0; i < 3; i++) {
        List<Integer> row = new ArrayList<>(3);
        List<Integer> column = new ArrayList<>(3);
        for (int j = 0; j < 3; j++) {
          row.add(board[i][j]);
          column.add(board[j][i]);
        }
        lines.add(row);
        lines.add(column);
      }

      List<Integer> diagonal_1 = new ArrayList<>(3);
      List<Integer> diagonal_2 = new ArrayList<>(3);
      for (int i = 0; i < 3; i++) {
        diagonal_1.add(board[i][i]);
        diagonal_2.add(board[2 - i][i]);
      }
      lines.add(diagonal_1);
      lines.add(diagonal_2);

      for (List<Integer> line : lines) {
        if (line.stream().allMatch(e -> e == 1)) return 1;
        if (line.stream().allMatch(e -> e == 2)) return 2;
        if (line.contains(0)) draw = false;
      }

      return draw ? 0 : -1;
    }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Decode the Morse code

In this kata you have to write a simple Morse code decoder. While the Morse code is now mostly superseded by voice and digital data communication channels, it still has its use in some applications around the world.
The Morse code encodes every character as a sequence of "dots" and "dashes". For example, the letter A is coded as ·−, letter Q is coded as −−·−, and digit 1 is coded as ·−−−−. The Morse code is case-insensitive, traditionally capital letters are used. When the message is written in Morse code, a single space is used to separate the character codes and 3 spaces are used to separate words. For example, the message HEY JUDE in Morse code is ···· · −·−−   ·−−− ··− −·· ·.

NOTE: Extra spaces before or after the code have no meaning and should be ignored.

In addition to letters, digits and some punctuation, there are some special service codes, the most notorious of those is the international distress signal SOS (that was first issued by Titanic), that is coded as ···−−−···. These special codes are treated as single special characters, and usually are transmitted as separate words.

Your task is to implement a function that would take the morse code as input and return a decoded human-readable string.

NOTE: For coding purposes you have to use ASCII characters . and -, not Unicode characters.

The Morse code table is preloaded for you as a dictionary, feel free to use it: MorseCode.get(".--")

All the test strings would contain valid Morse code, so you may skip checking for errors and exceptions.

Examples:

```
MorseCodeDecoder.decode(".... . -.--   .--- ..- -.. .")
//should return "HEY JUDE"
```

```java
public class MorseCodeDecoder {
    public static String decode(String morseCode) {
        // your brilliant code here, remember that you can access the preloaded Morse code table through MorseCode.get(code)
    }
}
```

<details><summary>Solution</summary>

```java
public class MorseCodeDecoder {
    public static String decode(String morseCode) {
      StringBuilder message = new StringBuilder();
      String[] morseWords = morseCode.trim().split("\\s{3}");
      for (String morseWord : morseWords) {
        String[] morseCharacters = morseWord.split(" ");
        for (String morseCharacter : morseCharacters) {
          message.append(MorseCode.get(morseCharacter));
        }
        message.append(' ');
      }
      return message.toString().trim();
    }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Decode the Morse code, advanced

In this kata you have to write a Morse code decoder for wired electrical telegraph.
Electric telegraph is operated on a 2-wire line with a key that, when pressed, connects the wires together, which can be detected on a remote station. The Morse code encodes every character being transmitted as a sequence of "dots" (short presses on the key) and "dashes" (long presses on the key).

When transmitting the Morse code, the international standard specifies that:

"Dot" – is 1 time unit long.
"Dash" – is 3 time units long.
Pause between dots and dashes in a character – is 1 time unit long.
Pause between characters inside a word – is 3 time units long.
Pause between words – is 7 time units long.
However, the standard does not specify how long that "time unit" is. And in fact different operators would transmit at different speed. An amateur person may need a few seconds to transmit a single character, a skilled professional can transmit 60 words per minute, and robotic transmitters may go way faster.

For this kata we assume the message receiving is performed automatically by the hardware that checks the line periodically, and if the line is connected (the key at the remote station is down), 1 is recorded, and if the line is not connected (remote key is up), 0 is recorded. After the message is fully received, it gets to you for decoding as a string containing only symbols 0 and 1.

For example, the message HEY JUDE, that is ···· · −·−−   ·−−− ··− −·· · may be received as follows:

1100110011001100000011000000111111001100111111001111110000000000000011001111110011111100111111000000110011001111110000001111110011001100000011

As you may see, this transmission is perfectly accurate according to the standard, and the hardware sampled the line exactly two times per "dot".

That said, your task is to implement two functions:

1. Function decodeBits(bits), that should find out the transmission rate of the message, correctly decode the message to dots ., dashes - and spaces (one between characters, three between words) and return those as a string. Note that some extra 0's may naturally occur at the beginning and the end of a message, make sure to ignore them. Also if you have trouble discerning if the particular sequence of 1's is a dot or a dash, assume it's a dot.
2. Function decodeMorse(morseCode), that would take the output of the previous function and return a human-readable string.

NOTE: For coding purposes you have to use ASCII characters . and -, not Unicode characters.

The Morse code table is preloaded for you (see the solution setup, to get its identifier in your language).

All the test strings would be valid to the point that they could be reliably decoded as described above, so you may skip checking for errors and exceptions, just do your best in figuring out what the message is!

Good luck!

```java
public class MorseCodeDecoder {
    public static String decodeBits(String bits) {
      return ".";
    }
    
    public static String decodeMorse(String morseCode) {
      return MorseCode.get(morseCode);
    }
}
```

<details><summary>Solution</summary>

```java
import java.util.Arrays;

public class MorseCodeDecoder {
    public static String decodeBits(String bits) {
        bits = bits.substring(bits.indexOf("1"), bits.lastIndexOf("1") + 1);
        String bitsDelimited = bits.replaceAll("10", "1:0").replaceAll("01", "0:1");
        int n = Arrays.stream(bitsDelimited.split(":")).distinct().mapToInt(String::length).min().orElse(0);
        if (n > 0) {
            String[] words = bits.split("0{" + n * 7 + "}");
            for (int i = 0; i < words.length; i++) {
                words[i] = words[i]
                        .replaceAll("0{" + n * 3 + "}", " ")
                        .replaceAll("1{" + n * 3 + "}", "-")
                        .replaceAll("1{" + n + "}", ".")
                        .replaceAll("0{" + n + "}", "");
            }
            return String.join("   ", words);
        }
        return "";
    }
    
    public static String decodeMorse(String morseCode) {
        StringBuilder message = new StringBuilder();
        String[] morseWords = morseCode.trim().split("\\s{3}");
        for (String morseWord : morseWords) {
            String[] morseCharacters = morseWord.split(" ");
            for (String morseCharacter : morseCharacters) {
                message.append(MorseCode.get(morseCharacter));
            }
            message.append(' ');
        }
        return message.toString().trim();
    }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Sum by Factors

Given an array of positive or negative integers

I= [i1,..,in]

you have to produce a sorted array P of the form

[ [p, sum of all ij of I for which p is a prime factor (p positive) of ij] ...]

P will be sorted by increasing order of the prime numbers. The final result has to be given as a string in Java, C#, C, C++ and as an array of arrays in other languages.

Example:

```
I = {12, 15}; // result = "(2 12)(3 27)(5 15)"
```

[2, 3, 5] is the list of all prime factors of the elements of I, hence the result.

Notes:
- It can happen that a sum is 0 if some numbers are negative!  
Example: I = [15, 30, -45] 5 divides 15, 30 and (-45) so 5 appears in the result, the sum of the numbers for which 5 is a factor is 0 so we have [5, 0] in the result amongst others.

- In Fortran - as in any other language - the returned string is not permitted to contain any redundant trailing whitespace: you can use dynamically allocated character strings.

```java
public class SumOfDivided {
  public static String sumOfDivided(int[] l) {
    // your code
  }
}
```

<details><summary>Solution</summary>

```java
public class SumOfDivided {
    public static String sumOfDivided(int[] l) {
        int max = Math.abs(l[0]);
        for (int i = 1; i < l.length; i++) {
            if (Math.abs(l[i]) > max) max = Math.abs(l[i]);
        }

        boolean[] prime = new boolean[max + 1];
        for (int i = 0; i <= max; i++) prime[i] = true;
        for (int p = 2; p * p <= max; p++) {
            if (prime[p]) {
                for (int i = p * p; i <= max; i += p) {
                    prime[i] = false;
                }
            }
        }
      
        StringBuilder result = new StringBuilder();
      
        for (int i = 2; i <= max; i++) {
            if (prime[i]) {
                int sum = 0;
                boolean hasSum = false;
                for (int n : l) {
                    if (n % i == 0) {
                        sum += n;
                        hasSum = true;
                    }
                }
                if (hasSum) result.append("(").append(i).append(" ").append(sum).append(")");
            }
        }
      
        return result.toString();
    }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

## Most frequently used words in a text

Write a function that, given a string of text (possibly with punctuation and line-breaks), returns an array of the top-3 most occurring words, in descending order of the number of occurrences.

Assumptions:
- A word is a string of letters (A to Z) optionally containing one or more apostrophes (') in ASCII.
- Apostrophes can appear at the start, middle or end of a word ('abc, abc', 'abc', ab'c are all valid)
- Any other characters (e.g. #, \, / , . ...) are not part of a word and should be treated as whitespace.
- Matches should be case-insensitive, and the words in the result should be lowercased.
- Ties may be broken arbitrarily.
- If a text contains fewer than three unique words, then either the top-2 or top-1 words should be returned, or an empty array if a text contains no words.

For java users, the calls will actually be in the form: TopWords.top3(String s), expecting you to return a List<String>.

Bonus points (not really, but just for fun):
1. Avoid creating an array whose memory footprint is roughly as big as the input text.
2. Avoid sorting the entire array of unique words.

Examples:

```
top_3_words("In a village of La Mancha, the name of which I have no desire to call to
mind, there lived not long since one of those gentlemen that keep a lance
in the lance-rack, an old buckler, a lean hack, and a greyhound for
coursing. An olla of rather more beef than mutton, a salad on most
nights, scraps on Saturdays, lentils on Fridays, and a pigeon or so extra
on Sundays, made away with three-quarters of his income.")
# => ["a", "of", "on"]

top_3_words("e e e e DDD ddd DdD: ddd ddd aa aA Aa, bb cc cC e e e")
# => ["e", "ddd", "aa"]

top_3_words("  //wont won't won't")
# => ["won't", "wont"]
```

```java
import java.util.List;

public class TopWords {
    
    public static List<String> top3(String s) {
        // Your code here
        return null;
    }
}
```

<details><summary>Solution</summary>

```java
import java.util.*;

public class TopWords {
    
    public static List<String> top3(String s) {
        Map<String, Integer> wordsCounter = new HashMap<>();
        Arrays.stream(s.split("[^a-zA-Z']+"))
          .filter(word -> !word.isEmpty() && !word.matches("[']+"))
          .map(String::toLowerCase)
          .forEach(word -> {Integer qty = wordsCounter.get(word); wordsCounter.put(word, qty == null ? 1 : ++qty);});
        return wordsCounter.entrySet().stream()
          .sorted(Map.Entry.comparingByValue(Comparator.reverseOrder()))
          .limit(3)
          .map(Map.Entry::getKey)
          .toList();
    }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

