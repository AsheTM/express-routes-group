# Express routes group
Simple way to group your routes in Express + chaining it.


If you want to prefix all routes with a certain URL you can use the group method as following:

```js
var app = require('express');
require('express-routes-group');
 
app
  .group("/api/v1", (router) => {
      router.get("/path1", controller1); // /api/v1/login 
  })
  .group("/api/v2", (router) => {
      router.get("/path2", controller2); // /api/v2/path2 
  });
```

In case you don't want to add a prefix but still need to group certain routes you can leave the first parameter 
and go straight for the function:

```js
var app = require('express');
require('express-routes-group');
 
app
  .group((router) => {
      router.use(middleware1);
  })
  .group((router) => {
      router.use(middleware2);
  });
```


* Inspired from `express-group-routes`
