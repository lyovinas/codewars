# ![java](java-logo.png) Java solutions for [Codewars](https://www.codewars.com/) katas

## Challenges

| Kyu | Title                                              |
|:---:|:---------------------------------------------------|
|  6  | [Stop gninnipS My sdroW!](#stop-gninnips-my-sdrow) |
|  7  | [Reverse words](#reverse-words)                    |
|  7  | [String ends with?](#string-ends-with)             |
|  6  | [Find the odd int](#find-the-odd-int)              |

  
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
  }
}
```
</details>

**[⬆ Back to Top](#challenges)**

---

