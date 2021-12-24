# 1. Create Angular App
````bash
ng new ngx-heroku
````

# 2. Configure Angular App to Deploy Properly on Heroku
```bash
npm install express --save
```

#### ✪ Create a server.js

```javascript
//Install express server
const express = require('express');
const app = express();
// Serve only the static files form the dist directory
app.use(express.static('./dist/angular-app-heroku'));
app.get('/*', (req, res) =>
    res.sendFile('index.html', {root: 'dist/angular-app-heroku/'}),
);
// Start the app by listening on the default Heroku port
app.listen(process.env.PORT || 8080);
```

#### ✪ Change start command in package.json

```json
{
  "name": "ngx-heroku",
  "version": "0.0.0",
  "scripts": {
    "start": "node server.js",
    "heroku-postbuild": "ng build --prod"
  }
}
```

# 3. Git to push source code

# 4. Login to Heroku and create a new app in Heroku
![Logo](https://raw.githubusercontent.com/id1945/ngx-heroku/master/connect-git-project.png)
![Logo](https://raw.githubusercontent.com/id1945/ngx-heroku/master/config-deploy.png)
![Logo](https://raw.githubusercontent.com/id1945/ngx-heroku/master/ngx-heroku.png)

### https://ngx-heroku.herokuapp.com