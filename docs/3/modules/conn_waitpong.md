---
title: "Module Details: conn_waitpong (v3)"
---

## The "conn_waitpong" Module

### Description

This module requires all clients to respond to a PING request before they can fully connect. This is useful for preventing drive-by attacks from sources that can send data but not respond.

### Configuration

To load this module use the following `<module>` tag:

```xml
<module name="conn_waitpong">
```

#### `<waitpong>`

The `<waitpong>` tag defines settings about how the conn_waitpong module should behave. This tag can only be defined once.

Name           | Type    | Default Value                          | Description
-------------- | ------- | -------------------------------------- | -----------
killonbadreply | Boolean | Yes                                    | Whether to kill clients that respond with an incorrect ping value.
sendsnotice    | Boolean | No *(since 3.5)*<br>Yes *(3.0 to 3.4)* | Whether to tell a user to run `/QUOTE PONG ...` when waiting for a response.

##### Example Usage

```xml
<waitpong killonbadreply="yes"
          sendsnotice="no">
```
