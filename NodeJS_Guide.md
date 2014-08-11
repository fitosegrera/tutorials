BootcampWeb-2014 NodeJS Guide
=============================

###Installing NodeJS
1.Download from:

	http://nodejs.org/download/

2.Install the binaries...

###Running Node

1.On the terminal type:

	node

2.It starts the node console. You can start using javascript syntax such as:

	console.log("Hello World!")

###First script

1.Open a file on your text editor and save it as:

	fileName.js

2.Write any javascript:

	console.log("Hello World!");

3.On your terminal:

	cd /PATH/TO/FILE

4.Hit enter

5.Type:

	node fileName.js

You should see "Hello World!" printed on your terminal...

###npm (Node Package Manager) commands and node-dev

1.on the terminal type:

	npm install node-dev -g

This installs the node-dev module globaly in your system. To use simply run the script like this:

	node-dev fileName.js

This allows to se changes in your script after saving the file. No need to re-run the script...

###Installing Modules and using modules

1.To install a module:

	sudo npm install moduleName	

2.To search for modules use the command:

	npm search | grep moduleName

or go to [the npm website](https://www.npmjs.org/)

3.To use a module you need to declare it on your script file:

	var myVar = require('moduleName');

###Local Modules

__Note:__ see example in folder /localModules

Local Modules act as independent .js files that you can call with the following syntax:

	var myVar = require('./localModule');

Notice the "./" before the module name, this is mandatory for calling local modules.

See the example at:

	/Exercise Files/3 Modules/1 What is a module/data_module

###Create a package.json files

1.In your terminal type:

	npm init

2.Fil the desired information and hit enter. Yoou will be prompted to confirm. Now a package.json file is created in your project's folder.

3.Open the file and before the "author" object add (notice this is just an example so we are using any modules):

	"dependencies" : {
		"node-markdown": "0.1.0",
		"socket.io" : "*"
	},

__Note:__ The "0.1.0" stands for the version of the mudule that we want to use. The "*" denotes the latest version of the module.

When the dependencies are added to the package,json file, you can install all of them with a simple command:

	npm install

###Update and remove modules

1.Inside the projects's directory type:

	npm update

This updates all the modules installed in the node_modules folder of the project...

2.To update global modules type:

	sudo npm update -g

3.To remove a module first delet it from the package,json file.

4.The on the terminal type:

	npm prune

###User Input in terminal

Take an iput from the terminal and procees it...

	var rl = require('readline');
	var prompts = rl.createInterface(process.stdin, process.stdout);
	prompts.question("How many cigars you some per day? ", function  (cigars) {
		var message = '';
		if (cigars > 5) {
			message = "Oh man " + cigars + 
			" is a lot!! Take it eassy... You should smoke less....";
		} else {
			message = "not that bad!";
		}
		console.log(message);
	  process.exit();
	});

###Reading a .txt file from your system

1.You need to have a "data.txt" file in your folder; same level as your .js file
2.Install the required modules
3.Run the script using the following command:

	node script.js data.txt

SCRIPT:

	var argv = require('optimist').argv,
		fs = require('fs');

	var file = argv._[0];

	/*UTF-8 (UCS Transformation Format—8-bit[1]) is a variable-width encoding 
	that can represent every character in the Unicode character set*/
	var txt = fs.readFileSync('data.txt', 'UTF-8');
	console.log('Text Contents: ' + txt);

###Reading a HTML file from your system

1.You need to have a "fileName.html" file in your folder; same level as your .js file
2.Install the required modules
3.Run the script using the following command:

	node script.js fileName.html

SCRIPT:

	var argv = require('optimist').argv,
		$ = require('jquery'),
		fs = require('fs');

	var file = argv._[0];

	/*UTF-8 (UCS Transformation Format—8-bit[1]) is a variable-width encoding 
	that can represent every character in the Unicode character set*/
	var html = fs.readFileSync(file, 'UTF-8');

	$(html).find('p').each(function(index) {
		var content = $(this).html();

		console.log('Paragraph ' + (index + 1) + ': ' + content);
	});

###Doing an HTTP Request

	var request = require('request');
	request('http://fii.to', function (error, response, body) {
	  if (!error && response.statusCode == 200) {
	    console.log(body) // Print the body of the page.
	  }
	});

###Downloading an .JPG file

	var http = require('http');
	var fs = require('fs');

	var file = fs.createWriteStream("fito.jpg");
	var request = http.get("http://fii.to/images/slides/15.jpg", function(response) {
	  response.pipe(file);
	});

###Simple HTTP Server

	// Load the http module to create an http server.
	var http = require('http');

	// Configure our HTTP server to respond with Hello World to all requests.
	var server = http.createServer(function (request, response) {
	  response.writeHead(200, {"Content-Type": "text/plain"});
	  response.end("Hello World\n");
	});

	// Listen on port 8000, IP defaults to 127.0.0.1
	server.listen(8000);

	// Put a friendly message on the terminal
	console.log("Server running at http://127.0.0.1:8000/");
