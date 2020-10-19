# Serverless Framework

## Create project
### Options
--name = Project Name
--path = Folder Name
--template = Template
--template-url = Custom Template

## Tips
* May use "sls" instead of "serverless"

### Template
```
serverless create --template aws-nodejs
```

### Custom Template
```
serverless create --name <PROJECT_NAME> --template-url https://github.com/codingly-io/sls-base
```

## Deploy
### Entire project
```
serverless deploy -v
```

### Stage
```
serverless deploy -s <STAGE>
```

### Specific function
```
serverless deploy -f <FUNCTION_NAME> -v
```

## Remove
```
serverless remove -v
```

## Function logs in terminal
Include "-t" to watch logs in real time
```
serverless logs -f <FUNCTION_NAME>
```

## Run function from terminal
```
serverless invoke -f <FUNCTION_NAME> -l
```

## Get info
```
serverless info
```

