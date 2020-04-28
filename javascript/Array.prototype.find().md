# Array.prototype.find()

Refs:
* [Standard built-in objects
](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)

Returns the first founded value based on given filter function. Otherwise returns <i>undefined</i>

## Sintax
> arr.find(callback(element[, index[, array]])[, thisArg])

## Examples
### Find in array
    const heroes = ['Wonder Woman', 'Batman', 'Brazilian worker', ]

    console.log(heroes.find( hero => hero == 'Batman' ))
    // "Batman"

### Find in object array
    const heroes = [
        {
            name: 'Wonder Woman',
            country: 'USA'
        },
        {
            name: 'Batman',
            country: 'USA'
        },
        {
            name: 'Brazilian worker',
            country: 'Brazil'
        },

    ]

    console.log(heroes.find( hero => hero.country === 'Brazil' ))
    // Object { name: "Brazilian worker", country: "Brazil" }