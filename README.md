# Blog app (using Vue.js 2) 

This app will allow you to edit and post articles on your blog. Test it !
For running the app, make sure you have [node.js](https://nodejs.org/en/) npm version 3+ and [Git](https://git-scm.com/) installed.

## Getting Started
These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

Use those commands to generate node-modules &co (using vue-cli).
```
$ npm install -g vue-cli
$ vue init webpack-simple blog-app
$ cd blog-app
# npm install
$ npm run dev
```
When your files and folders are created, you can replace what is inside and src/App.vue by what is on this github. Then, you will have to install all dependencies below.

For vue-resource :
```
$ npm install vue-resource
or
$ yarn add vue-resource
```

For vue-router :
```
$ npm install vue-router
or
$ yarn add vue-router
```

For Firebase :
```
# npm
$ npm install --save re-base
 
# yarn
$ yarn add re-base
```


### What I used to build this app :
* [Vue.js version 2.x](https://vuejs.org/) - Web framework used
* [vue-cli](https://github.com/vuejs/vue-cli) - Dependency Management
* [vue-resource](https://github.com/pagekit/vue-resource) - Dependency Managment
* [vue-router](https://router.vuejs.org/en/installation.html) - Dependency Managment
* [Firebase](https://firebase.google.com/) - Database
* [JSONPlaceholder](https://jsonplaceholder.typicode.com/) - Fake online REST API for testing and prototyping
* [Flaticon](https://www.flaticon.com/) - Free icon

### Author
* **Orélia Sokambi** - *Initial work*
