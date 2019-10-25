## Description

A **Simple Blog** is full ASP.NET MVC application that supports users, roles, posts and tags. Application covers most important features of ASP.NET MVC: routing, areas, asset bundling, controllers, the Razor view engine, data binding and validation. Data is being handled using the mature and very powerful nHibernate OR/M to access database; and the Fluent Migrator database migration framework to version database schema in source control. Covered are also security issues - from CSRF and XSS attacks, to making sure errors aren’t displayed to customers. User interface is implemented using both jQuery and Bootstrap 3.

## Prerequisites:

- Working knowledge of C# and Visual Studio
- Visual Studio 2012 or above (including free express/community editions)
- MySQL and MySQL Workbench (free software from mysql.com)

## Installation

- create an empty database in MySql server (DB name: "simpleblog")
- configure *connection_string* in *web.config* file of application
- create a database schema - run migration script (*SimpleBlog/Tools/DeployDb-Dev.bat*)
- enter the role with the name **admin** in the *roles* table (through MySQL Workbench)
- steps to enter first(*admin*) user to database:
  1. comment the `[Authorize(Roles = "admin")]` attribute of *UsersController* class under *Admin* area
  2. rebuild, run the application and go to */admin/users* path
  3. click on *Create user*, fill the form data, be sure to check *admin* role
  4. uncomment the `[Authorize(Roles = "admin")]` attribute of *UsersController* class under *Admin* area
- use the application

## Usage

**Simple Blog** application covers typical blog engine functionality. This functionality can be divided into two sections:

- frontend usage
- backend usage

**Frontend:**
Homepage displays list of paginated posts, ordered by creation date. Clicking on certain post title, opens posts page. On a sidebar are displayed tag names, and number that shows how many times have certain tag been used in blog posts. Tag field is at the same time a progress bar that presents percentage of tag usage. Clicking on a tag will render posts that are tagged with clicked tag.

**Backend:**
User can login to application going to **/login** page. 
When user with **admin** role logs in, an option for *Posts management* becomes available on the sidebar. Clicking on this option gets user to the admin area of Simple Blog application, where user (*admin*) can manage both *posts* and *users*. 
User can logout going to the **/logout** page.

