# ![java](java-logo.png) Java solutions for [Codewars](https://www.codewars.com/) katas

## Challenges

| Kyu | Title                                                         |
|:---:|:--------------------------------------------------------------|
|  6  | [Stop gninnipS My sdroW!](#stop-gninnips-my-sdrow)            |
|  7  | [Reverse words](#reverse-words)                               |
|  7  | [String ends with?](#string-ends-with)                        |
|  6  | [Find the odd int](#find-the-odd-int)                         |
|  6  | [Build a pile of Cubes](#build-a-pile-of-cubes)               |
|  7  | [Growth of a Population](#growth-of-a-population)             |
|  7  | [Odd or Even?](#odd-or-even)                                  |
|  5  | [RGB To Hex Conversion](#rgb-to-hex-conversion)               |
|  6  | [Convert string to camel case](#convert-string-to-camel-case) |

  
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
  	return odd
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

