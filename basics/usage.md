# Basic Usage
Most of the code generation features are inspired by [`savannabits/jetstream-inertia-generator`](https://github.com/coolsam726/jetstream-inertia-generator), with some major re-writes. This section provides the basic usage instructions, but the [Digging Deeper](../digging-deeper/index) section will go into more details on each of the code generation features.

---
- [Initial Admin User](#initial-admin-user)
- [Write Migrations](#write-migrations)
- [Preparing Schematics](#preparing-schematics)
- [Generating Code](#generating-code)
 
<a name='initial-admin-user'></a>
## Initial Admin User
If you followed the installation steps, a default user should be created and given the `administrator` role. The user is created with the following credentials:

| Email                         | Password      |
| :-----                        | :--------     |
| `admin@savannabits.com`       | `password`    |

<a name='write-migrations'></a>
## Write Migrations
`Acacia` generates code based on an existing database. If the database does not exist yet, the first step is to write and run migrations. To better illustrate, we will be generating one of the `CRUDs` needed to build a music streaming web app mentioned in this [Case Scenario](../getting-started/overview#case-scenario). Let's create an `album_types` table:

```bash
php artisan make:migration create_album_types_table
```

Populate the migration with this content:

```php
    Schema::create('album_types', function (Blueprint $table) {
        $table->id();
        $table->string('slug')->unique();
        $table->string('name')->unique();
        $table->text('description')->nullable();
        $table->boolean('active')->default(true);
        $table->timestamps();
    });
```
Run the migration:

```bash
php artisan migrate
```

<a name='preparing-schematics'></a>
## Preparing Schematics
Code generation in `Acacia` is a two-step process, but this can be done all in one command. The first step is to generate a `schematic` for the module. The schematic defines the fields and relationships of the module. Later the generation command will use this information when generating the code. You can create the code from the interface, or simply run the following command:
```bash
php artisan acacia:blueprint album_types
```
Output:
[Image]

<a name='generating-code'></a>
## Generating Code
The next step is to finally generate the code: This is done with the following command:

```bash
php artisan acacia:make album_types
```
The command will generate the `AlbumTypes` module, whose files will be under the folder `acacia/AlbumTypes/` as shown in the command output below:

Output:
[Image]
__________________________
**TIP: If the module already exists and you would like to force its replacement, you can specify `-F` or `--force` to the `acacia:make` command.**
___________________________
**NB: If the `album_types` Schematic did not exist, running `acacia:make` will generate it first before proceeding.**
____________________
**TIP: In order to have the module's frontend assets registered, you need either run `npm run build` or even better, have the `vite.js compiler` watching the files by running `npm run dev` under the `acacia/` folder. See [Frontend Assets](../basics/frontend-assets) for more details.**
_______________

Congratulations! You have just generated your first CRUD! You can access the module via the backend sidebar under `Backend -> Album Types`

<p class="flex justify-between">
<larecipe-button tag="a" href="./package-structure" type="primary" class="btn-sm"><i class="fas fa-arrow-left"></i> Installation</larecipe-button>
<larecipe-button tag="a" href="./frontend-assets" type="primary" class="btn-sm">Frontend Assets <i class="fas fa-arrow-right"></i> </larecipe-button>
</p>
