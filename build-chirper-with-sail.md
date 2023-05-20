https://docs.docker.com/desktop/networking/
https://docs.docker.com/desktop/networking/
https://www.youtube.com/watch?v=iHad9TH9mOA
https://bootcamp.laravel.com/blade/installation#installation-via-docker

https://artisansweb.net/how-to-run-laravel-artisan-commands-in-visual-studio-code/

[only install the services you want](https://laravel.com/docs/10.x/installation#choosing-your-sail-services)
cd ~/src
mkdir chirper
curl -s "https://laravel.build/chirper?with=mysql" | bash
# or do this if projects already is in github
git clone git@github.com:brentgroves/chirper.git
pushd ~/src/chirper/chirper

# test project
./vendor/bin/sail up
from user agent run localhost

However, instead of repeatedly typing vendor/bin/sail to execute Sail commands, you may wish to configure a shell alias that allows you to execute Sail's commands more easily:

alias sail='[ -f sail ] && sh sail || sh vendor/bin/sail'

# Starting & Stopping Sail
Laravel Sail's docker-compose.yml file defines a variety of Docker containers that work together to help you build Laravel applications. Each of these containers is an entry within the services configuration of your docker-compose.yml file. The laravel.test container is the primary application container that will be serving your application.

Before starting Sail, you should ensure that no other web servers or databases are running on your local computer. To start all of the Docker containers defined in your application's docker-compose.yml file, you should execute the up command:

# start containers
sail up
# start in detached mode
To start all of the Docker containers in the background, you may  start Sail in "detached" mode:
sail up -d
# test
Once the application's containers have been started, you may access the project in your web browser at: http://localhost.
# stop containers
To stop all of the containers, you may simply press Control + C to stop the container's execution. Or, if the containers are running in the background, you may use the stop command:
sail stop

# start apps from sail
When developing applications using Sail, you may execute Artisan, NPM, and Composer commands via the Sail CLI instead of invoking them directly:
./vendor/bin/sail php --version
./vendor/bin/sail artisan --version
./vendor/bin/sail composer --version
./vendor/bin/sail npm --version

# xdebug
https://laravel.com/docs/10.x/sail#debugging-with-xdebug
Laravel Sail's Docker configuration includes support for Xdebug, a popular and powerful debugger for PHP. In order to enable Xdebug, you will need to add a few variables to your application's .env file to configure Xdebug. To enable Xdebug you must set the appropriate mode(s) before starting Sail:

SAIL_XDEBUG_MODE=develop,debug,coverage

sail artisan sail:publish

# check docker image from docker-compose.yml
build
  context: ./docker/8.2
# add copy command to dockerfile
COPY ext-xdebug.ini /etc/php/8.2/cli/conf.d/ext-xdebug.ini
# add ext-xdebug.ini to docker directory
[xdebug]
xdebug.start_with_request=yes
xdebug.discover_client_host=true
xdebug.max_nesting_level=256
xdebug.remote_handler=dbgp
xdebug.client_port=9003
xdebug.idekey=VSCODE
xdebug.mode=debug
# xdebug.client_host=host.docker.internal
xdebug.client_host=10.1.1.83
# change image name in docker-compose file
brentgroves/sail-8.2
# rebuild 
sail down
sail build --no-cache

docker inspect -f {{range.NetworkSettings.Networks}}{{.Gateway}}{{end}} test-laravel.test-1
I dont think this contains the correct info so i just 

# start
sail up -d
# check php version for xdebug 
sail php -v
# update 1st configuration in launch.json
      "port": 9000,
      "log": false,
      "externalConsole": false,
      "pathMappings": {
        "/var/www/html":"$workspaceFolder"
      },
      "ignore": [
        "**/vendor/**/*.php"
      ]
# Installing Laravel Breeze
Next, we will give your application a head-start by installing Laravel Breeze, a minimal, simple implementation of all of Laravel's authentication features, including login, registration, password reset, email verification, and password confirmation. Once installed, you are welcome to customize the components to suit your needs.

Laravel Breeze offers several options for your view layer, including Blade templates, or Vue and React with Inertia. For this tutorial, we'll be using Blade.

Open a new terminal in your chirper project directory and install your chosen stack with the given commands:
pushd ~/src/chirper/chirper
sail composer require laravel/breeze --dev
sail php artisan breeze:install blade
Breeze will install and configure your front-end dependencies for you, so we just need to start the Vite development server to automatically recompile our CSS and refresh the browser when we make changes to our Blade templates:
sail npm run dev

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





