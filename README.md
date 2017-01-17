# web_push_notifications

A demo project to send web based push notifications.

Please go through the article [here](http://thihara.github.io/Web-Push/) to undestand how this demo project is implemented and
how to generate the values needed for the required environmental variables.

# Requirements

* node >= 6
* npm

# Starting the app

You need to set the following environmental variables

```
VAPID_SUBJECT
VAPID_PUBLIC_KEY
VAPID_PRIVATE_KEY
AUTH_SECRET
```

Afterwards type

`npm install` 

to install the dependencies and then

`node index.js`

to start the server. If you don't have any environmental variable named `PORT` set, the server should start on port **8080**.

# Testing the app

1. Goto the URL http://localhost:8080 from either Chrome or Firefox, latest versions.
2. Click the *Subscribe to push notifications* button, and choose to allow notifications when prompted by the browser.
3. Use the following curl command to send a push notification, you will obviously need to change the `auth-secret` header 
value to match your environmental variable.

```
curl -G --header "auth-secret: qwertyuiop" "http://localhost:8080/notify/all" \
    --data-urlencode "title=Willy Wonka" \
    --data-urlencode "message=Willy Wonka's new chocklate is awesome" \
    --data-urlencode "clickTarget=http://www.favoritemedium.com"
```
