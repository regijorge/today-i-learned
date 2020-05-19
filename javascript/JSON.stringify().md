# JSON.stringify()

Res:
* [Standard built-in objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify)


## Sintax
> JSON.stringify(value[, replacer[, space])

## Examples
### Simple usage
    const obj = {
        x: 'foo',
        y: 'bar',
        z: 1
    }
    const stringified = JSON.stringify(obj)
    console.log(stringified)
    // {"x":"foo","y":"bar","z":1}

    // With identation:
    const stringified1 = JSON.stringify(obj, null, 2)
    console.log(stringified1)