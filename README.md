# Laravel installproject

This is a simple Composer script which listed basic commands that is used to setup a Laravel project in a shared hosting or VPS.

### Requirements

1. [Composer](https://getcomposer.org/).
2. [NodeJS](https://nodejs.org/en/) (for NPM).
3. [PHP](https://www.php.net/).

### The script includes these commands:
1. `npm install` : Install NPM packages.
2. `composer install` : Install Composer packages.
3. `php artisan storage:link` : Create symbolic links.
4. `php artisan migrate` : Migrate the database tables.
5. `npm run prod` : Compile assets with Laravel Mix.
6. `php artisan key:generate` : Generate application key.

### How to use

1. Insert the following event inside `scripts` property in `composer.json` file.
      ```json
        "install-project": [
            "npm install && npm run prod",
            "composer install",
            "@php artisan key:generate",
            "@php artisan migrate",
            "@php artisan key:generate"
        ]
      ```
      Example:
      ```json
        "scripts": {
          "install-project": [
            "npm install && npm run prod",
            "composer install",
            "@php artisan key:generate",
            "@php artisan migrate",
            "@php artisan key:generate"
          ],
        },
      ```
2. Run `composer run-script install-project` inside your terminal.
3. Done!
        
### FAQ
1. Why did you create this script?

   This is because I usually forget a few steps when setting up any Laravel project in shared hosting or VPS. 

2. Why don't you turn this into a package?

   Because, I don't know how :)
   
3. I have a suggestion to add new commands.

   Open an issue and I'll try to look it up.

<br>

**Laravel is a Trademark of Taylor Otwell.**
