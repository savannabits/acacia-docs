# Frontend Assets
I do realize that **Frontend** may mean several things to several people, but here we are simply discussing the client-side assets, those that are loaded directly in the browser. Mostly, these include the `Vue.js` pages and components as well as `CSS` that is used to render the User Interface.

---
- [Compiling Assets for Modules](#compiling-assets-for-modules)

## Compiling Assets for Modules
Most of the Shared Vue files are located inside the `Core` module. Compilation is done using [Vite](https://vitejs.dev/) and all the configurations are located inside the `acacia/` folder. To run the vite compiler in development (watch) mode simply execute this from your project's root directory:

```bash
cd acacia/ && npm run dev
```

To build the assets for production, run the following from your project's root directory:

```bash
cd acacia/ && npm run build
```
The destination of the compiled assets upon running the build command is in the `public/vendor/acacia` folder of your laravel app.

______________
<p class="flex justify-between">
<larecipe-button tag="a" href="./usage" type="primary" class="btn-sm"><i class="fas fa-arrow-left"></i> Basic Usage</larecipe-button>
<larecipe-button tag="a" href="../digging-deeper/index" type="primary" class="btn-sm">Digging Deeper <i class="fas fa-arrow-right"></i> </larecipe-button>
</p>