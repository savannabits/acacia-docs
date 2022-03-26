# Installation 

---
- [Requirements](#requirements)
- [Before Installation](#before-installation)
- [Installation](#installation)
- [Configuration](#configuration)
  
<a name='requirements'></a>
## Requirements
### PHP 8.x
Acacia requires php 8.0 or higher to run 
### PHP Sqlite3 extension (`php8.0-sqlite3` or `php8.1-sqlite3`)
Acacia generates code by first generating Schematic blueprints from the table. These are stored in an sqlite database, which requires the sqlite3 php extension.
You can install the extension easily by running one of the following commands:
```bash
sudo apt install php8.0-sqlite3 #for php 8.0
sudo apt install php8.1-sqlite3 #for php 8.1
```
### Laravel 9.x
Acacia runs on the latest Laravel, 9.0 or higher.
### Laravel Breeze
Required as the authentication library.
### Laravel Scout
Required for creating a search index on models which is used in filtering datatables
### Laravel Sanctum
Required as the authentication library
### Laravel Permission
Required for RBAC
### Node and npm/yarn
Required for building frontend assets

<a name='before-installation'></a>
## Before Installation
Before you begin installation, you have to prepare your laravel app by installing the following:
1. Install and Configure Laravel Sanctum <a target="_blank" href="https://laravel.com/docs/9.x/sanctum#installation">Follow these Steps</a>
2. Install and configure Laravel Breeze as the authentication package <a target="_blank" href="https://laravel.com/docs/9.x/starter-kits#laravel-breeze-installation">Follow these steps</a>
3. Install and configure `spatie/laravel-permission`. <a target="_blank" href="https://spatie.be/docs/laravel-permission/v5/installation-laravel">Follow these Steps</a>
4. Install and configure `laravel/scout`. By default, acacia will try to configure the basic `database` driver for scout during installation. <a target="_blank" href="https://laravel.com/docs/9.x/scout#installation">Follow Scout Installation steps</a>

Now you are ready to install Acacia!
Don't worry, acacia will be installed under the `acacia/` directory as a separate modular component, with its own frontend assets and even compilation process using vite.js, all separate from your main app, allowing you to even mix two frontend stacks together!

<a name="installation"></a>
## Installation

To install through Composer, by run the following command:

```bash
composer require savannabits/acacia -W
```

By default, Acacia's classes are not loaded automatically.
Since acacia will be installed in the `acacia/` folder, before proceeding with installation, autoload the Acacia namespace and backend modules using `psr-4` by adding the following to your app's composer.json:

```json
{
  "autoload": {
    "psr-4": {
        "App\\": "app/",
        "Database\\Factories\\": "database/factories/",
        "Database\\Seeders\\": "database/seeders/",
        "Acacia\\": "acacia/" 
    }
  }
}
```

**Tip: don't forget to run `composer dump-autoload` afterwards.**

The package will automatically register its service providers.

Then install the necessary files for code generation and backend by running:

```bash
php artisan acacia:install 
```

**Tip: If you would like to force the replacement of existing Acacia files, add the `--force` or `-F` option to the command above**<br>

**Tip: By default, when permission migrations are created, the package will ask you if you would like to run the migrations now or later. You can specify the `-y` option to automatically accept to run migrations non-interactively**

Run the seeders for all modules. This is necessary in order to have the default **Administrator** role and user seeded. Without this step you won't be able to login immediately.

```bash
php artisan acacia:seed
```

Finally you can build acacia's assets using vite. The vite asset compiler is inside the `acacia/` folder.
```bash
cd acacia/ && npm run dev #to watch assets during development
cd acacia/ && npm run build # To build the assets for production
```
**TIP: The destination of the built assets is in `public/vendor/acacia` and the folder is cleared first with each build**

<a name="configuration"></a>
## Configuration

During the installation step, the acacia config file is published to `config/acacia.php`. It has the following among other configs:
- **`acacia.route_prefix`** - allows you to define the uri under which the backend can be accessed. By default it is `admin`. You can change this by setting the **env** variable `ACACIA_ROUTE_PREFIX`
- **`acacia.sidebar.heading`** - Allows you to define the sidebar heading displayed above the backend's sidebar. You can change this by setting the **env** key `ACACIA_SIDEBAR_HEADING`
- **`acacia.dev_modules`** - I highly recommend that you don't touch this setting. It lists the modules that should not be available when the app is in production. 

**Congratulations! Your backend is now set and you can access it on `your-domain/admin` or the route prefix specified in config. Let's now proceed to generate some code**
<p class="flex justify-between">
<larecipe-button tag="a" href="./overview" type="primary" ><i class="fas fa-arrow-left"></i> Overview</larecipe-button>
<larecipe-button tag="a" href="../basics/package-structure" type="primary" >Package Structure <i class="fas fa-arrow-right"></i> </larecipe-button>
</p>
