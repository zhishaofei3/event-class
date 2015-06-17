# A lightweight Event class defined in small module (JavaScript/ES6)


## Installation

Use [jspm](http://jspm.io/) ease the use of ES6 features and it installs the package from the npm registry

```bash
jspm install npm:event-class
```
or simply use npm

```bash
npm install event-class --save
```

## Usage

```javascript
import EventClass from "event-class";

// Extends
class AnyClass extends EventClass{
}

let anyObject = new AnyClass();

function namedFunction(data){
	console.log("change event :", data);
}

// Listen to the 'change' event
anyObject.on("change", namedFunction);

// Listen once to the 'change:attribute' event 
anyObject.once("change:attribute", function(data){
	console.log("change:attribute event :", data);
});

anyObject.trigger("change:attribute", "Hello 1 !");
anyObject.trigger("change:attribute", "Hello 2 !");
anyObject.off("change", namedFunction);
anyObject.trigger("change:attribute", "Hello 3 !");



/* console output
> change:attribute event : Hello 1 !
> change event : Hello 1 !
> change event : Hello 2 !

No output with "Hello 3 !" because there is no listener anymore 
*/
```
