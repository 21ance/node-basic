# node-basic

This is a simple project to try out node.js - I am currently learning it through [The Odin Project](https://www.theodinproject.com/lessons/nodejs-basic-informational-site).

```javascript
const express = require("express");
const app = express();
const port = 8080;

app.get("/", (req, res) => res.sendFile(__dirname + `/index.html`));
app.get("/about", (req, res) => res.sendFile(__dirname + `/about.html`));
app.get("/contact-me", (req, res) =>
	res.sendFile(__dirname + `/contact-me.html`)
);
app.get("*", (req, res) => res.sendFile(__dirname + `/404.html`));

app.listen(port, () => {
	console.log(`running on http://localhost:${port}`);
});
```
