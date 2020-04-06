[game-logic-sdk](../README.md) › [Globals](../globals.md) › ["ClientSDK"](../modules/_clientsdk_.md) › [ClientSDK](_clientsdk_.clientsdk.md)

# Class: ClientSDK

## Hierarchy

* **ClientSDK**

## Index

### Constructors

* [constructor](_clientsdk_.clientsdk.md#constructor)

### Properties

* [activeGUID](_clientsdk_.clientsdk.md#activeguid)
* [baseUrl](_clientsdk_.clientsdk.md#baseurl)
* [bookkeeper_data](_clientsdk_.clientsdk.md#bookkeeper_data)
* [demoMode](_clientsdk_.clientsdk.md#demomode)
* [options](_clientsdk_.clientsdk.md#options)
* [queryOptions](_clientsdk_.clientsdk.md#queryoptions)

### Methods

* [capture](_clientsdk_.clientsdk.md#capture)
* [combineParameters](_clientsdk_.clientsdk.md#private-combineparameters)
* [getQueryStringVariables](_clientsdk_.clientsdk.md#private-getquerystringvariables)
* [init](_clientsdk_.clientsdk.md#init)
* [request](_clientsdk_.clientsdk.md#private-request)
* [spin](_clientsdk_.clientsdk.md#spin)
* [triggerEvent](_clientsdk_.clientsdk.md#triggerevent)

## Constructors

###  constructor

\+ **new ClientSDK**(`demo`: boolean, `options?`: [ClientOptions](_clientsdk_.clientoptions.md)): *[ClientSDK](_clientsdk_.clientsdk.md)*

Defined in ClientSDK.ts:31

Create a new instance of ClientSDK

**Parameters:**

Name | Type | Default | Description |
------ | ------ | ------ | ------ |
`demo` | boolean | false | boolean Demo Mode Enabled/Disabled |
`options?` | [ClientOptions](_clientsdk_.clientoptions.md) | - | ClientOptions Optional options for injection of manual spin data  |

**Returns:** *[ClientSDK](_clientsdk_.clientsdk.md)*

## Properties

###  activeGUID

• **activeGUID**: *string* = ""

Defined in ClientSDK.ts:11

the activeGUID changes each spin, this is the currently active GUID

___

###  baseUrl

• **baseUrl**: *string* = "/op/"

Defined in ClientSDK.ts:6

relative path of the backend

___

###  bookkeeper_data

• **bookkeeper_data**: *any*

Defined in ClientSDK.ts:31

If a win is pending, this contains information to capture the win

___

###  demoMode

• **demoMode**: *boolean* = false

Defined in ClientSDK.ts:16

true, if demomode is enabled

___

###  options

• **options**: *[ClientOptions](_clientsdk_.clientoptions.md)* = new ClientOptions()

Defined in ClientSDK.ts:21

Options to set for simulation mode

___

###  queryOptions

• **queryOptions**: *any*

Defined in ClientSDK.ts:26

Contains additional aggregator data

## Methods

###  capture

▸ **capture**(`callback`: function): *void*

Defined in ClientSDK.ts:146

Capture a previous win from bookkeeper - needs active bookkeeper_data (set automagically)

**Parameters:**

▪ **callback**: *function*

Callback with (err: string, data: object)

▸ (`err`: string, `data`: object): *void*

**Parameters:**

Name | Type |
------ | ------ |
`err` | string |
`data` | object |

**Returns:** *void*

___

### `Private` combineParameters

▸ **combineParameters**(`object`: any): *string*

Defined in ClientSDK.ts:99

combine parameters into query string

**Parameters:**

Name | Type | Description |
------ | ------ | ------ |
`object` | any | parameters to migrate into query string  |

**Returns:** *string*

___

### `Private` getQueryStringVariables

▸ **getQueryStringVariables**(): *object*

Defined in ClientSDK.ts:115

Parse variables sent via GET query string into associative array

**Returns:** *object*

* \[ **index**: *string*\]: string

___

###  init

▸ **init**(`providerToken`: string, `callback`: function): *void*

Defined in ClientSDK.ts:131

Initialize a new gaming session

**Parameters:**

▪ **providerToken**: *string*

SessionID / IdempotentToken / ProviderToken sent by Aggregator

▪ **callback**: *function*

Callback with (err: string, data: object)

▸ (`err`: string, `data`: object): *void*

**Parameters:**

Name | Type |
------ | ------ |
`err` | string |
`data` | object |

**Returns:** *void*

___

### `Private` request

▸ **request**(`url`: string, `parameters`: object, `callback`: function): *void*

Defined in ClientSDK.ts:56

Fire the HTTP request to the server

**Parameters:**

▪ **url**: *string*

string the url to call

▪ **parameters**: *object*

object parameters to send via POST

▪ **callback**: *function*

callback in format (err: string, response: object)

▸ (`err`: string, `response`: object): *void*

**Parameters:**

Name | Type |
------ | ------ |
`err` | string |
`response` | object |

**Returns:** *void*

___

###  spin

▸ **spin**(`bet`: number, `callback`: function): *void*

Defined in ClientSDK.ts:170

Issue a spin to the game backend

**Parameters:**

▪ **bet**: *number*

number bet amount

▪ **callback**: *function*

Callback with (err: string, data: object)

▸ (`err`: string, `data`: object): *void*

**Parameters:**

Name | Type |
------ | ------ |
`err` | string |
`data` | object |

**Returns:** *void*

___

###  triggerEvent

▸ **triggerEvent**(`eventNum`: number, `eventParameters`: object, `callback`: function): *void*

Defined in ClientSDK.ts:215

Trigger a new event on game backend

**Parameters:**

▪ **eventNum**: *number*

number event number as specified in the game config

▪ **eventParameters**: *object*

objects the event parameters

▪ **callback**: *function*

Callback with (err: string, data: object)

▸ (`err`: string, `data`: object): *void*

**Parameters:**

Name | Type |
------ | ------ |
`err` | string |
`data` | object |

**Returns:** *void*
