## **Basic Flask Deployment on Heroku**

_We need to create these text files_

```1.Aptfile```
- This is where you are going to put your packages that will be installed into the your web application
```
# you can list packages
libexample-dev

# or include links to specific .deb files
https://downloads.example.com/example.deb

# or add custom apt repos (only required if using packages outside of the standard Ubuntu APT repositories)
:repo:deb https://apt.example.com/ example-distro main

```
```2. wsgi.py```
- add this code in your into the wsgi.py
```
# Example That you have app.py as your main
# so the code will go like this
from app import app
  
if __name__ == "__main__":
        app.run()
```
```3. Procfile```
- so this is the config file where it will run as gunicorn, and the app.py "CORRECT ME IF I'M WRONG"

```
web: gunicorn wsgi:app
```
****

####if you want to add packages on Aptfile you are going to install this on your heroku repo
```
heroku buildpacks:add --index 1 heroku-community/apt
```
****

### To Deploy on Heroku

We need to create a account on Heroku then downloading 
- git
- heroku cli

```
To create and app and deploying it you need to follow this code 
which will be run in the folder of your  project
$ git init
$ git add .
$ git commit -m "Initial Commit"

# HEROKU CLI

heroku login
> login through the browser

heroku create hello_world
> this will create a app called hello_world 
> which will be deploy as hello_word.herokuapp.com

git push
> push the files into the heroku

```


Sources: https://elements.heroku.com/buildpacks/heroku/heroku-buildpack-apt
