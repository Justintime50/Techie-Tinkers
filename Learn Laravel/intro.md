# Intro

Hey there! Let's dive into http://laravel.com, a PHP Framework for Web Artisans.

Let's call your root directory `client` (replace this name with whatever your project folder is titled.) 

Inside this folder is a `laravel` folder which is basically everything you'll need. Anything not in the `laravel` folder is typically required for the server. We'll leave these alone for now.

Inside `laravel`, you'll notice a bunch of different folders. Let's discuss them here:

- `bootstrap` folder - this is NOT the Bootstrap JS/CSS Framework that can be found at http://getbootstrap.com.
- Most of the folders for simplicity sake you can ignore for now. The two you'll want to pay special attention to are `public` and `resources/views`
- The `public` folder is where all the assets go. (css, pictures, js, etc.) Sass files that compile into CSS files are stored here. You'll open the `scss` folder in the `public` folder (make sure it's in public, laravel has it's own sass files in other folders.) The sass files here compile into css files in the css folder.
- Then, in the `resources/views` folder, that's where you'll find all the actual pages. They are called `blade` files - these are basically php files with a few extra perks (don't worry about it for now) - as I'm sure you know, .php files allow you to run normal html and php in the same file, so we only ever use php files.

## MVC

Laravel is an MVC (model, view, controller) framework. The model declares something, the controller says what to do with it, and the view is the output (pages).

SO, we won't go over the M or the C part yet, but if you don't declare a page in the `web` file, the page won't be accessible.

So a typical page declaration looks like this:

```
Route::get('/for-sale', function () {
    return view('for-sale');
});
```

The above says - if someone goes to the route `/for-sale` (eg: mysite.com/for-sale) then find the `/for-sale` page in the `views` folder.

Sweet! So now you know where the pages are, where the assets are, and how to link a page in laravel if needed. That's laravel at its most basic level.

## Layouts

In laravel, you can reuse code (actually, you can do that in php using what's called an `include`) - laravel just makes it look much nicer.

Layouts are housed in the `view/layouts` folder.

In many projects, there is an `@extends('layouts.app')` line of code. This says, input the referenced file at the here.

In the layout file, you'll see a `@yield('content')` line, that says, input the section's content here. An example, our layout has the dependencies at the top, the nav, then asks for the pages content to be inserted in the middle of all that, then the footer underneath. Layouts makes it really simple to reuse code easily.

##

There you have it! Let's move on to the next section.
