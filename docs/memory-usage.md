This section deals with using memory in backbench.

To use our memory, you need to send a `POST` request to endpoint [https://memory.backbench.io](https://memory.backbench.io).

The request body/payload has the following format:


```json
{
	"cmd": "",
	"auth": {
		"benchId": "",
		"userId": "",
		"accessKey": ""
	},
	"args": {

	},
	"json": true
}

```

These parameters values differs based on operations. 

**CMD** is basically operation name.

***AUTH*** is for authentication for API. Has 3 mandatory properties `benchId, userId, accessKey` (accessKey can be found in dropdown of bench). These all properties are `constant` for a bench.  

**ARGS** is based on operations to perform.

Following operations possible for the API

#### Setting Memory

```
cmd : bb:mem:set 
args: {key: "", value : ""}
```

#### Getting Memory

```
cmd : bb:mem:get
args: {key: ""}
```

#### Deleting Memory

```
cmd : bb:mem:del
args: {key: ""}
```

An example payload for setting up memory in backbench.

```json
{
	"cmd": "bb:mem:set",
    	"auth": {
        	"benchId": "aaaaa0",
        	"userId": "mybench",
        	"accessKey": "c72d2f3a91b80c1e7fb46f4332383795facd8e99df31b689513c2fa11a699adb"
    	},
    	"args": {
		"key": "jlo",
		"value": "one the floor"
	}
}
```
