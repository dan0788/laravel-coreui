<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

## This project is a corrected compilation of the original bilaschandra repository. Link original bilaschandra repository: https://github.com/bilaschandra/laravel-coreui. For more information: https://coreui.io/bootstrap/docs/integration-guides/laravel/
# The changes are:
1. The "Access to undeclared static property Spatie\Permission\PermissionRegistrar::$pivotPermission" error occurs when migrations are run because the migration is trying to access a static property ($pivotPermission) that is not declared static in the PermissionRegistrar class. To address this issue, the migration was modified to access the $pivotPermission property of a PermissionRegistrar instance, rather than attempting to access it as a static property.
2. The "Route [verification.verify] not defined" error indicates that Laravel is trying to redirect or generate a URL for a route with the name verification.verify and it is not defined in your routes files, because an SMTP service is needed to validation of emails at the time of registration. Therefore MustVerifyEmail was disabled in the app/Models/User.php path. Also in routes/web.php, Auth::routes(['verify' => true]); placing Auth::routes();. If you want to enable this service in the future, SMTP must be configured in the .env file.
#

## Laravel 11.x ready to start project

You may save your time to setup your project. You can start your project using this template where we have used Laravel 11.x and CoreUI out of the box Bootstrap.

## Laravel 11
As you may know, Laravel transitioned to yearly releases with the release of Laravel 10. Previously, major versions were released every 6 months. This transition is intended to ease the maintenance burden on the community and challenge our development team to ship amazing, powerful new features without introducing breaking changes. Therefore, we have shipped a variety of robust features to Laravel 9 without breaking backwards compatibility.

Therefore, this commitment to ship great new features during the current release will likely lead to future "major" releases being primarily used for "maintenance" tasks such as upgrading upstream dependencies, which can be seen in these release notes.

Laravel 11 continues the improvements made in Laravel 10.x by introducing argument and return types to all application skeleton methods, as well as all stub files used to generate classes throughout the framework. In addition, a new, developer-friendly abstraction layer has been introduced for starting and interacting with external processes. Further, Laravel Pennant has been introduced to provide a wonderful approach to managing your application's "feature flags".

## PHP 8.2.0 or greater.
Laravel 11.x requires a minimum PHP version of 8.2.0 or greater.

## curl 7.34.0 Required
Laravel's HTTP client now requires curl 7.34.0 or greater.


## Features

* User Authentication
* Role-Permissions for Users
* Bootstrap 5, CoreUI
* Landing Page
  * Tailwind


# User Guide

## Installation

Follow the steps mentioned below to install and run the project.

1. Clone or download the repository
2. Go to the project directory (cd laavel-coreui) and run `composer install` and `npm install`
    1. It will install all the laravel (PHP) packages by the command `composer install` (if you do not have `composer` then install it - https://getcomposer.org/download/)
    2. It will install all the NPM packages by the command `npm install` (if you do not have npm then install it - https://nodejs.org/en/download)
3. Create `.env` file by copying the `.env.example`. You may use the command to do that `cp .env.example .env`
4. Run the command `composer run-script post-create-project-cmd` to APP_KEY ## (optional)
5. Update the database name and credentials in `.env` file
6. Run the command `php artisan migrate`
7. Run the command `php artisan db:seed --class=UserSeeder` to create user, it will generate super admin `super@admin.com` and the password is `secret`
8. Link storage directory: `php artisan storage:link`
9. You may create a virtualhost entry to access the application or run `php artisan serve` an `npm run dev` from the project root and visit `http://127.0.0.1:8000`

OR

Using the Docker, you may run the project

1. docker-compose up

Important note: if you get broken page then run the command `npm run dev` or `npm run build`

# Screenshots
Login View
![login](https://github.com/bilaschandra/laravel-coreui/assets/5582015/5ca1d995-90be-4e02-b3ee-693fad45b588)

Dashboard View
![dashboard](https://github.com/bilaschandra/laravel-coreui/assets/5582015/9d233ac2-83e9-4668-8413-e6c150bc0b37)

Users View
![User-List-Laravel](https://github.com/bilaschandra/laravel-coreui/assets/5582015/a3088739-7771-4264-9378-9523dcbfae35)

Roles View
![Role-list-Laravel](https://github.com/bilaschandra/laravel-coreui/assets/5582015/2d1b52d2-63d0-40bd-b10a-5c07f2db169c)

Permissions View
![Permission-List-Laravel](https://github.com/bilaschandra/laravel-coreui/assets/5582015/a69a3a8a-956f-4fe2-8c53-0e642ba8099d)

## Release

### Laravel 10
    Tags
        v1.0-beta
        v1.0.1
### Laravel 11
    Tags
        v2.0.0


## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
# laravel-coreui
