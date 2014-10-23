mongodb_commands
================

###Basic Commands
Whwnwever you see "dbname" in a command it means the database's name so you should replace it with your own.  

Start the Database:

	sudo service mongodb start

Stop the Database:

	sudo service mongodb stop

Show databases:

	show dbs

Find a Database:

	db.dbname.find()

Delete a database (from within the database):

	db.dropDatabase()

Use database (if there is no database with the name you specify, it will create it for you):

	use dbname

Saving a document in a database. This is a high level command, if the Document does not have a unique object ID, then it saves it as a new object and creates an ID for it. therwise, if the document does have a unique object ID then it just updates it:

	db.dbname.save(documentName)

Print the contents os a databased but formated as a JSON object (It makes it eassier to read):

	db.dbname.find().forEach(printjson);

To create a unique object ID (not using the default created by mongodb) you just need to include a '_id = ' to the begining of the document:

	db.dbname.insert({_id = "12", name = "joe".....});

The unique ID that mongoDB gives to a document by default, contains the date of when it was created. To get this date:

	db.dbname.find()[0]._id.getTimestamp()



####Create documents:
There are several ways of creating a document.

1.Inserting a full object:

	db.dbname.insert({name: "fito", last_name: "segrera", url: "http://fii.to", saved_on: new Date()});

2.Inserting element by element (line by line):

	var doc = {};
	doc.name = "fito";
	doc.last_name = "segrera";
	doc.url = "http://fii.to";
	doc.saved_on = new Date;
	
Check the new document:

	doc

You should see something like:

	{
		"name" : "fito",
		"last_name" : "segrera",
		"url" : "http://fii.to",
		"saved_on" : ISODate("2014-10-06T21:15:54.140Z")
	}

Finally the new document should be saved into the desired database:

	db.dbname.save(doc)

Print:

	db.dbname.find().forEach(printjson);