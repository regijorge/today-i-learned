# CLI

## Create profile
```
aws configure --profile <PROFILE_NAME>
```

### Check current profile configuration
```
aws configure list
```

## Switch profile
To use a named profile for multiple commands, you can avoid specifying the profile in every command by setting the AWS_PROFILE environment variable at the command line.
```
export AWS_PROFILE=<PROFILE_NAME>
```
