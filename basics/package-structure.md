- [Inspiration](#inspiration)
- [Module Folder Structure](#module-folder-structure)

# Package Structure

<a name="inspiration"></a>
## Inspiration

The modular structure of this package's generated code is heavily inspired by **<a target="_blank" href="https://nwidart.com/laravel-modules/v6/introduction">nwidart/laravel-modules</a>**. In fact, the generated modules are almost similar, with only slight differences in the folder structure.

<a name="module-folder-structure"></a>
## Module Folder Structure
|Folder         | Subfolder     | Description |
| -----------:  | ------------: | :---------- |
| **ModuleName/**   |               | Parent folder for the module the module. Each CRUD generated will be created as a separate module.<br> The module name takes the plural Pascal case form of the table name. E.g if the table name is `user_types` the module name hence the folder name will be `UserTypes` |
|               | **Config/**   | Holds the module's configuration files |
|               | **Console/**  | Holds the module's console commands |
|               | **Database/** | Holds the module's migrations, factories and seeders |
|               | **Http/**     | Holds the module's controllers, middleware and requests. <br> Validation and Authorization are done within Request classes. Currently the generated request classes include `IndexRequest`,`ViewRequest`,`StoreRequest`,`UpdateRequest`,`DestroyRequest` and `DtRequest` for the datatable.<br>There are two generated controllers: the `web` controller and the `api` controller |
|               | **Js/**     | Holds the module's javascript assets. These are mainly `Vue.js 3` components and pages. <br> The backend uses `Inertia.js` to handle requests from Vue.js pages. If you need to customize your UI, this is mostly where you will dwell in after code generation. <br>Most of the common layout and component files are located in the `Core` module inside the `Js` folder, which you will find aliased as `@/` to other components |
|               | **Models/**     | Holds the models for the module. Only one main Model will be generated per module. You can add more models in the same module if you like. |
|               | **Policies/**     | Holds the Authorization logic for the module. Only one main Authorization policy is generated. The policies have been configured to check the available permissions from `laravel-permission`. |
|               | **Providers/**     | Holds the module's Main Service Provider and any other Service Providers for the module |
|               | **Repositories/**     | Holds the Repositories for the module. Only one Repository is initially generated but you can create more. The `Repository` class holds all the logic for the CRUD. The work of controllers is merely to receive validated and authorized user input, pass the input to the Repository and return a response to the user after the action is completed. |
|               | **resources/**     | This is used to load the module's blade views and other modular assets just in case you may want to extend the module. Currently it is not in use, but it was retained from `nwidart/laravel-module`'s design. |
|               | **Routes/**     | This contains the module's routes. There are two separate route files: `api.php` and `web.php` You can read more in the Routing Section.|
|               | **tests/**     | Holds the module's Unit and Feature tests. Currently, tests are not generated yet. |
|               | **composer.json**     | This is the module's composer definition |
|               | **module.json**     | This is the module's definition file. |
|               | **package.json**     | The module's `package.json` just in case you want to extend the module with other dependencies. These are compiled by running the module's `webpack.mix` |
|               | **webpack.mix.js**     | The module's `webpack.mix` file to be used for compiling the `assets` inside the `resources` folder. This is not used in the generated code, but it felt right to still maintain it from `nwidart/laravel-modules'` structure. |
| **package.json**      |                   |Inside `acacia/`, this is the main npm dependencies definition file. Most of these dependencies are the ones used in the `Core` module, hence shared with all the other modules.|
| **package-lock.json** |                   |The lock file for the main `package.json` file|
| **tailwind.config.ts**|                   |The main `tailwindcss` configuration file. If you would like to change your theme colors or any other tailwindcss settings, this is the place to do it. |
| **tsconfig.json**     |                   |All the `Vue` pages are written in `typescript`. This is the main `typescript config` file for development|
| **vite.config.ts**    |                   |The backend assets are compiled using `vite.js`. This is the main `vite config` file.|


<p class="flex justify-between">
<larecipe-button tag="a" href="./installation" type="primary" ><i class="fas fa-arrow-left"></i> Installation</larecipe-button>
<larecipe-button tag="a" href="../basics/usage" type="primary" >Basic Usage <i class="fas fa-arrow-right"></i> </larecipe-button>
</p>
