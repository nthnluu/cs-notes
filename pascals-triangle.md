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

> **Problem:** Given a non-negative integer `numRows`, generate the first `numRows` of Pascal's triangle.

```
/**
 * @param {number} numRows
 * @return {number[][]}
 */

function getItem(j, row) {
    if (j < 0 || j >= row.length) {
        return 0
    } else {
        return row[j]
    }
}

var generate = function(numRows) {
    var rows = [[1]]
    
    for (let i = 0; i <= (numRows - 1); ++i) {
        var newRow = []
        for (let j = 0; j <= i; ++j) {
            let digit = getItem(j-1, rows[i]) + getItem(j, rows[i])
            newRow.push(digit)
        }
        rows.push(newRow)
    }
    
    rows.shift()
    return rows
    
};
```
