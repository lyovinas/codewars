# ![java](java-logo.png) Java solutions for [Codewars](https://www.codewars.com/) katas

## Challenges

| Kyu | Title                                              |
|:---:|:---------------------------------------------------|
|  6  | [Stop gninnipS My sdroW!](#stop-gninnips-my-sdrow) |
|  7  | [Reverse words](#reverse-words)                    |
|  7  | [String ends with?](#string-ends-with)             |

  
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

