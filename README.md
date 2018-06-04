# Express lab Test API

from : [source](http://www.artit-k.com/restful-api-node-js-express/)

init package.json

and Installatiob express.js

```sh
$ mkdir node-app
$ cd node-app
$ npm init -y
$ npm install express nodemon body-parser --save
```

goto package.json

```json
{
  "name": "express-lab",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "start": "nodemon server.js",  <-- add
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "body-parser": "^1.18.3",
    "express": "^4.16.3",
    "nodemon": "^1.17.5"
  }
}
```

create server.js

```js
const express = require("express");
const app = express();

app.get("/", (req, res) => {
  res.send("Hello World");
});

app.listen(3000, () => {
  console.log(`Example app listening on port 3000`);
});
```

| Methods | Route         | Request body (JSON)     | Response body (JSON)          | Success (HTTP status) | Fail (HTTP Status) | Description          |
| ------- | ------------- | ----------------------- | ----------------------------- | --------------------- | ------------------ | -------------------- |
| GET     | /item/        |                         | {"items": ["Init item"]}      | 200                   |                    | Get All Item         |
| GET     | /item/{index} |                         | {"item": "Init item"}         | 200                   | 404                | Get Item by Index    |
| POST    | /item/        | {"item": "New item"}    |                               | 201                   | 400                | Add Item             |
| PUT     | /item/{index} | {"item": "Update item"} | {"oldItem": "Old item"}       | 200                   | 400/404            | Update item by index |
| DELETE  | /item/{index} |                         | {"removeItem": "Remove item"} | 200                   | 404                | Delete item by index |

---- 

cool