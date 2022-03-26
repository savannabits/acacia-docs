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
| **Roles/**   |               | Parent folder for the module The module Name, in this case `roles` |
|               | **Config/**   | Holds the module's configuration files |
|               | **Console/**  | Holds the module's console commands |
|               | **Database/** | Holds the module's migrations, factories and seeders |
|               | **Http/**     | Holds the module's controllers, middleware and requests |
|               | **Js/**     | Holds the module's jobs |
|               | **Models/**     | Holds the module's jobs |
|               | **Policies/**     | Holds the module's jobs |
|               | **Providers/**     | Holds the module's jobs |
|               | **Repositories/**     | Holds the module's jobs |
|               | **resources/**     | Holds the module's jobs |
|               | **Routes/**     | Holds the module's jobs |
|               | **tests/**     | Holds the module's jobs |
|               | **composer.json**     | Holds the module's jobs |
|               | **module.json**     | Holds the module's jobs |
|               | **package.json**     | Holds the module's jobs |
|               | **webpack.mix.js**     | Holds the module's jobs |
| **package.json**      |                   ||
| **package-lock.json** |                   ||
| **tailwind.config.ts**|                   ||
| **tsconfig.json**     |                   ||
| **vite.config.ts**    |                   ||
