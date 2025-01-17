# Laravel API coding test
#### Arash Tajdar

## About the project
This is a simple laravel api to manage events. 
Users can CRUD.

### I used :
- Sanctum for Auth
- Laravel collections to display the results
- Faker and factory for feature tests
- Middleware to count product view count

### Necessary improvements :

- Avoid using eloquent inside controller (it's sample, and I used them inside for now)
- feature tests can be extended.
- Documentation can get improved.
- Docker and related files need improvements.
- Update down method of some migrations
- Add policy to some controllers to manage who can edit products and category names
- create statistics table and create command to collect some statistics and save it in that table

## How to run the project

1. Create .env file and Copy .env.example file to this new file
2. Change variable like this or else you may encounter errors on running db-container
<pre>
   DB_CONNECTION=mysql
   DB_HOST=db
   DB_PORT=3306
   DB_DATABASE=laravel
   DB_USERNAME=laravelUser
   DB_PASSWORD=@wn12341818
</pre>
also 
<pre>QUEUE_CONNECTION=database
</pre>
   - It is important to :  
     - change host variable to db 
     - set a new username and password 
       - change the name of the database to laravel (you can modify this in docker-compose/mysql/db_init.sql file) 
   - The app will send an email after creating every product:<br>
you should change these settings in env file  and set the variables with working smtp settings to be able to send email from inside the app <br>
     (I can give you the settings)
<pre>
MAIL_HOST=
MAIL_PORT=
MAIL_USERNAME=
MAIL_PASSWORD=
</pre>
or if you want to disable this feature simply comment Line 31 in SendMailToAdminForNewProductListener.php

3. Run ./init.sh bash file (* it may take a long time to generate autoload file*)
4. Run localhost:8000 and use Postman collection (api.postman_collection.json) in root folder to send requests
5. you can also test all functionalities by initializing this repo ```https://github.com/arashtajdar/VueJs-sample```

