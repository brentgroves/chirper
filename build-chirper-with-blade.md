https://bootcamp.laravel.com/blade/installation
https://artisansweb.net/how-to-run-laravel-artisan-commands-in-visual-studio-code/

If you have already installed PHP and Composer on your local machine, you may create a new Laravel project via Composer:
cd ~/src
git clone git@github.com:brentgroves/chirper.git
pushd ~/src/chirper
composer create-project laravel/laravel chirper
https://unit.nginx.org/howto/laravel/
sudo chown -R unit:unit chirper
Note
The unit:unit user-group pair is available only with official packages, Docker images, and some third-party repos. Otherwise, account names may differ; run the ps aux | grep unitd command to be sure.
https://unit.nginx.org/howto/security/#sec-files
unitd -h


cd chirper
After the project has been created, start Laravel's local development server using the Laravel's Artisan CLI serve command:
cd chirper
php artisan serve

