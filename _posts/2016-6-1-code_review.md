---
layout: post
title: Understanding Code
---
After deciding the milestones and features required in the application, I had started exploring the code to get familiar with the code. For understanding the code, I explore the things used in code and get to know many things and I studied about different gems used in the application like "devise", "ActiveAdmin", "CanCanCan" gems. Lets discuss all these one by one:

* ActiveAdmin gem
* CanCanCan gem

1. **ActiveAdmin gem:**

ActiveAdmin is already used in the application for creating adminstration style interfaces. To set up Active Admin, add the gem in your Gemfile and run it:

gem 'activeadmin'

Then run $ bundle install

Run the generator to install Active Admin. This will create an AdminUser model, an initializer file for configuring Active Admin and an app/admin directory that will hold the administration files. It uses Devise for authentication. We can explore this gem from the documentation given below:

For more detail we can refer to http://activeadmin.info/docs/documentation.html

2. **CanCanCan gem:**

We need an authorization mechanism to define access rules for various users,for this we use CanCanCan, a flexible authorization solution for Rails. As our project have different users like superadmin, admin, volunteer and contributor and guest. All they have different access rights. So we need to define access rules for each one of them, so that they can access the functionality according to their rights. Their is a propoer hierarchy for this:

* Define the access rules in the ability.rb file in models.
* Check the rights in every controller using the  load_and_authorize_resource method defined in the every controller.
* Use the cancan helper in the view to cutomise according to rights. "can?" is the method to check if the current user has the permission to perform an action.

For more detail we can refer to https://github.com/CanCanCommunity/cancancan
