# Intro to Laravel

Hey there! Let's dive into http://laravel.com, a PHP Framework for Web Artisans.

We've setup a blank installation of laravel for you here, feel free to dive in after learning a bit below and adding a new page.

Laravel provides a great [Quick Start](https://laravel.com/docs/5.1/quickstart) guide that covers many additional pieces of the Framework.

## Installation

To setup this blank Laravel installation, you'll need to setup your `.env variables`. Use the `.env.example` template file for the basic setup. These are found in the laravel folder.

1) Install project dependencies. Navigate to the directory of the project.

```bash
php composer.phar install

OR

composer install
```

2) Generate a Laravel Key
```bash
php artisan key:generate
```

3) Start up docker containers
```bash
docker-compose up -d
```

4) Migrate and create the database
```bash
php artisan migrate
```

**Practice Learning Laravel:** Pull the repo, navigate to the director of this project, (Learn Laravel) and run `docker-compose up -d` and access Laravel at `localhost:8080` in your browser.

## Folder Structure

Let's call your root directory `my-project` (our root folder for this project is titled `laravel`) - replace this name with whatever your project folder is titled.

Inside this folder is a `laravel` folder which houses everything the app should need. Anything not in the `laravel` folder is typically required for the server. We'll leave these alone for now. These items can be learned about in our `Learn Docker` section.

Inside `laravel`, you'll notice a bunch of different folders. Let's discuss them here:

- `/app` - Contains our `Controllers, Models, and Middleware`. We'll discuss these in depth later.
- `/bootstrap` - this is NOT the [Bootstrap](http://getbootstrap.com) JS/CSS Framework. Instead, this is where laravel pulls in various files to run.
- `/config` - We can declare app variables and other configuration items here.
- `/database` - This folder houses our migrations and seeds.
- `/public` - This is where public front-end files are housed such as js and css, pictures, files, etc.
- `/resources` - Along with some files Laravel needs, we find the `views` folder here which is where our pages are located.
- `/routes` - The `web` file is particularly important here as it tells Laravel where to route traffic. More on this below.
- `/storage` - Here we can store files for recall later such as a profile picture. `Logs` are also stored here.
- `/tests` - unit tests and functional tests, [more info here](https://laravel.com/docs/5.8/testing).
- `/vendor` - Laravel files and other dependencies are stored here. 3rd party dependencies can be installed at anytime. The vendor folder contains non-versioned control files.
- Most of the folders for simplicity sake you can ignore for now. The two you'll want to pay special attention to are `public` and `resources/views`

## MVC

Laravel is an MVC (model, view, controller) framework. The model declares something, the controller says what to do with it, and the view is the output (pages).

### Views

Views are the actual pages. They are called `blade` files - these are basically php files with a few extra perks which we'll dive into more elsewhere. - `.php` files allow you to run normal html and php in the same file, so we only ever use php files.

If you don't declare a page in the `/routes/web` file, the page won't be accessible. A typical page declaration looks like this:

```php
Route::get('/blog', function () {
    return view('blog');
});
```

The above says - if someone goes to the route `/blog` (eg: mysite.com/blog) then find the `/blog` page in the `views` folder and return that page.

### Models

Models define a database and what's accessible from that database. We'll cover this more later.

### Controllers

Controllers tell Laravel what to do, they are they blueprints for your commands. They can simply return a page or they can be used to create, edit, or delete records. We'll explore this more later.

## Layouts

In laravel, you can reuse code (actually, you can do that in php using what's called an `include`) - laravel just makes it look much nicer.

Layouts are housed in the `view/layouts` folder.

In many projects, there is an `@extends('layouts.app')` line of code. This creates a dynamic template that returns the current file referenced in extends based on the view the user is on.

In the layout file, you'll see a `@yield('content')` line, that says, input the section's content here. An example, our layout has the dependencies at the top, the nav, then asks for the pages content to be inserted in the middle of all that, then the footer underneath. Layouts makes it really simple to reuse code easily.

## Conclusion

Sweet! So now you know where the pages are, where the assets are, and how to link a page in laravel if needed. That's laravel at its most basic level.
