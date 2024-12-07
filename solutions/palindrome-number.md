# Question #9 Palindrome Number

## Solution
```php []
class Solution {

    /**
     * @param Integer $x
     * @return Boolean
     */
    function isPalindrome($x) {

        // A palindrome cannot be negative
        if ($x < 0) return false;

        // Create a string representation of the integer
        $string = strval($x);
        
        // Create a reversed representation of the integer
        $reversedString = strrev($string);

        // Compare the values
        return $string === $reversedString;
    }
}
```
