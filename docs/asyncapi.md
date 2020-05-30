# GrandMA 2 Websockets API 3.7.0 documentation

The GrandMA 2 Websockets API is the API used by the web remote.
## Table of Contents

* [Servers](#servers)
* [Channels](#channels)

<a name="servers"></a>

## Servers

<table>
  <thead>
    <tr>
      <th>URL</th>
      <th>Protocol</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
  <tr>
      <td>{deskIp}/?ma=1</td>
      <td>ws</td>
      <td>The GrandMA 2 console software</td>
    </tr>
    <tr>
      <td colspan="3">
        <details>
          <summary>URL Variables</summary>
          <table>
            <thead>
              <tr>
                <th>Name</th>
                <th>Default value</th>
                <th>Possible values</th>
                <th>Description</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td>deskIp</td>
                <td>
                    192.168.0.1
                  </td>
                <td>
                    Any
                  </td>
                <td>The IP of the desk we want to control.</td>
              </tr>
              </tbody>
          </table>
        </details>
      </td>
    </tr>
    </tbody>
</table>




## Channels



<a name="channel-/"></a>


#### Channel Parameters




###  `publish` /



#### Message

Accepts **one of** the following messages:

##### Message #1

Unsure


##### Payload


<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
      <th>Accepted values</th>
    </tr>
  </thead>
  <tbody>
<tr>
  <td>session </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "session": 0
}
```


##### Message #2



##### Payload


<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
      <th>Accepted values</th>
    </tr>
  </thead>
  <tbody>
<tr>
  <td>requestType </td>
  <td>string</td>
  <td></td>
  <td><code>getdata</code></td>
</tr>
<tr>
  <td>data </td>
  <td>string</td>
  <td><p>The data fields to query from the desk.
Looks like MA is not following standards here, because this is not an array with data field keys but a
concatenated string like <code>&quot;set,clear,solo,high&quot;</code>.</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>maxRequests </td>
  <td>integer</td>
  <td><p>Unsure</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>session </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "requestType": "getdata",
  "data": "string",
  "maxRequests": 1,
  "session": 0
}
```


##### Message #3



##### Payload


<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
      <th>Accepted values</th>
    </tr>
  </thead>
  <tbody>
<tr>
  <td>requestType </td>
  <td>string</td>
  <td></td>
  <td><code>login</code></td>
</tr>
<tr>
  <td>username </td>
  <td>string</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>password </td>
  <td>string</td>
  <td><p>MD5 hash of user's password.</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>session </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>maxRequests </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "requestType": "login",
  "username": "string",
  "password": "string",
  "session": 0,
  "maxRequests": 1
}
```


##### Message #4

Tells the desk that the WebSocket should be closed


##### Payload


<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
      <th>Accepted values</th>
    </tr>
  </thead>
  <tbody>
<tr>
  <td>requestType </td>
  <td>string</td>
  <td></td>
  <td><code>close</code></td>
</tr>
<tr>
  <td>session </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>maxRequests </td>
  <td>integer</td>
  <td><p>Unsure</p>
</td>
  <td><em>Any</em></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "requestType": "close",
  "session": 0,
  "maxRequests": 1
}
```





###  `subscribe` /



#### Message

Accepts **one of** the following messages:

##### Message #1



##### Payload


<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
      <th>Accepted values</th>
    </tr>
  </thead>
  <tbody>
<tr>
  <td>status </td>
  <td>string</td>
  <td></td>
  <td><code>server ready</code></td>
</tr>
<tr>
  <td>appType </td>
  <td>string</td>
  <td></td>
  <td><code>gma2</code></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "status": "server ready",
  "appType": "gma2"
}
```


##### Message #2

Unsure


##### Payload


<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
      <th>Accepted values</th>
    </tr>
  </thead>
  <tbody>
<tr>
  <td>realtime </td>
  <td>boolean</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>session </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>forceLogin </td>
  <td>boolean</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>worldIndex </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "realtime": true,
  "session": 0,
  "forceLogin": true,
  "worldIndex": 0
}
```


##### Message #3

The desk responding to `dataRequest`


##### Payload


<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
      <th>Accepted values</th>
    </tr>
  </thead>
  <tbody>
<tr>
  <td>realtime </td>
  <td>boolean</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>responseType </td>
  <td>string</td>
  <td></td>
  <td><code>getdata</code></td>
</tr>
<tr>
  <td>data </td>
  <td>array(object)</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>worldIndex </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>prompt </td>
  <td>string</td>
  <td><p>The prompt used by the desk shell.</p>
</td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>promptcolor </td>
  <td>string</td>
  <td></td>
  <td><em>Any</em></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "realtime": true,
  "responseType": "getdata",
  "data": [
    {}
  ],
  "worldIndex": 0,
  "prompt": "[Channel]>",
  "promptcolor": "#808080"
}
```


##### Message #4

The desk responding to `loginRequest`


##### Payload


<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
      <th>Accepted values</th>
    </tr>
  </thead>
  <tbody>
<tr>
  <td>realtime </td>
  <td>boolean</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>responseType </td>
  <td>string</td>
  <td></td>
  <td><code>login</code></td>
</tr>
<tr>
  <td>result </td>
  <td>boolean</td>
  <td></td>
  <td><em>Any</em></td>
</tr>
<tr>
  <td>worldIndex </td>
  <td>integer</td>
  <td></td>
  <td><em>Any</em></td>
</tr></tbody>
</table>


###### Example of payload _(generated)_

```json
{
  "realtime": true,
  "responseType": "login",
  "result": true,
  "worldIndex": 0
}
```






