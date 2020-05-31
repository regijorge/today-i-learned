# Comparison Operators


## Embeeded documents
    {'<KEY>.<SUB_KEY>.<SUB_SUB_KEY>' : <VALUE>}


## Query operators
### EQUAL

    {<KEY_PATH>: {$eq: <VALUE>}}
    {<KEY_PATH>: <VALUE>}

### NOT EQUAL

    {<KEY_PATH>: {$ne: <VALUE>}}

### LOWER THAN

    {<KEY_PATH>: {$lt: <VALUE>}}

### LOWER THAN OR EQUAL

    {<KEY_PATH>: {$lte: <VALUE>}}

### GREATER THAN

    {<KEY_PATH>: {$gt: <VALUE>}}

### GREATER THAN OR EQUAL

    {<KEY_PATH>: {$gte: <VALUE>}}

### IN

    {<KEY_PATH>: {$in: [<VALUE1>, <VALUE2>, <VALUE3>]}}

### NOT IN

    {<KEY_PATH>: {$nin: [<VALUE1>, <VALUE2>, <VALUE3>]}}


## Logical Operators

### OR

    {$or: [{<FILTER1>}, {<FILTER2>}]}

### NOR

    {$nor: [{<FILTER1>}, {<FILTER2>}]}

### AND

    {$and: [{<FILTER1>}, {<FILTER2>}]}


## Elements Operators

### EXISTS

    {<KEY_PATH>: {$exists: true}}
    {<KEY_PATH>: {$exists: false}}

### TYPE
[Ref](https://docs.mongodb.com/manual/reference/bson-types/)

    {<KEY_PATH>: {$type: <TYPE>}}


## Evaluation

### REGEX

    {<KEY_PATH>: {$regex: /<PATTERN>/}}


### SIZE
    {<KEY_PATH>: {$size: <NUMBER>}}


## Quering arrays

### ELEM MATCH
    {<KEY_PATH>: {$elemMatch: [<FILTER1>, <FILTER2>]}}
