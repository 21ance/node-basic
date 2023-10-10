# node-basic

This is a simple project to try out node.js - I am currently learning it through [The Odin Project](https://www.theodinproject.com/lessons/nodejs-basic-informational-site).

```javascript
const http = require("http");
const fs = require("fs");

const hostname = "localhost";
const port = 8080;

const server = http.createServer((req, res) => {
	res.writeHead(200, { "Content-Type": "text/html" });

	let filename = req.url;
	switch (filename) {
		case "/":
			filename = "/index";
			break;
		case "/about":
			break;
		case "/contact-me":
			break;
		default:
			filename = "/404";
	}
	filename = `.${filename}.html`;

	fs.readFile(filename, "utf8", (err, data) => {
		console.log(filename);
		if (err) {
			res.writeHead(404, { "Content-Type": "text/html" });
			console.log(err);
		}
		res.write(data);
		res.end();
	});
});

server.listen(port, hostname, () => {
	console.log(`running at https://${hostname}:${port}`);
});
```
