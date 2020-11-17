# Two Sum

## Hashmap Implementation
```
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    let result
    let numberMap = new Map();
    nums.forEach((element, index) => numberMap.set(element, index))

    for (i = 0; i < nums.length && !result; ++i) {
        const neededNum = target - nums[i]

        if (numberMap.has(neededNum)) {
            if (numberMap.get(neededNum) !== i) {
                result = [numberMap.get(neededNum), i]
            }
        }
    }

    return result
};
```
