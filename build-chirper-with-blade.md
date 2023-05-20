https://bootcamp.laravel.com/blade/installation
https://artisansweb.net/how-to-run-laravel-artisan-commands-in-visual-studio-code/

If you have already installed PHP and Composer on your local machine, you may create a new Laravel project via Composer:
cd ~/src
git clone git@github.com:brentgroves/chirper.git
pushd ~/src/chirper
composer create-project laravel/laravel chirper
https://unit.nginx.org/howto/laravel/
sudo chown -R unit:unit chirper
namei -l `pwd`/app
Note
The unit:unit user-group pair is available only with official packages, Docker images, and some third-party repos. Otherwise, account names may differ; run the ps aux | grep unitd command to be sure.
https://unit.nginx.org/howto/security/#sec-files
unitd -h


cd chirper
After the project has been created, start Laravel's local development server using the Laravel's Artisan CLI serve command:
On another terminal run dbgpClient to verify debugging is working.
cd chirper
php artisan serve
ctrl-c twice

# Installing Laravel Breeze
Next, we will give your application a head-start by installing Laravel Breeze, a minimal, simple implementation of all of Laravel's authentication features, including login, registration, password reset, email verification, and password confirmation. Once installed, you are welcome to customize the components to suit your needs.

Laravel Breeze offers several options for your view layer, including Blade templates, or Vue and React with Inertia. For this tutorial, we'll be using Blade.

Open a new terminal in your chirper project directory and install your chosen stack with the given commands:
pushd ~/src/chirper/chirper
composer require laravel/breeze --dev
 
php artisan breeze:install blade

Breeze will install and configure your front-end dependencies for you, so we just need to start the Vite development server to automatically recompile our CSS and refresh the browser when we make changes to our Blade templates:

npm run dev
Finally, open another terminal in your chirper project directory and run the initial database migrations to populate the database with the default tables from Laravel and Breeze:

Finally, open another terminal in your chirper project directory and run the initial database migrations to populate the database with the default tables from Laravel and Breeze:

https://laravel.com/docs/10.x/sail#xdebug-cli-usage

A sail debug command may be used to start a debugging session when running an Artisan command:

# Run an Artisan command without Xdebug...
sail artisan migrate
 
# Run an Artisan command with Xdebug...
sail debug migrate

https://www.stackhawk.com/blog/laravel-cors/
### Running Vite
There are two ways you can run Vite. You may run the development server via the dev command, which is useful while developing locally. The development server will automatically detect changes to your files and instantly reflect them in any open browser windows.

Or, running the build command will version and bundle your application's assets and get them ready for you to deploy to production:

# Run the Vite development server...
npm run dev
 
# Build and version the assets for production...
npm run build





