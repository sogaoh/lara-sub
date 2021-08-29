# laravel-heroku-app

## Procedure to run app

```
git clone https://github.com/sogaoh/laravel-heroku-app.git

cd /path/to/laravel-heroku-app

make local
make up
make chmod

make upb

make web

# In web Container
make npmid    # build js
exit

make app

# In app Container
make fresh    # migration 
exit

open http://localhost:3100
```
