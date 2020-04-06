
<a name="globalsmd"></a>

[game-logic-sdk](#readmemd) ÔÇ║ [Globals](#globalsmd)

# game-logic-sdk

## Index

### Modules

* ["ClientSDK"](#modules_clientsdk_md)


<a name="readmemd"></a>

[game-logic-sdk](#readmemd) ÔÇ║ [Globals](#globalsmd)

# game-logic-sdk

# GameLogicSDK


<a name="classes_clientsdk_clientoptionsmd"></a>

[game-logic-sdk](#readmemd) ÔÇ║ [Globals](#globalsmd) ÔÇ║ ["ClientSDK"](#modules_clientsdk_md) ÔÇ║ [ClientOptions](#classes_clientsdk_clientoptionsmd)

# Class: ClientOptions

Options for simulated spins

## Hierarchy

* **ClientOptions**

## Index

### Properties

* [injectedJSON](#optional-injectedjson)
* [simulationMode](#simulationmode)

## Properties

### `Optional` injectedJSON

ÔÇó **injectedJSON**? : *ArrayÔÇ╣stringÔÇ║* = []

Defined in ClientSDK.ts:229

___

###  simulationMode

ÔÇó **simulationMode**: *boolean* = false

Defined in ClientSDK.ts:230


<a name="classes_clientsdk_clientsdkmd"></a>

[game-logic-sdk](#readmemd) ÔÇ║ [Globals](#globalsmd) ÔÇ║ ["ClientSDK"](#modules_clientsdk_md) ÔÇ║ [ClientSDK](#classes_clientsdk_clientsdkmd)

# Class: ClientSDK

## Hierarchy

* **ClientSDK**

## Index

### Constructors

* [constructor](#constructor)

### Properties

* [activeGUID](#activeguid)
* [baseUrl](#baseurl)
* [bookkeeper_data](#bookkeeper_data)
* [demoMode](#demomode)
* [options](#options)
* [queryOptions](#queryoptions)

### Methods

* [capture](#capture)
* [combineParameters](#private-combineparameters)
* [getQueryStringVariables](#private-getquerystringvariables)
* [init](#init)
* [request](#private-request)
* [spin](#spin)
* [triggerEvent](#triggerevent)

## Constructors

###  constructor

\+ **new ClientSDK**(`demo`: boolean, `options?`: [ClientOptions](#classes_clientsdk_clientoptionsmd)): *[ClientSDK](#classes_clientsdk_clientsdkmd)*

Defined in ClientSDK.ts:31

Create a new instance of ClientSDK

**Parameters:**

Name | Type | Default | Description |
------ | ------ | ------ | ------ |
`demo` | boolean | false | boolean Demo Mode Enabled/Disabled |
`options?` | [ClientOptions](#classes_clientsdk_clientoptionsmd) | - | ClientOptions Optional options for injection of manual spin data  |

**Returns:** *[ClientSDK](#classes_clientsdk_clientsdkmd)*

## Properties

###  activeGUID

ÔÇó **activeGUID**: *string* = ""

Defined in ClientSDK.ts:11

the activeGUID changes each spin, this is the currently active GUID

___

###  baseUrl

ÔÇó **baseUrl**: *string* = "/op/"

Defined in ClientSDK.ts:6

relative path of the backend

___

###  bookkeeper_data

ÔÇó **bookkeeper_data**: *any*

Defined in ClientSDK.ts:31

If a win is pending, this contains information to capture the win

___

###  demoMode

ÔÇó **demoMode**: *boolean* = false

Defined in ClientSDK.ts:16

true, if demomode is enabled

___

###  options

ÔÇó **options**: *[ClientOptions](#classes_clientsdk_clientoptionsmd)* = new ClientOptions()

Defined in ClientSDK.ts:21

Options to set for simulation mode

___

###  queryOptions

ÔÇó **queryOptions**: *any*

Defined in ClientSDK.ts:26

Contains additional aggregator data

## Methods

###  capture

Ôû© **capture**(`callback`: function): *void*

Defined in ClientSDK.ts:146

Capture a previous win from bookkeeper - needs active bookkeeper_data (set automagically)

**Parameters:**

Ôû¬ **callback**: *function*

Callback with (err: string, data: object)

Ôû© (`err`: string, `data`: object): *void*

**Parameters:**

Name | Type |
------ | ------ |
`err` | string |
`data` | object |

**Returns:** *void*

___

### `Private` combineParameters

Ôû© **combineParameters**(`object`: any): *string*

Defined in ClientSDK.ts:99

combine parameters into query string

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`object` | any | parameters to migrate into query string  |

**Returns:** *string*

___

### `Private` getQueryStringVariables

Ôû© **getQueryStringVariables**(): *object*

Defined in ClientSDK.ts:115

Parse variables sent via GET query string into associative array

**Returns:** *object*

* \[ **index**: *string*\]: string

___

###  init

Ôû© **init**(`providerToken`: string, `callback`: function): *void*

Defined in ClientSDK.ts:131

Initialize a new gaming session

**Parameters:**

Ôû¬ **providerToken**: *string*

SessionID / IdempotentToken / ProviderToken sent by Aggregator

Ôû¬ **callback**: *function*

Callback with (err: string, data: object)

Ôû© (`err`: string, `data`: object): *void*

**Parameters:**

Name | Type |
------ | ------ |
`err` | string |
`data` | object |

**Returns:** *void*

___

### `Private` request

Ôû© **request**(`url`: string, `parameters`: object, `callback`: function): *void*

Defined in ClientSDK.ts:56

Fire the HTTP request to the server

**Parameters:**

Ôû¬ **url**: *string*

string the url to call

Ôû¬ **parameters**: *object*

object parameters to send via POST

Ôû¬ **callback**: *function*

callback in format (err: string, response: object)

Ôû© (`err`: string, `response`: object): *void*

**Parameters:**

Name | Type |
------ | ------ |
`err` | string |
`response` | object |

**Returns:** *void*

___

###  spin

Ôû© **spin**(`bet`: number, `callback`: function): *void*

Defined in ClientSDK.ts:170

Issue a spin to the game backend

**Parameters:**

Ôû¬ **bet**: *number*

number bet amount

Ôû¬ **callback**: *function*

Callback with (err: string, data: object)

Ôû© (`err`: string, `data`: object): *void*

**Parameters:**

Name | Type |
------ | ------ |
`err` | string |
`data` | object |

**Returns:** *void*

___

###  triggerEvent

Ôû© **triggerEvent**(`eventNum`: number, `eventParameters`: object, `callback`: function): *void*

Defined in ClientSDK.ts:215

Trigger a new event on game backend

**Parameters:**

Ôû¬ **eventNum**: *number*

number event number as specified in the game config

Ôû¬ **eventParameters**: *object*

objects the event parameters

Ôû¬ **callback**: *function*

Callback with (err: string, data: object)

Ôû© (`err`: string, `data`: object): *void*

**Parameters:**

Name | Type |
------ | ------ |
`err` | string |
`data` | object |

**Returns:** *void*


<a name="modules_clientsdk_md"></a>

[game-logic-sdk](#readmemd) ÔÇ║ [Globals](#globalsmd) ÔÇ║ ["ClientSDK"](#modules_clientsdk_md)

# Module: "ClientSDK"

## Index

### Classes

* [ClientOptions](#classes_clientsdk_clientoptionsmd)
* [ClientSDK](#classes_clientsdk_clientsdkmd)
