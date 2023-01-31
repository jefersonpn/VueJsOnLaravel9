# VueJsOnLaravel9
How to install VueJs on Laravel 9 with Vite


1. Install laravel 9 App
First, open Terminal and run the following command to create a fresh laravel project:

```command
composer create-project --prefer-dist laravel/laravel:^9.0 laravel9-vue3-vite
```
or, if you have installed the Laravel Installer as a global composer dependency:

laravel new laravel9-vue3-vite
2. Install NPM Dependencies
Run the following command to install frontend dependencies:
```command
npm install
```
Step 3: Install Vue 3
Now after installing node modules we need to install vue 3 in our application, for that execute the following command in the terminal npm install vue@next vue-loader@next. vue-loader is a loader for webpack that allows you to author Vue components in a format called Single-File Components. vue-loader@next is a loader that is for webpack to author Vue components in single-file components called SFCs.
```command
npm install vue@next vue-loader@next
```
Step 4: Install vitejs/plugin-vue plugin
In laravel 9 latest release install vitejs/plugin-vue plugin for installing vue3 or vue in laravel. This plugin provides required dependencies to run the vuejs application on vite. Vite is a  build command that bundles your code with Rollup and runs of localhost:3000 port to give hot refresh feature.
```command
npm i @vitejs/plugin-vue
```
Step 4: Update vite.config.js file
Vite is a module bundler for modern JavaScript applications. Open vite.config.js and copy-paste the following code. First invoice defineConfig from vite at the top of the file and also import laravel-vite-plugin. Here plugins() take the path of the js and CSS file and create bundles for your application. you need to add vue() in the plugins array.

```js
// vite.config.js
import { defineConfig } from 'vite';
import laravel from 'laravel-vite-plugin';
import vue from '@vitejs/plugin-vue'


export default defineConfig({
    plugins: [
        vue(),
        laravel([
            'resources/css/app.css',
            'resources/js/app.js',
        ]),
    ],
});
```
Step 4: Vite Dev Server Start
Now after installing the vue 3, we need to start the dev server for vite for that run the following command and it will watch your resources/js/app.js file and resources/css/app.css file. It also starts a vite server on http://localhost:3000. you can not open it in the browser as it is for vite hot reload and it runs in the background and watches the assets of your application like js and CSS.
```command
npm run dev
```
Step 5: Create Vue 3 App
In resources/js/app.js create an instance of the vue 3 firstly you import { createApp } from 'vue' and createApp It takes a parameter here we have passed App. Before that, you can create a vue file which is the main file responsible for the vuejs content name is App.vue.
```js
// app.js
require('./bootstrap');

import {createApp} from 'vue'

import App from './App.vue'

createApp(App).mount("#app")
```
Step 6: Create Vue 3 Component
Under the js folder create a file name 'App.vue' and write content for this example let’s write simple "How To Install Vue 3 in Laravel 9 with Vite - TechvBlogs" you can change it according to your requirement.
```js
<template>
    How To Install Vue 3 in Laravel 9 with Vite - TechvBlogs
</template>
```
Step 7: Connect Vue 3 Component with Laravel blade file
In this step, go-to resource / views  directory, create the  app.blade.php  file, and add the following code to app.blade.php  as follow:
```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title>How To Install Vue 3 in Laravel 9 with Vite</title>
</head>
<body>
	<div id="app"></div>

	@vite(['resources/css/app.css', 'resources/js/app.js'])
</body>
</html>
```
