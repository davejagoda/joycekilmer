Before beginning, make sure the name you want is available on Heroku and in your git repositories.

`cd` to your top level source directory:

`cd ~/src/github/`

Create a directory to hold the code repository and `cd` into it:

`mkdir joycekilmer`

`cd joycekilmer`

Make sure Heroku is working and that you are the user you expect if you have more than one account:

`heroku auth:whoami`

Create the Heroku app:

`heroku create joycekilmer`

You'll get back something like this:

Creating joycekilmer... done, stack is cedar-14
https://joycekilmer.herokuapp.com/ | https://git.heroku.com/joycekilmer.git

Create the Github repo:

`curl -d '{"name": "joycekilmer"}' -H X-GitHub-OTP:123456 -u davejagoda https://api.github.com/user/repos`

Initialize the local git repo:

`git init`

Set Github remote:

`git remote add origin git@github.com:davejagoda/joycekilmer.git`

Set Heroku remote:

`heroku git:remote -a joycekilmer`

Install Composer locally:

`curl -sS https://getcomposer.org/installer | php`

Use Composer to install local dependencies:

`php composer.phar update`
