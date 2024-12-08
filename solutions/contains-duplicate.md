# Question #217 Contains Duplicate

## Solution
```php []
class Solution {

    /**
     * @param Integer[] $nums
     * @return Boolean
     */
    function containsDuplicate($nums) {

        // Create an array of unique numbers
        $uniqueNums = [];
        
        // Iterate over numbers and check them
        for ($i = 0; $i < count($nums); $i++) {
            $number = $nums[$i];
            $numberKey = (string) $number;
            $alreadyExists = array_key_exists($numberKey, $uniqueNums);

            if ($alreadyExists) {
                return true;
            } else {
                $uniqueNums[$numberKey] = true;
            }
        }

        return false;
    }
}
```
