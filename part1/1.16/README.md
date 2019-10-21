Live at
http://dank-test-app.herokuapp.com/

commands
```
$ docker pull devopsdockeruh/heroku-example
$ docker tag devopsdockeruh/heroku-example registry.heroku.com/dank-test-app/web
$ heroku login
$ heroku container:login
$ docker push registry.heroku.com/dank-test-app/web
$ heroku container:release web -a dank-test-app
```
