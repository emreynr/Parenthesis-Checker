# Parenthesis-Checker
Parenthesis Checker with Java


```java

import java.util.Stack;

public class ParenthesisCheckerJava {

    // checker method
    public static boolean parenthesisIsBalanced(String stringValue) {

        // Create stack
        Stack<Character> stack = new Stack<>();

        // Check all each chars in the given string
        for (int i = 0; i < stringValue.length(); i++) {
            char currentChar = expression.charAt(i);

            if (currentChar == '(' || currentChar == '{' || currentChar == '[') {
                stack.push(currentChar);
            }
            else if (currentChar == ')' || currentChar == '}' || currentChar == ']') {
                if (stack.isEmpty()) {
                    return false;
                }
                // get the top element
                char topChar = stack.pop();

                // Check all chars if equals or not
                if (currentChar == ')' && topChar != '(' ||
                    currentChar == '}' && topChar != '{' ||
                    currentChar == ']' && topChar != '[') {
                    return false;
                }
            }
        }

        // All Parenthesis are equal if stack is emtpy
        return stack.isEmpty();
    }

    public static void main(String[] args) {

        // Check with some examples
        String string1 = "{[()]}";
        String string2= "{[(])}";
        String string3 = "{{[[(())]]}}";

        System.out.println(parenthesisIsBalanced(string1)); // output -> true
        System.out.println(parenthesisIsBalanced(string2)); // output -> false
        System.out.println(parenthesisIsBalanced(string3)); // output -> true
    }
}
```
