# MongoDB $inc Operator Error with String Value
This example demonstrates a common error in using the MongoDB `$inc` operator with an incorrect data type.  The `$inc` operator is designed to increment a numerical value. Attempting to increment a field with a non-numeric value (such as a string) will result in an error or unexpected results.

## Bug
The code `db.collection('myCollection').updateOne({name: 'John'}, {$inc: {age: '1'}})` attempts to increment the `age` field by '1', which is a string. This will not behave as intended.

## Solution
Use a number to increment the `age` field: `db.collection('myCollection').updateOne({name: 'John'}, {$inc: {age: 1}});`