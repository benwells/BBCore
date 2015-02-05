# BBCore

[![Build Status](https://travis-ci.org/bombbomb/BBCore.svg?branch=master)](https://travis-ci.org/bombbomb/BBCore) [![Code Climate](https://codeclimate.com/github/bombbomb/BBCore/badges/gpa.svg)](https://codeclimate.com/github/bombbomb/BBCore) [![Test Coverage](https://codeclimate.com/github/bombbomb/BBCore/badges/coverage.svg)](https://codeclimate.com/github/bombbomb/BBCore)

A Javascript API enabling the use of BombBomb's video recording, sending and more!

Use of BBCore requires only a recent version of jQuery and bbcore.js.

Running the tests requires [grunt-cli](https://github.com/gruntjs/grunt-cli). Then run `grunt` to test and miniaturize.
## Usage Examples!

To begin, include the `BBCore` and `jQuery` libraries in your html:

```html
<script type="text/javascript" src="//ajax.googleapis.com/ajax/libs/jquery/1.10.2/jquery.min.js"></script>
<script type="text/javascript" src="/app/js/bbcore-min.js"></script>
```

Then instantiate BBCore:

```javascript
var bb = new BBCore({ accessToken: '<your api key>'});
```


### Capture a video with user's webcam
Then create a video recorder, and save a recording, being by calling `startVideoRecorder()` specifying a css selctor `target` into which you would like the recorder to appear.

```javascript
bb.startVideoRecorder({ target: '#recorderDiv'}, function (vidInfo) {
 if (confirm('Is this the take you would like to save?')) {
     bb.saveRecordedVideo('Our video!', vidInfo.videoId, vidInfo.filename, function (data) {
         alert('Your video has been saved!');
     });
 }
});
```


### Send a video in an email through BombBomb
To send that video in your default template, use `videoQuickSend()`

```javascript
bb.videoQuickSend({
    subject: 'Your Subject Line',
    video_id: vidInfo.videoId, // saved from the earlier call
    email_addresses: 'test@emailaddress.com',
    mobile_message: "Simple message to include"

}, function (data) {
    alert("You've sent a video! " + data.info);
});
```
# BBCore





* * *

### BBCore.isAuthenticated() 

**Returns**: `boolean | *`


### BBCore.sendRequest(metho, params, success, success) 

Sends a request to the specified method of the [BombBomb API](//bombbomb.com/api)

**Parameters**

**metho**: `string`, The method name to call

**params**: `array`, The parameters to send with the request

**success**: `responseSuccess`, A callback when the request succeeds

**success**: `responseSuccess`, A callback when the request fails



### BBCore.videoQuickSend() 



### BBCore.deleteVideo(videoId, success) 

Deletes a Video

**Parameters**

**videoId**: `string`, Deletes a Video

**success**: `responseSuccess`, Deletes a Video



### BBCore.getLists(success) 

Retrieves Contact Lists

**Parameters**

**success**: `responseSuccess`, Retrieves Contact Lists



### BBCore.createList(listName, success) 

Creates a Contact List and returns the Guid

**Parameters**

**listName**: `string`, Creates a Contact List and returns the Guid

**success**: `responseSuccess`, Creates a Contact List and returns the Guid



### BBCore.getEmails(listName, success) 

Retrieves a list of Email

**Parameters**

**listName**: `string`, Retrieves a list of Email

**success**: `responseSuccess`, Retrieves a list of Email



### BBCore.getContact(contactId, success) 

Retrieves a Contact

**Parameters**

**contactId**: `string`, Retrieves a Contact

**success**: `responseSuccess`, Retrieves a Contact



### BBCore.getListContacts(listId, success) 

Retrieves Contacts from a Contact List

**Parameters**

**listId**: `string`, Retrieves Contacts from a Contact List

**success**: `responseSuccess`, Retrieves Contacts from a Contact List



### BBCore.addContact(contact, success) 

Adds a Contact to a Contact List

**Parameters**

**contact**: `contact`, Adds a Contact to a Contact List

**success**: `responseSuccess`, Adds a Contact to a Contact List



### BBCore.bulkAddContacts(opts, success) 

Adds a batch of Contacts

**Parameters**

**opts**: `object`, Adds a batch of Contacts

**success**: `responseSuccess`, Adds a batch of Contacts



### BBCore.add(contact) 

add

**Parameters**

**contact**: `contact`, add

**Returns**: `contacts`


### BBCore.add(video) 

**Parameters**

**video**: `video`

**Returns**: `videos`



* * *










