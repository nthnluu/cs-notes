# Pascal's Triangle
> **Problem:** Given an integer `rowIndex`, return the `rowIndex`th row of the Pascal's triangle.

## Steps to solve
* Use a for-loop to generate each row of Pascal's Triangle until we reach `rowIndex`.
* Inside the for-loop, use another for-loop to generate each row's values, storing them inside the `newRow` variable.
    * Generate each row by getting the previous element and adding the current element to `newRow`
 * Set `row` to `newRow`
 * return `row`

```
/**
 * @param {number} rowIndex
 * @return {number[]}
 */

function getItem(j, row) {
    if (j < 0 || j >= row.length) {
        return 0
    } else {
        return row[j]
    }
}

var getRow = function(rowIndex) {
    var row = [1]
    
    for (var i=0; i <= rowIndex; ++i) {
        var newRow = []
        for (var j = 0; j <= i; ++j) {
            let num = getItem((j - 1), row) + getItem(j, row)
            newRow.push(num)
        }
        row = newRow
    }
    
    return row
};

```
