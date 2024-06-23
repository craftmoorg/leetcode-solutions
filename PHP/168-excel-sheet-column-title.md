[Back](./)

# 168. Excel Sheet Column Title
Given an integer columnNumber, return its corresponding column title as it appears in an Excel sheet.

For example:
\
A -> 1
\
B -> 2
\
C -> 3
\
...

Z -> 26
\
AA -> 27
\
AB -> 28
\
...


- Example 1:
\
Input: columnNumber = 1 
\
Output: "A"

- Example 2:
\
Input: columnNumber = 28
\
Output: "AB"

- Example 3:
\
Input: columnNumber = 701
\
Output: "ZY"

### Solution
```php
class Solution {

    /**
     * @param Integer $columnNumber
     * @return String
     */
    function convertToTitle($columnNumber) {
        $columnSymbol = '';

        while ($columnNumber > 0) {
            $num = ($columnNumber - 1) % 26;
            $columnSymbol = chr($num + 65) . $columnSymbol;
            $columnNumber = intval(($columnNumber - $num - 1) / 26); 
        }

        return $columnSymbol;
    }
}
```