# Shell

Refs:
* [Docs](https://docs.mongodb.com/manual/mongo/)

## Connect to MongoDB Cloud
* [Ref](https://docs.atlas.mongodb.com/mongo-shell-connection/)

    mongo "mongodb+srv://{cluster}.mongodb.net/{collection}" --username {username}

### Show created dbs
    show dbs
    > {dbName}    0.000GB

### Use database
It not needs to be created yet

    use {dbName}
    > switched to db {dbName}

### Clear console
    cls

### Add document to dabase
    db.{collectionName}.insertOne({document})

    db.{collectionName}.insertMany([documentsList])

### Find document
    db.{collectionName}.findOne({query})
    db.{collectionName}.findMany({query}).pretty()

    db.{collectionName}.find({query})
    db.{collectionName}.find({query}).pretty()

### Update document
    db.{collectionName}.updateOne({query}, {$set: {newData}})

    db.{collectionName}.updateMany({query}, {$set: {newData}})

### Delete document
    db.{collectionName}.deleteOne({query})

    db.{collectionName}.deleteMany({query})

## Import data to Mongodbcloud
    mongoimport --uri "mongodb://<USERNAME>:<PASSWORD>@atlas-host1:27017,atlas-host2:27017,atlas-host3:27017/<DBNAME>?ssl=true&replicaSet=myAtlasRS&authSource=admin" --collection <COLLECTIONAME> --drop --file '<FILEPATH>'