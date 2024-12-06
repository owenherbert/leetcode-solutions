# Question #1 Two Sum

## Solution
```php []
class Solution {

    /**
     * @param Integer[] $nums
     * @param Integer $target
     * @return Integer[]
     */
    function twoSum($nums, $target) {

        // Hashmap to store value-to-index mappings
        $hashMap = [];

        // Iterate over the array once
        foreach ($nums as $i => $num) {

            // Calculate the complement
            $complement = $target - $num;

            // Check if complement is already in the hashmap
            if (isset($hashMap[$complement])) {
                return [$hashMap[$complement], $i];
            }

            // Store the current number and its index in the hashmap
            $hashMap[$num] = $i;
        }

        // Return an empty array if no solution is found
        return [];
    }
}
```
