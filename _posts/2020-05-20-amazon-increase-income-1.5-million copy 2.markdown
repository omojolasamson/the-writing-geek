---
layout: post
title:  ARTICLE - Coping With Stress at Workk
excerpt: Everyone who has ever held a job has, at some point, felt the pressure of work-related stress. Any job can have stressful elements, even if you love what you do. 
date:   2020-05-20 15:05:55 +0300
image:  post-5.jpg
---

<!---author: uixgeek
tags:   UX design
---
![post-thumb]({{site.baseurl}}/assets/images/blog/post-1.jpg){:class="img-fluid rounded float-left mr-5 mb-4"}-->

Tips for Upgrading Laravel Versions In Existing Apps

Introduction 

There are a lot of benefits to keeping your apps updated and constantly upgrading to the most recent version of the stacks they utilize. It prevents vulnerabilities, enhances usability, and the most recent releases usually unlock a plethora of bug fixes and new features. So even if your app can still function properly with old code, whenever you can, it’s usually best to perform an upgrade.
  
In this article, I’ll be sharing with you tips on how to upgrade earlier Laravel versions to more recent releases in your existing apps. 

What the Latest Version Offers

For a long time, Laravel has been one of (if not) the most popular open-source PHP frameworks. It is flexible, scalable, and adaptive, and it has become the top-shelf choice for engineers and businesses working with PHP. The latest version of Laravel (Laravel 9) was made available in February 2022, and the next future release (Laravel 10) will come in February 2023. Laravel 9 comes with a number of new and interesting features. Some of the notable ones are:

Symfony Mailer - Swift Mailer was used by earlier versions of Laravel to send outgoing emails. However, Symfony Mailer has been used to replace it since Swift Mailer is no longer maintained. Symfony Mailer is now used to enable email sending on Laravel apps via SMTP, Postmark, Mailgun, Amazon SES, and sendmail.

If the application that you are trying to upgrade uses Swift Mailer, you may need to install some mailgun driver prerequisites, and rename some Swift methods to Symphony methods.

Flysystem 3. x –: In Laravel apps, files are manipulated with the help of the Storage facade. And the Storage facade's whole filesystem interface is powered by Flysystem. In version 9, Laravel’s upstream Flysystem dependency has been upgraded from Flysystem 1.x to Flysystem 3.x. 

Improved Eloquent Accessors/Mutators -: In laravel 9, by type-hinting a return type of `Illuminate\Database\Eloquent\Casts\Attribute`, you can define an accessor and a mutator using one, non-prefixed method, as opposed to earlier versions where you had to define multiple prefixed methods. This makes getting and setting attributes a lot easier.

Implicit Route Bindings with enum -: Enums were finally introduced in PHP 8.1. Laravel 9, which uses PHP 8.1, supports using Enums in your route definitions. When Enums are used on a route, the route will be invoked only if its URL has a valid Enum value. If not, the route will return a 404 response.

Controller Route Group -: Laravel 9’s Route::controller() method can be used to define a common controller for every route within a route group.

Full Text Indexes/Where Clauses -: To generate full text indexes for MySQL or PostgreSQL database colums, the fullText method can be added to the definition.


    $table->text('post')->fullText();

You can use the `whereFullText` and `orWhereFullText` methods to add “where” clauses to queries for fullText columns. When you run your app, Laravel will transform them into the proper SQL for your chosen database system. 

Laravel Scout Database Engine -: If your application doesn’t deal with a huge load of data, Laravel’s Scout database engine should suffice for search features and serve as an alternative to dedicated search services like Algollia and MeiliSearch. 

Rendering inline Blade Templates -: the `Blade` facade’s render method can be used to generate valid HTML from a raw Blade template string. 


    use Illuminate\Support\Facades\Blade;
     
    return Blade::render('My name is {{ $name }}', ['name' => 'Samson Omojola']);

Above, we have Blade’s `render` method taking a Blade template string with which it will generate a corresponding HTML.

Blade’s `renderComponent` method can be used to render a class component. The method will render any component instance that’s passed into it.


    use App\View\Components\NameComponent;
     
    return Blade::renderComponent(new NameComponent('Samson Omojola'));

Slot Name Shortcut -: In laravel 9, you can now specify a slot’s name without using the `name` attribute. 

Before:

        <x-slot name="options">
            <a>display</a>
            <a>hide</a>
        </x-slot>

Now:

    <x-slot:options>
       <a>display</a>
       <a>hide</a>
    </x-slot>

Laravel Breeze API & Next.js -: The laravel Breeze starter now has an API scaffolding mode and a complimentary Next.js frontend. This starter kit will enable you build Laravel applications that serve as a backend for a JavaScript frontend, using Laravel Sanctum authentication 

New Helpers -: two new helper functions have been introduced with Laravel 9,  `str` and `to_route`. The former returns a `Illuminate\Support\Stringable` instance for any string it’s given, while the latter helps you redirect to a named route from your controllers and routes.


Manually Upgrading to Laravel 9

Step 1
Before upgrading an application to Laravel 9, it is advisable to back up your existing code and the composer.json file. This can be done by simply creating a repository on GitHub and uploading your code to it. 

Step 2 
Changing PHP Version
Laravel 9 requires a minimum PHP version of 8.0 due to it’s dependence on Symfony’s most recent version (v6.0), which depends on PHP 8.

Navigate to your composer.json file and change your PHP version to 8.


    "require": {
        "php": "^8.0",
    }

Step 3
Updating Depedencies
In your composer.json file replace the following packages with their updated versions:


    “laravel/framework” : “^9.0”, 
    “nunomaduro/collision”: “^6.1”, 
    “spatie/laravel-ignition”: “1.0” 

Then run `composer update` to update the dependencies. 

After composer performs an update, some of your third-party packages might throw errors, since they do not support Laravel 9. They’ll need to be updated to versions that do.

For example, say you see an error like this:


    spatie/laravel-backup requires illuminate/support ~6.0|~7.0|~8.0 -> satisfiable by illuminate/support[v6.0.0, ..., v6.20.16, v7.0.0, ..., v7.30.4, v8.0.0, ..., v8.28.1].
    - Only one of these can be installed: illuminate/support[v4.0.0, ..., v4.2.17, v5.0.0, ..., v5.8.36, v6.0.0, ..., v6.20.16, v7.0.0, ..., v7.30.4, v8.0.0, ..., v8.28.1], laravel/framework[v9.0.-beta.1]. laravel/framework replaces illuminate/support and thus cannot coexist with it.
    - Root composer.json requires laracasts/generators dev-master as 1.1.4 -> satisfiable by laracasts/generators[dev-master].


You’ll need to navigate to the GitHub page or official website of spatie/laravel-backup and check if its latest version supports Laravel 9. If it does, then go to your composer.json and change the package’s version to the latest version.

After updating all the outdated third-party packages, run `composer update` again.

If you get any syntax error, go to Laravel’s official upgrade guide page and search for the necessary update relating to that error.


USING LARAVEL SHIFT TO UPGRADE YOUR LARAVEL VERSION 

Shift is an automated (paid) tool that can be used to automatically upgrade applications with older versions of Laravel to later versions.

To use Shift, navigate to https://laravelshift.com in your browser.


![](https://paper-attachments.dropbox.com/s_224901DE828DC09096687E31B4752CEF1A5208F9AD8C4B14BE5C541C6C3008CF_1657665773733_Screenshot+49.png)


On the homepage, click on the Run Shift button at the top right side of the page.

You should see a list of the different kinds of upgrades that can be done and their corresponding prices. Decide which one you want and click the purchase option on it.


![](https://paper-attachments.dropbox.com/s_224901DE828DC09096687E31B4752CEF1A5208F9AD8C4B14BE5C541C6C3008CF_1657665890811_Screenshot+50.png)


Next, select the option to sign in with your GitHub account and give Shift access to your repositories by clicking on ‘Authorize laravel-shift’. 


![](https://paper-attachments.dropbox.com/s_224901DE828DC09096687E31B4752CEF1A5208F9AD8C4B14BE5C541C6C3008CF_1657665980199_Screenshot+51.png)

![](https://paper-attachments.dropbox.com/s_224901DE828DC09096687E31B4752CEF1A5208F9AD8C4B14BE5C541C6C3008CF_1657666068072_Screenshot+52.png)


On the next page, under Connection, ensure that the GitHub repo attached is your GitHub repo. Under REPOSITORY OR CLONE URL, enter the link to the specific repository you want to upgrade. Under Branch, enter the branch of the repository you want upgraded (e.g. main).


![](https://paper-attachments.dropbox.com/s_224901DE828DC09096687E31B4752CEF1A5208F9AD8C4B14BE5C541C6C3008CF_1657666165859_Screenshot+54.png)


With the above information, Laravel Shift will create a pull request to that branch with the required changes for an upgrade. You can review the changes manually and decide what to accept. Next, click on "Checkout and run". On the next page, your credit card details will be requested. Enter your details and click on Purchase Shift.


![](https://paper-attachments.dropbox.com/s_224901DE828DC09096687E31B4752CEF1A5208F9AD8C4B14BE5C541C6C3008CF_1657666259366_Screenshot+55.png)


After making the purchase, you’ll be directed to a page that will show you the status of your request. 

You should see the "Running" status for some seconds, indicating that Shift is upgrading your application. When it's complete, the Running status will change to a link to the pull request Shift created for you. Click on it. Under the ‘Files changed’ tab, you’ll see the updates Shift made.

A downside of Shift is that it might be considered too expensive by some. It may also be considered slow, as, if you are upgrading from a very old version to the latest version, Shift doesn’t do one single upgrade. It proceeds step by step. e.g. from v7 to v9, Shift upgrades first to v8, and then to v9. However, if you consider the amount of effort it saves you, you may find that it’s worth it.


Conclusion 

You made it to the end of the post! We covered the new features the latest version of Laravel ships with, tips for manually upgrading the Laravel version of your existing application, and a tool (Laravel Shift) that automates the process for you.
For more info on upgrading Laravel versions, you can check out the official documentation.
