# Events emitted by client & processed by server

_* Note: All server side events returning data to the client include properties: *_
  * logged_in: Boolean
  * user: object containing user info of loggedin user (per socket)

## source: videoController:

### cs-init 
  _data object transmitted to server:_
  * videoid: String

**Todo : add**
  * videotitle: String
  * videoduration: Number

### cs-comment 
_data object transmitted to server:_
  * username: String,
  * userId: ObjectID,
  * videoId: String,
  * text: String,
  * timestamp: Number

## source: homeController:

### cs-movielist
  * data object transmitted to server:
  * non   


# Events emitted by server & processed by client

## source: sockets/index.js

### sc-init
  _data object transmitted to client:_
  * videoId: String,
  * videoTitle: String, (default: unknown title)
  * comments: Array of comment objects (see below for comment new)
  * commentCount: Number (default: 0 as of now)

### sc-comment new
  _data object transmitted to client:_
  * videoid: String,
  * username: String,
  * text: String,
  * votes: Number,
  * timestamp: Number

### sc-comment error
  _data object transmitted to client:_
  * error: String

### sc-movielist
  _data object transmitted to client:_
  * videos: Object with Array of video objects
