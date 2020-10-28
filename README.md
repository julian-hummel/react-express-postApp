# react-express-postApp

## Overview

This application has a react frontend and an express backend. In general, you can register to the app and login with your login credentials. 
Features as change or forgot password are not available. After registering and logging in, you can create posts, in the 'Sprüche' - Section. These posts can be seen by non-registered users.
Only registered users can create posts. Moreover, admin accounts may exist, which can also delete all posts from other users.

## Create an admin account

As the application is connected to a local mongodb database, a registered user in the database may be modified, to obtain admin rights. If simply an attribute role:"admin" is added to the user object
in the database, the user gets admin rights, as the admin role is processed by the app. To remove admin rights, the role attribute has to be removed.

## Login-Security

After successfully loggging in, a jwt-token is returned. This token is used for further authorisation and authentication and contains the user data. In this case, the token expires after 
24 minutes and is not refreshed during the session. After expiration and reload, the user is logged out automatically and is supposed to login again. As the token is saved in the local storage,
the page may be closed and opened again, without causing a logout as long as the token is still valid. 

## Features to add

* Password change
* Password forgot and set new password
* Change user data in settings
* optional: commenting posts of other people
* optional: own page, that shows only the self-posted posts
