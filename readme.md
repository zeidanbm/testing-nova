# Testing Nova
This project is to show examples of my approach to testing Nova. This app is TDD, so all functionality _should_ have a corresponding test. Tests are broken up into the the Feature directory under Nova and by model from there.

There is also an API that was utilized for front end access, so the example code of how I went about that is also in this project.


## Project Overview
This is an app I made for a customer that required a dropbox style application with some custom fucntionality. Some of functionality has been scrubbed due to proprietary processes, as well as code being stripped due to premium themese, etc. What is left is a Nova code base focusing on:

* Projects, they can have:
  * Files and Email Addresses
* Email Addresses have an action to be notified they have access to a project
* Email Addresses can receive an email with a signed URL
* Signed URLs can be used to see and download files
* Email Addresses can upload files back to the UI

Nova has administration screens for each model, actions, and relationships described above.

## Setup
1. Clone the repo
2. Run `cp .env.example .env`
2. Drop Nova into the project root at /nova (tested up to Nova release 1.0.12)
3. Run `composer install`
4. Run `php artisan key:generate`
5. Run `php artisan nova:install`
6. Run `vendor/phpunit/phpunit/phpunit` from this directory

Homestead is installed per project here and can be run to view the UI if desired.
1. [Follow these instructions](https://laravel.com/docs/5.7/homestead#per-project-installation)
2. Run `vagrant up`

There is also one Dusk test to test the one front end interface.
1. Follow the Homestead instructions above, and make sure vagrant is running
2. Update `.env` with your database connection
3. Run `php artisan dusk`

Seeds are available in this repo to get you going
1. Run `php artisan migrate:refresh --seed`

The default Nova login generated by the seeder is:

  U: `youremail@address.com`
  P: `Af2URF2oCp`
