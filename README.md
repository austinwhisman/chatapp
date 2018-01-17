# RealTimechatApp

Real Time Chat Application made with Laravel echo, Vue.js, and Pusher.

Simply set up your environment and begin. It would be helpful if you have node.js and npm installed.

# Setting up

> **1.** open up your terminal and cd to the appropriate path where your project is located.

> **2.** run command **composer install**

> **3.** run command **php artisan cache:clear**

> **4.** Establish proper database connection

## DATABASE
I used Mamp for my enviornment. Assuming you're using a Mac the socket defined should be set already. If using another OS you will most likely need to edit this if a unix socket is required.

 Make sure your database connection matches up in the **.env** and your **config/database.php** file.

> **config/database.php**
```
'host' => env('DB_HOST', '127.0.0.1'),
'port' => env('DB_PORT', '3306'),
'database' => env('DB_DATABASE', 'forge'),
'username' => env('DB_USERNAME', 'forge'),
'password' => env('DB_PASSWORD', ''),
'unix_socket' => env('DB_SOCKET', '/Applications/MAMP/tmp/mysql/mysql.sock')
```
> **.env**
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=forge
DB_USERNAME=forge
DB_PASSWORD=
```
> This setup is appropriate if using mysql as your database. You will need to define the Host, Port, Database, Username, and password.


## SQLite

  If you would prefer to use SQLite, here is a resource. 
  > **http://laravel-recipes.com/recipes/118/setting-up-the-sqlite-database-driver**
  
  You should be able to run these commands to set up your local development afterwards.
  
  > **php artisan migrate**
  
  > **php artisan serve**

## PUSHER DETAILS
You will need a Pusher Account. Create an account and an application. the necessary values will be created for you by the pusher application. With these values, fill out the details in your .**env** file and your **bootstap.js located in resources/assets/js/bootstrap.js** 

> **.env**
```
 PUSHER_APP_ID=
 PUSHER_APP_KEY=
 PUSHER_APP_SECRET=
 PUSHER_APP_CLUSTER=
```


> **bootstap.js**
```
import Echo from 'laravel-echo'
window.Pusher = require('pusher-js');
window.Echo = new Echo({
   broadcaster: 'pusher', 
   key: 'your_key', 
   cluster: 'your_cluster', 
   encrypted: true
});
```

**If using outside of the US, make sure you set the appropriate cluster. **

### Features

Real Time chat. If you have more than one browser up and running the application, it will update when you send the message without refreshing.

Will indicate how many **Different** users are present in the chat room. This allows for more than two users to interact at once.

If the user is not signed in, they will be sent to a login screen and prompted to sign in or register.
