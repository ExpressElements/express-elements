# express-server-demo

> Declaratively create a Express server inside of your electron applications using polymer web components.


## Run

```
$ npm install && bower install && npm start
```

### Build

```
$ npm run build
```

# Usage

```html
<!doctype html>
<html>
  <head>
		<meta charset="utf-8">
		<title>Electron boilerplate</title>
		<script src="bower_components/webcomponentsjs/webcomponents-lite.js"></script>
		<link rel="import" href="bower_components/express-server/express-server.html">
	</head>
	<body>
		<template id="app" is="dom-bind">
			<express-server port="{{port}}">
				<express-route method="get" path="/" middleware="[[_home()]]"></express-route>
			</express-server>
			<h1>Express Server running on port [[port]]</h1>
		</template>
		<script>
		(function(){
			'use strict';
			const app = document.getElementById("app");

			app._home = () => {
				return function (req, res) {
					res.send("hello world2");
				};
			}
		})();
		</script>
	</body>
</html>

```
