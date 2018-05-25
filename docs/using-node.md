This section deals with using **NodeJS** on backebench.

To map a module to an endpoint, you need to make it as a public function, to make it same use the following conventions:

## Declaration

Follows this basic format.

``` 
module.exports.endpoint = function(req, cb){
...
}

```


### req (the request object)

Has following fields.

```
{  
	"method": "",  
	"path": "",  
	"body": {},  
	"headers": {},
	"query": {} 
}
```

### cb (callback function)

This is to be used to send `http response`. Follows the format as: 

```
cb(Object error, Object results);
```

**Convention:** 1st argument is used to send `error` response, while second one to send `success` response. 
**Note:** arguments must be `json` (otherwise it will throw an error and you'll get a blank response).

## Restriction

- Response format for `cb` must be json.
- Cannot use single inverted commas anywhere in the code.
- Module name cannot be `func.js`.

## Debugging

Error can be seen here.

## Logging

Logging can be done using `console.log()`, which can be seen in **Logs section**.

## Version

Currently supports *Node 5.10.1*.

## Example

We'll write a program using the conventions followed above, here we will print the request object.   


In module section, create a module (say `sample.js`) and paste the following code and hit save. 
```
module.exports.endpoint = function(req, callback){
	console.log("Request started processing at "+ (new Date()))
	callback(undefined, req)
	console.log("Request finished processing at "+ (new Date()))
}
```

In endpoint section, create a new endpoint with Path (say `/sample`) and select Handler as module's name (sample).

Done, now run the program at `https://USERNAME-BENCHID.beta-bench.backbench.io/`
