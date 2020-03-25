## In what data type have we chosen to represent a book?

String

## Is this the best data type, do you think? Could we have chosen a more appropriate data type? Why?

No, as the title and author are concatenated.
It would be better to use an object as then you could use key/value pairs to separate these.

e.g.
```js
{
    title: "The Catcher in the Rye",
    author: "J.D. Salinger"
}
```

## Take a read of the Jest Documentation about [Matchers](https://jestjs.io/docs/en/using-matchers) such as `toBe` and `toEqual`. What other matchers might come in useful? Check the tests you have written and make a list of alternative matchers which you might have been able to use.

toBe uses tests exact equality whereas toEqual checks the value so is needed for objects such as arrays.

### Other useful matchers

- not.toBe tests for the opposite of toBe, can be used for other matchers
- truthiness: test the difference between null, undefined, false
- numbers: most ways of comparing numbers have matcher equivalents e.g. toBeGreaterThan
- floating point equality: toBeCloseTo as used in 001
- strings: toMatch, this can be used with regular expressions 

e.g.
```js
test('but there is a "stop" in Christoph', () => {
  expect('Christoph').toMatch(/stop/);
});
```
- arrays and iterables: toContain to search for a particular item


### Alternative matchers

I'm not sure which of these matchers I could use in my tests without changing the functions to return different values.

## What data types are considered "complex" data types?

- Arrays
- Objects
- Functions

## What data types are considered "primitive" data types?

- String
- Number
- Boolean

# #In JavaScript it is possible to use `==` ("double equals") or `===` ("triple equals") to compare two values. What is the difference and why do we prefer triple equals?

In js === tests that both the value and the data type are equal.
e.g.
```js
5 === 5 
// true
7 === "7"
// false
```

However == only matches the value after trying to turn both into the same data type. 
In this case:
```js
7 == "7"
// true
```

By using === we are truly testing whether both the value and data type are equal.
This also avoids problems where different types of falsy values (0, null, false, undefined) pass as being equal to each other when they are not.