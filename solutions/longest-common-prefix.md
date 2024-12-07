# Question #14 Longest Common Prefix

## Solution
```php []
class Solution {

    /**
     * @param String[] $strs
     * @return String
     */
    function longestCommonPrefix($strs) {

        // Handle the edge case where the array is empty
        if (empty($strs)) {
            return "";
        }
        
        $longestPrefix = "";
        $firstString = $strs[0];
        $firstStringLetters = str_split($firstString);

        // Iterate over letters of the first string
        for ($i = 0; $i < count($firstStringLetters); $i++) {
            $letterToSearch = $firstStringLetters[$i];
            
            // Iterate and check each string
            foreach ($strs as $stringToSearch) {
                if ($i >= strlen($stringToSearch) || $stringToSearch[$i] !== $letterToSearch) {
                    // If we exceed the length of the current string or find a mismatch
                    return $longestPrefix;
                }
            }

            // If all strings match at this index, add to the prefix
            $longestPrefix .= $letterToSearch;
        }

        return $longestPrefix;
    }
}
```
