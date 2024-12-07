# Question #14 Length Of Last Word

## Solution
```php []
class Solution {

    /**
     * @param String $s
     * @return Integer
     */
    function lengthOfLastWord($s) {

        // Replace whitespace and trim
        $s = str_replace('  ', ' ', $s);
        $s = trim($s);

        // Split the string into an array of words
        $strings = explode(" ", $s);

        // Find the last word in the array
        $lastWord = $strings[count($strings) - 1];
        
        return strlen($lastWord);
    }
}
```
