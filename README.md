simple-imap
===========

Simple imap listener for Node.js.

## Installation

```
npm install simple-imap
```

## Usage

```
var SimpleImap = require('simple-imap');

var options = {
	user: '<your username>',
	password: '<password>',
	host: '<imap host>',
	port: 993,
	tls: true,
	mailbox: 'INBOX'
};

var simpleImap = new SimpleImap(options);

simpleImap.on('error', function(err) {
	console.log(err);
});

simpleImap.on('ready', function() {
	console.log('ready');
});

simpleImap.on('open', function() {
	console.log('mailbox opened');
});

simpleImap.on('mail', function(mail) {
	console.log(mail);
});

simpleImap.on('close', function() {
	console.log('closed');
});

simpleImap.on('end', function() {
	console.log('end');
});

simpleImap.start();
```