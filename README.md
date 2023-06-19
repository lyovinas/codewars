# ![java](java-logo.png) Java solutions for [Codewars](https://www.codewars.com/) katas

## Challenges

| Kyu | Title                                              |
|:---:|:---------------------------------------------------|
|  6  | [Stop gninnipS My sdroW!](#stop-gninnips-my-sdrow) |
  
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

