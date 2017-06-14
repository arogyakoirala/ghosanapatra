#### Initialize an empty node project

`npm init -y`

#### Initailize empty git repo

git init

#### Create index.js @ `/server/index.html`:

```javascript
import express from 'express';
import path from 'path'

let portNumber = 4000;
let app = express();


app.get('/*', (req, res) => {
	res.sendFile(path.join(__dirname, './index.html'));
});

app.listen(portNumber, () => {
	console.log(`App is running on port ${portNumber}`)
})

```
#### Create index.html page @ `/server/index.html`

```html
<!DOCTYPE html>
<html>

<head>
    <title>Auth0 Testing</title>
</head>

<body>
    <h1>Hello world!</h1>
</body>

</html>

```

#### Install express and babel-cli

`npm i --save-dev babel-cli`
`npm i -S express`


#### Update `/package.json` with the server script

```javascript
  "scripts": {
    "server": "babel-node server/index.js",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
```

####  Create `/.babelrc` file 

```javascript
{
	"presets": ["es2015"]
}

```
#### Install required es2015 preset dependency

`npm i --save-dev babel-preset-es2015`

#### Run server
`npm run server`