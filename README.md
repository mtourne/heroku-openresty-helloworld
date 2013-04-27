# Hello world with Openresty - Heroku

Not much to see here, I was new to heroku and installed Openresty in 10 minutes thanks to :
https://github.com/leafo/heroku-openresty

## Installing

clone this repo normally :

    $ git clone https://github.com/mtourne/heroku-openresty-helloworld.git

eventually, rename it :

    $ mv heroku-openresty-helloworld my_cool_project
    $ cd my_cool_project

if you're a first time heroku user like me :
(you'll find heroku-toolbelt command line here: https://toolbelt.heroku.com/)

    $ heroku login

create your new heroku app

    $ heroku create --buildpack http://github.com/leafo/heroku-buildpack-lua.git


the output will look like this (you can always rename this later)

```
Creating gentle-taiga-4242... done, region is us
BUILDPACK_URL=http://github.com/leafo/heroku-buildpack-lua.git
http://gentle-taiga-4242.herokuapp.com/ | git@heroku.com:gentle-taiga-4242.git
```

let's add a new git remote in order to deploy to your new heroku instance:

    $ git remote add heroku git@heroku.com:gentle-taiga-4242.git


now, whatever you push to the heroku remote will get deployed :

    $ git push heroku master


it should say a bunch of things, but most importantly :

```
-----> Launching... done, v6
       http://gentle-taiga-4242.herokuapp.com deployed to Heroku
```

you can now run your web app :

    $ heroku scale web=1


You should know be able to go to your herokuapp page, and see your request with :

    $ heroku logs -t


Happy hacking!
