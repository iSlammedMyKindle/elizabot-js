elizabot-js
===========

Eliza JS bot based on www.masswerk.at/elizabot and http://en.wikipedia.org/wiki/ELIZA

Usage:

```js
const elizabotObj = require('./elizabot.js');
const eliza = new elizabotObj.bot(); //initializes a new eliza instance

eliza.start()          // returns a greeting message

eliza.reply(msgtext)   // returns a eliza-like reply based on the message text passed into it

eliza.bye()            // returns a farewell message, sets eliza.quit to true

//To make custom responses:
var customResponses = [
    ["chillidog", 0, [
		["*", [
		     "You seem to have an obsession with chillidogs.",
		     "chillidogs are the best.",
		     "those are very delicious.",
		     "Mmmmmm."
		]]
	]],
];

//setup regex for the response, this permanently alters the array:
elizabotObj.initializeKeywordRegex(customResponses);
```

## Modifications

* Lighter memory footprint for when defining multiple instances - Definitions for english dialects were separated from the `Elizabot` Object
* Support for new keywords before initializing elizabot (`new elizabotObj.bot(false,keywordsArray)`)
* Removed some legacy javascript that was used for IE6 and under.