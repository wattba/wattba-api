# wattba-api


Start by creating a django project
Install python
Install pip
Install pipenv

Create a folder
cd into the foler

pipenv install django

pipenv shell

django-admin startproject instagram_project

instagram project .

django-admin startapp instagram

register app in settings.py

runserver the app is there

Go to the models file and add the following

let django know that we are using our own users
AUTH_USER_MODEL = "instagram.User"
install Pillow (python images)

- ./manage.py makemigrations

		Migrations for 'instagram':
  			instagram/migrations/0001_initial.py
    			- Create model User
    			- Create model Post
- ./manage.py migrate
 Operations to perform:
  Apply all migrations: admin, auth, contenttypes, instagram, sessions
Running migrations:
  Applying contenttypes.0001_initial... OK
  Applying contenttypes.0002_remove_content_type_name... OK
  Applying auth.0001_initial... OK
  Applying auth.0002_alter_permission_name_max_length... OK
  Applying auth.0003_alter_user_email_max_length... OK
  Applying auth.0004_alter_user_username_opts... OK
  Applying auth.0005_alter_user_last_login_null... OK
  Applying auth.0006_require_contenttypes_0002... OK
  Applying auth.0007_alter_validators_add_error_messages... OK
  Applying auth.0008_alter_user_username_max_length... OK
  Applying auth.0009_alter_user_last_name_max_length... OK
  Applying instagram.0001_initial... OK
  Applying admin.0001_initial... OK
  Applying admin.0002_logentry_remove_auto_add... OK
  Applying admin.0003_logentry_add_action_flag_choices... OK
  Applying sessions.0001_initial... OK

- python manage.py createsuperuser
	- username: yourname
	- email: your@name
	-password: 1111
	-confirm
	output:
	This password is too short. It must contain at least 8 characters.
	This password is too common.
	This password is entirely numeric.

Thanks django but not now

- GO into settings and you will see:
AUTH_PASSWORD_VALIDATORS = [
    {
        'NAME': 'django.contrib.auth.password_validation.UserAttributeSimilarityValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.MinimumLengthValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.CommonPasswordValidator',
    },
    {
        'NAME': 'django.contrib.auth.password_validation.NumericPasswordValidator',
    },
]

Bypass password validation and create user anyway? [y/N]
y

- python manage.py runserver
localhost:8000/admin

Add the admin files

now view the post and users from the admin view

----------------------------------------------------------------------

Django Rest framework

Sending the model date over to the reactapp
- pipenv install djangorestframework
- pipenv install django-cors-headers

add to installed apps in settings.py
    'corsheaders',
    'rest_framework'

add the courseheader's middleware
 -'corsheaders.middleware.CorsMiddleware'
 - CORS Headers allows the reactjs front end to access our application
 -add the courseheaders middleware

 Serializer
  - convert django model data into json files ->for reactjs

update our views
 - we now have views but how to we access them: create urls
 - add a urls.py file for our app

 regiser your app's urls in the project urls


 ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

 Get connected with REACJS

 install nodejs
 check that it works
    - npm
    - npm install -g create-react-app
    - create-react-app -V
      2.1.5
    -create-react-app frontend
    -cd frontend
    -yarn start
    -check localhost:3000
    - got to src->App.js, replace the text 'Learn React' with 'Build Django', click save and you will see that it updates automatically.

    UI -> bootsrap ->reactstrap
    -npm install --save bootstrap
    -npm install --save reactstrap react react-dom
    -reactstrap does not come with css, it comes with the react components
    - we will still need bootstrap
    -we run yarn install (update yarn about new json packages)


    Add boostrap to our index.js file
      -import 'bootstrap/dist/css/bootstrap.css';
      -import './App.css';
      - add some simple buttons and rows

add the api connection
  api.js

inside of App.js
  - add the constructor, didMount and get data
  - you should see the data on the console

create a folder in side of frontend/src called components
- create a file called posts.js

Go through the learn react stuff

Install avatar

$ npm install react-avatar --save
 
# besides React, react-avatar also has prop-types as peer dependency, 
# make sure to install it into your project 
$ npm install prop-types --save