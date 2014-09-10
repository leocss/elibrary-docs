API Documentation for Developers
====================================

The API-server is the central server for all systems developed for this e-library project.

Installation
================

#### Step 1: Source Code

If you already have the [Elibrary-API](https://github.com/leocss/elibrary-api) repository on your local machine, you can skip this step.

Clone the elibrary-api repository to your development machine to any location of your choice. 

The commands below show an example that clones the elibrary-api repository to c:/dev/www/elibrary-api

	$ cd c:/dev/www
	$ git clone https://github.com/leocss/elibrary-api.git

#### Step 2: Install NodeJS

If you already have NodeJS installed on your dev machine, you can skip this step..

Go over to [NodeJS Official Website](http://nodejs.org) and grab yourself a copy of NodeJS.

Tip: i prefer installing nodejs outside of "Program Files" folder if on Windows. For example, install it on `c:/dev/nodejs`

#### Step 3: Running API-Server

This is pretty simple. All you have to do is `cd` into the directory where you cloned the 
elibrary api repository to and run this command to install all dependencies.

	$ cd c:/dev/www/elibrary-api
	$ npm install

Next, run this command after `npm install` to start the server

	$ npm start

Thats it... You should now see on your command promt that the Elibrary API Server is Running...

Next, try visiting http://127.0.0.1:4000/books on your browser to test. Thank you.