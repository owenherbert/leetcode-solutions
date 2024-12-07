# Question #13 Roman To Integer

## Solution
```php []
class Solution {

    /**
     * @param String $s
     * @return Integer
     */
    function romanToInt($s) {

        // Split the string into an array
        $romanNumeralArray = str_split($s);

        // Create sum variable
        $sum = 0;

        // Iterate over elements of the array
        for ($i = 0; $i < count($romanNumeralArray); $i++) {
            $currentNumeral = $romanNumeralArray[$i];
            $nextNumeral = null;

            // Find next numeral if possible
            if ($i < count($romanNumeralArray) - 1) {
                $nextNumeral = $romanNumeralArray[$i+1];
            }

            // Add roman numeral value to sum
            if ($currentNumeral === 'I') {
                // Handle roman numeral combinations
                if ($nextNumeral === 'V') {
                    $sum += 4;
                    $i++;
                } else if ($nextNumeral === 'X') {
                    $sum += 9;
                    $i++;
                } else {
                    $sum += 1;
                }
            } else if ($currentNumeral === 'V') {
                $sum += 5;
            } else if ($currentNumeral === 'X') {
                // Handle roman numeral combinations
                if ($nextNumeral === 'L') {
                    $sum += 40;
                    $i++;
                } else if ($nextNumeral === 'C') {
                    $sum += 90;
                    $i++;
                } else {
                    $sum += 10;
                }
            } else if ($currentNumeral === 'L') {
                $sum += 50; 
            } else if ($currentNumeral === 'C') {
                // Handle roman numeral combinations
                if ($nextNumeral === 'D') {
                    $sum += 400;
                    $i++;
                } else if ($nextNumeral === 'M') {
                    $sum += 900;
                    $i++;
                } else {
                    $sum += 100;
                }
            } else if ($currentNumeral === 'D') {
                $sum += 500;
            } else if ($currentNumeral === 'M') {
                $sum += 1000;
            }
        }

        return $sum;
    }
}
```
