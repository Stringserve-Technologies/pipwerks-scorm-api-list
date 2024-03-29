# Pipwerks SCORM API list

It's a module list for the wonderful [Pipwerks] api list.

```
npm install --save pipwerks-scorm-api-list
```

# Add a New future

### 1.added score

```
cmi.core.score.raw - This is for 1.2 SCORM function
```

### 2. cumulativeScore

```
here we get cmi.core.score.raw before set. Then add with the current before set
```

### 3. maxscore

```js
cmi.core.score.max - This is for 1.2 SCORM function
```

```js
cmi.score.max -This is for 2004 SCORM function
```

## Example

```js
import { SCORM } from "pipwerks-scorm-api-list";

SCORM.init();
var name = SCORM.get("cmi.core.student_name");
SCORM.set("cmi.core.lesson_status", "completed");
SCORM.save();
SCORM.quit();
```

## Shortcuts

```
pipwerks.SCORM.init = pipwerks.SCORM.connection.initialize;
pipwerks.SCORM.get  = pipwerks.SCORM.data.get;
pipwerks.SCORM.set  = pipwerks.SCORM.data.set;
pipwerks.SCORM.save = pipwerks.SCORM.data.save;
pipwerks.SCORM.quit = pipwerks.SCORM.connection.terminate;
```

## Methods

### `pipwerks.SCORM.isAvailable(): boolean`

A simple function to allow Flash ExternalInterface to confirm
presence of JS list before attempting any LMS communication.

### `pipwerks.SCORM.API.find(window): object`

Looks for an object named API in parent and opener windows

### `pipwerks.SCORM.API.get():object`

Looks for an object named API, first in the current window's frame
hierarchy and then, if necessary, in the current window's opener window
hierarchy (if there is an opener window).

### `pipwerks.SCORM.API.getHandle(): object`

Returns the handle to API object if it was previously set
Returns the pipwerks.SCORM.API.handle variable.

### `pipwerks.SCORM.connection.initialize(): boolean`

Tells the LMS to initiate the communication list.

### `pipwerks.SCORM.connection.terminate(): boolean`

Tells the LMS to terminate the communication list

### `pipwerks.SCORM.data.get(parameter:string): string`

Requests information from the LMS.

### `pipwerks.SCORM.data.set(parameter:string, value:string): boolean`

Tells the LMS to assign the value to the named data model element.
Also stores the SCO's completion status in a variable named
pipwerks.SCORM.data.completionStatus. This variable is checked whenever
pipwerks.SCORM.connection.terminate() is invoked.

### `pipwerks.SCORM.data.save():boolean`

Instructs the LMS to persist all data to this point in the list

### `pipwerks.SCORM.debug.getCode():number`

Requests the error code for the current error state from the LMS

### `pipwerks.SCORM.debug.getInfo(errorCode:number):string`

> "Used by a SCO to request the textual description for the error code
> specified by the value of [errorCode]."

### `pipwerks.SCORM.debug.getDiagnosticInfo(errorCode:number):string`

> "Exists for LMS specific use. It allows the LMS to define additional
> diagnostic information through the API Instance."

### `pipwerks.UTILS.StringToBoolean(str:string):boolean`

Converts 'boolean strings' into actual valid booleans.
(Most values returned from the API are the strings "true" and "false".)

### `pipwerks.UTILS.trace(msg:string):void`

Displays error messages when in debug mode.

[Pipwerks]: https://github.com/devopsjavauser/pipwerks-scorm-api-list
