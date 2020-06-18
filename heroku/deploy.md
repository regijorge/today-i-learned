## Deploying to Heroku

### Install Heroku Cli
https://devcenter.heroku.com/articles/heroku-cli
```
sudo snap install --classic heroku
```

### Login
```
heroku login
```

### Add ssh key
```
heroku keys:add
```

### Create app
Inside project folder run:
```
heroku create <APP_NAME>
```

### Add git remote to herku repository
```
heroku git:remote -a <APP_NAME>
```

### Push to heroku
```
git push heroku master
```

