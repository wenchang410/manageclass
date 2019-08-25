## Larablog
#### A powerful open source Laravel Blog with WYSWYG and CRUD (Create Read Update Delete) built on [Laravel](http://laravel.com/) 5.8 and [Bootstrap](http://getbootstrap.com) 4

[![Build Status](https://travis-ci.org/jeremykenedy/larablog.svg?branch=master)](https://travis-ci.org/jeremykenedy/larablog)
[![StyleCI](https://github.styleci.io/repos/40459558/shield?branch=master)](https://github.styleci.io/repos/40459558)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/jeremykenedy/larablog/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/jeremykenedy/larablog/?branch=master)
[![Code Intelligence Status](https://scrutinizer-ci.com/g/jeremykenedy/larablog/badges/code-intelligence.svg?b=master)](https://scrutinizer-ci.com/code-intelligence)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

#### Table of contents
- [Features](#features)
- [Installation Instructions](#installation-instructions)
    - [Build the Front End Assets with Mix](#build-front-end-assets-with-mix)
- [Seeds](#seeds)
    - [Seeded Roles](#seeded-roles)
    - [Seeded Permissions](#seeded-permissions)
    - [Seeded Users](#seeded-users)
    - [Themes Seed List](#themes-seed-list)
- [Commands](#commands)
    - [Generate Site Map](#generate-site-map)
- [Configs](#configs)
    - [Config File](#config-file)
    - [Env Variables](#env-variables)
    - [Language Files](#language-files)
- [Routes](#routes)
- [Screenshots](#screenshots)
- [File Tree](#file-tree)
- [Opening an Issue](#opening-an-issue)
- [License](#license)


#### Build the Front End Assets with Mix
##### Using NPM:
1. From the projects root folder run `npm install`
2. From the projects root folder run `npm run dev` or `npm run production`
  * You can watch assets with `npm run watch`

##### Using Yarn:
1. From the projects root folder run `yarn install`
2. From the projects root folder run `yarn run dev` or `yarn run production`
  * You can watch assets with `yarn run watch`

###### And thats it with the caveat of setting up and configuring your development environment. I recommend [Laravel Homestead](https://laravel.com/docs/5.8/homestead)

### Seeds
* [DatabaseSeeder.php](https://github.com/jeremykenedy/larablog/blob/master/database/seeds/DatabaseSeeder.php)
* [PermissionsTableSeeder.php](https://github.com/jeremykenedy/larablog/blob/master/database/seeds/PermissionsTableSeeder.php)
* [RolesTableSeeder.php](https://github.com/jeremykenedy/larablog/blob/master/database/seeds/RolesTableSeeder.php)
* [ConnectRelationshipsSeeder.php](https://github.com/jeremykenedy/larablog/blob/master/database/seeds/ConnectRelationshipsSeeder.php)
* [UsersTableSeeder.php](https://github.com/jeremykenedy/larablog/blob/master/database/seeds/UsersTableSeeder.php)
* [TagTableSeeder.php](https://github.com/jeremykenedy/larablog/blob/master/database/seeds/TagTableSeeder.php)
* [PostTableSeeder.php](https://github.com/jeremykenedy/larablog/blob/master/database/seeds/PostTableSeeder.php)

##### Seeded Roles
| Role | Level |
| :------------ | :------------ |
|Unverified|Level 0|
|User|Level 1|
|Writer|Level 2|
|Moderator|Level 3|
|Admin|Level 4|
|Super Admin|Level 5|

##### Seeded Permissions
  * view.users
  * create.users
  * edit.users
  * delete.users
  * perms.super-admin
  * perms.admin
  * perms.moderator
  * perms.writer
  * perms.user

##### Seeded Users
|Email|Password|Access|
|:------------|:------------|:------------|
|admin@admin.com|password|Super Admin Access|

* Controlled by the `.env` file.

##### Themes Seed List
  * [ThemesTableSeeder](https://github.com/jeremykenedy/larablog/blob/master/database/seeds/ThemesTableSeeder.php)

### Commands
#### Generate Site Map
* You can generate a XML sitemap which is located at `/sitemap.xml` with the following Artisan Command:

`php artisan sitemap:generate` or `php artisan sitemap:generate {limit}`

`{limit}` is the number of pages that the sitemap generator will limit to generating.

* The sitemaps default number of pages is controlled by the `.env` variable `BLOG_SITEMAP_LIMIT`


### Configs
#### Config File
Here is a list of the custom config files that have been added or modified to the project:
* [blog.php](https://github.com/jeremykenedy/larablog/blob/master/config/blog.php)
* [admin.php](https://github.com/jeremykenedy/larablog/blob/master/config/admin.php)
* [laravel-logger.php](https://github.com/jeremykenedy/larablog/blob/master/config/laravel-logger.php)
* [laravelPhpInfo.php](https://github.com/jeremykenedy/larablog/blob/master/config/laravelPhpInfo.php)
* [laravelusers.php](https://github.com/jeremykenedy/larablog/blob/master/config/laravelusers.php)
* [roles.php](https://github.com/jeremykenedy/larablog/blob/master/config/roles.php)
* [superadmin.php](https://github.com/jeremykenedy/larablog/blob/master/config/superadmin.php)
* [sitemap.php](https://github.com/jeremykenedy/larablog/blob/master/config/sitemap.php)
* [filesystems.php](https://github.com/jeremykenedy/larablog/blob/master/config/filesystems.php)


### File Tree

```
Larablog
├── .editorconfig
├── .env.example
├── .env.travis
├── .gitattributes
├── .gitignore
├── .travis.yml
├── LICENSE
├── README.md
├── app
│   ├── Console
│   │   ├── Commands
│   │   │   └── GenerateSitemap.php
│   │   └── Kernel.php
│   ├── Exceptions
│   │   └── Handler.php
│   ├── Handlers
│   │   └── LfmConfigHandler.php
│   ├── Http
│   │   ├── Controllers
│   │   │   ├── Admin
│   │   │   │   ├── AdminController.php
│   │   │   │   ├── PostController.php
│   │   │   │   ├── TagController.php
│   │   │   │   └── ThemesManagementController.php
│   │   │   ├── Api
│   │   │   │   └── BlogController.php
│   │   │   ├── Auth
│   │   │   │   ├── ForgotPasswordController.php
│   │   │   │   ├── LoginController.php
│   │   │   │   ├── RegisterController.php
│   │   │   │   ├── ResetPasswordController.php
│   │   │   │   └── VerificationController.php
│   │   │   ├── BlogController.php
│   │   │   ├── ContactController.php
│   │   │   ├── Controller.php
│   │   │   └── HomeController.php
│   │   ├── Kernel.php
│   │   ├── Middleware
│   │   │   ├── Authenticate.php
│   │   │   ├── CheckForMaintenanceMode.php
│   │   │   ├── EncryptCookies.php
│   │   │   ├── RedirectIfAuthenticated.php
│   │   │   ├── TrimStrings.php
│   │   │   ├── TrustProxies.php
│   │   │   └── VerifyCsrfToken.php
│   │   ├── Requests
│   │   │   ├── ContactRequest.php
│   │   │   ├── DeleteThemeRequest.php
│   │   │   ├── DestroyPostRequest.php
│   │   │   ├── DestroyTagRequest.php
│   │   │   ├── GenerateSitemapRequest.php
│   │   │   ├── StorePostRequest.php
│   │   │   ├── StoreTagRequest.php
│   │   │   ├── StoreThemeRequest.php
│   │   │   ├── ThemeRequest.php
│   │   │   ├── UpdatePostRequest.php
│   │   │   ├── UpdateTagRequest.php
│   │   │   └── UpdateThemeRequest.php
│   │   └── ViewComposers
│   │       └── BlogSettingsComposer.php
│   ├── Logic
│   │   └── helpers.php
│   ├── Mail
│   │   └── ContactMail.php
│   ├── Models
│   │   ├── BlogSetting.php
│   │   ├── Post.php
│   │   ├── Tag.php
│   │   ├── Theme.php
│   │   └── User.php
│   ├── Providers
│   │   ├── AppServiceProvider.php
│   │   ├── AuthServiceProvider.php
│   │   ├── BroadcastServiceProvider.php
│   │   ├── ComposerServiceProvider.php
│   │   ├── EventServiceProvider.php
│   │   └── RouteServiceProvider.php
│   ├── Services
│   │   ├── BlogThemeServices.php
│   │   ├── Markdowner.php
│   │   ├── PostAuthors.php
│   │   ├── PostFormFields.php
│   │   ├── PostProcesses.php
│   │   ├── PostTemplates.php
│   │   ├── SitemapCrawlProfile.php
│   │   └── TagFormFields.php
│   └── Traits
│       └── CaptchaTrait.php
├── artisan
├── bootstrap
│   ├── app.php
│   └── cache
│       ├── .gitignore
│       ├── packages.php
│       └── services.php
├── composer.json
├── composer.lock
├── config
│   ├── admin.php
│   ├── app.php
│   ├── auth.php
│   ├── blog.php
│   ├── broadcasting.php
│   ├── cache.php
│   ├── database.php
│   ├── debug-server.php
│   ├── debugbar.php
│   ├── feed.php
│   ├── filesystems.php
│   ├── hashing.php
│   ├── image.php
│   ├── laravel-logger.php
│   ├── laravelPhpInfo.php
│   ├── laravelusers.php
│   ├── lfm.php
│   ├── logging.php
│   ├── mail.php
│   ├── queue.php
│   ├── roles.php
│   ├── services.php
│   ├── session.php
│   ├── sitemap.php
│   ├── superadmin.php
│   ├── tinker.php
│   ├── trustedproxy.php
│   └── view.php
├── database
│   ├── .gitignore
│   ├── factories
│   │   ├── PostFactory.php
│   │   ├── TagFactory.php
│   │   └── UserFactory.php
│   ├── migrations
│   │   ├── 2014_10_12_000000_create_users_table.php
│   │   ├── 2014_10_12_100000_create_password_resets_table.php
│   │   ├── 2016_01_15_105324_create_roles_table.php
│   │   ├── 2016_01_15_114412_create_role_user_table.php
│   │   ├── 2016_01_26_115212_create_permissions_table.php
│   │   ├── 2016_01_26_115523_create_permission_role_table.php
│   │   ├── 2016_02_09_132439_create_permission_user_table.php
│   │   ├── 2018_10_10_070913_create_posts_table.php
│   │   ├── 2018_10_10_070928_create_tags_table.php
│   │   ├── 2018_10_10_070949_create_post_tag_pivot_table.php
│   │   ├── 2018_10_28_070857_create_themes_table.php
│   │   └── 2018_10_29_042545_create_blog_settings_table.php
│   └── seeds
│       ├── BlogSettingsTableSeeder.php
│       ├── ConnectRelationshipsSeeder.php
│       ├── DatabaseSeeder.php
│       ├── PermissionsTableSeeder.php
│       ├── PostTableSeeder.php
│       ├── RolesTableSeeder.php
│       ├── TagTableSeeder.php
│       ├── ThemesTableSeeder.php
│       └── UsersTableSeeder.php
├── package.json
├── phpunit.xml
├── public
│   ├── .htaccess
│   ├── css
│   │   ├── admin.css
│   │   ├── app.css
│   │   └── bs3-modals.css
│   ├── favicon.ico
│   ├── fonts
│   │   ├── font-awesome
│   │   │   ├── fa-brands-400.eot
│   │   │   ├── fa-brands-400.svg
│   │   │   ├── fa-brands-400.ttf
│   │   │   ├── fa-brands-400.woff
│   │   │   ├── fa-brands-400.woff2
│   │   │   ├── fa-regular-400.eot
│   │   │   ├── fa-regular-400.svg
│   │   │   ├── fa-regular-400.ttf
│   │   │   ├── fa-regular-400.woff
│   │   │   ├── fa-regular-400.woff2
│   │   │   ├── fa-solid-900.eot
│   │   │   ├── fa-solid-900.svg
│   │   │   ├── fa-solid-900.ttf
│   │   │   ├── fa-solid-900.woff
│   │   │   └── fa-solid-900.woff2
│   │   └── nucleo
│   │       ├── nucleo-icons.eot
│   │       ├── nucleo-icons.ttf
│   │       ├── nucleo-icons.woff
│   │       └── nucleo-icons.woff2
│   ├── images
│   ├── index.php
│   ├── js
│   │   ├── admin.js
│   │   ├── app.js
│   │   └── jquery.dataTables.min.js
│   ├── mix-manifest.json
│   ├── photos
│   │   ├── 1
│   │   └── shares
│   ├── robots.txt
│   ├── sitemap.xml
│   └── svg
│       ├── 403.svg
│       ├── 404.svg
│       ├── 500.svg
│       └── 503.svg
├── resources
│   ├── admin
│   │   ├── js
│   │   │   ├── admin.js
│   │   │   ├── bootstrap.js
│   │   │   ├── bs-tooltips.js
│   │   │   └── set-ckeditor.js
│   │   └── sass
│   │       ├── _dropzone.scss
│   │       ├── _fab.scss
│   │       ├── _forms.scss
│   │       ├── _mixins.scss
│   │       ├── _nucleo-icons.scss
│   │       ├── _tables.scss
│   │       ├── _variables.scss
│   │       └── admin.scss
│   ├── js
│   │   ├── app.js
│   │   ├── bootstrap.js
│   │   └── components
│   │       └── ExampleComponent.vue
│   ├── lang
│   │   └── en
│   │       ├── admin.php
│   │       ├── auth.php
│   │       ├── emails.php
│   │       ├── forms.php
│   │       ├── larablog.php
│   │       ├── messages.php
│   │       ├── modals.php
│   │       ├── pagination.php
│   │       ├── passwords.php
│   │       ├── themes.php
│   │       ├── tooltips.php
│   │       └── validation.php
│   ├── sass
│   │   ├── _variables.scss
│   │   ├── app.scss
│   │   └── partials
│   │       └── _bs-visibility-classes.scss
│   └── views
│       ├── admin
│       │   ├── forms
│       │   │   └── generate-sitemap.blade.php
│       │   ├── modals
│       │   │   ├── delete-modal.blade.php
│       │   │   ├── delete-post-modal-form.blade.php
│       │   │   ├── delete-tag-modal-form.blade.php
│       │   │   ├── save-modal.blade.php
│       │   │   ├── save-post-modal-form.blade.php
│       │   │   └── upload-modal.blade.php
│       │   ├── pages
│       │   │   ├── home.blade.php
│       │   │   ├── sitemap.blade.php
│       │   │   └── uploads.blade.php
│       │   ├── partials
│       │   │   ├── drawer-nav.blade.php
│       │   │   ├── footer.blade.php
│       │   │   ├── loading-file-1.blade.php
│       │   │   ├── loading-spinner-1.blade.php
│       │   │   ├── messages.blade.php
│       │   │   ├── navbar.blade.php
│       │   │   └── sidebar.blade.php
│       │   ├── post
│       │   │   ├── create.blade.php
│       │   │   ├── edit.blade.php
│       │   │   ├── index.blade.php
│       │   │   └── partials
│       │   │       └── post-form.blade.php
│       │   ├── scripts
│       │   │   ├── delete-modal-script.blade.php
│       │   │   ├── post-form-scripts.blade.php
│       │   │   ├── save-modal-script.blade.php
│       │   │   ├── save-post-modal.blade.php
│       │   │   └── toggle-status.blade.php
│       │   ├── tag
│       │   │   ├── create.blade.php
│       │   │   ├── edit.blade.php
│       │   │   ├── index.blade.php
│       │   │   └── partials
│       │   │       └── tag-form.blade.php
│       │   └── themesmanagement
│       │       ├── create-theme.blade.php
│       │       ├── edit-theme.blade.php
│       │       ├── index.blade.php
│       │       ├── partials
│       │       │   ├── default-theme-form.blade.php
│       │       │   └── theme-table-list.blade.php
│       │       └── show-theme.blade.php
│       ├── auth
│       │   ├── login.blade.php
│       │   ├── passwords
│       │   │   ├── email.blade.php
│       │   │   └── reset.blade.php
│       │   ├── register.blade.php
│       │   └── verify.blade.php
│       ├── blog
│       │   ├── forms
│       │   │   └── contact-form.blade.php
│       │   ├── pages
│       │   │   ├── author.blade.php
│       │   │   ├── authors.blade.php
│       │   │   └── contact.blade.php
│       │   ├── partials
│       │   │   ├── analytics.blade.php
│       │   │   ├── disqus.blade.php
│       │   │   ├── disqusjs.blade.php
│       │   │   ├── footer.blade.php
│       │   │   ├── header-post.blade.php
│       │   │   ├── header.blade.php
│       │   │   ├── messages.blade.php
│       │   │   ├── nav.blade.php
│       │   │   ├── posts-pager.blade.php
│       │   │   ├── posts-roll.blade.php
│       │   │   └── social-media.blade.php
│       │   ├── post-layouts
│       │   │   └── standard.blade.php
│       │   └── roll-layouts
│       │       └── home.blade.php
│       ├── layouts
│       │   ├── admin.blade.php
│       │   ├── app.blade.php
│       │   └── auth.blade.php
│       └── mail
│           └── contact.blade.php
├── routes
│   ├── api.php
│   ├── channels.php
│   ├── console.php
│   └── web.php
├── server.php
├── tests
│   ├── CreatesApplication.php
│   ├── Feature
│   │   ├── ExampleTest.php
│   │   ├── MarkdownerTest.php
│   │   └── PostsTest.php
│   ├── TestCase.php
│   └── Unit
│       └── ExampleTest.php
├── webpack.mix.js
├── yarn-error.log
└── yarn.lock
```
* Tree command can be installed using brew: `brew install tree`
* File tree generated using command `tree -a -I '.git|node_modules|vendor|storage|ckeditor'`
"# class" 
