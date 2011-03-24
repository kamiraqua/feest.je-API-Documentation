URL:
----
[http://api.feest.je/1/activity/put](http://api.feest.je/1/activity/put)

REQUEST METHOD:
---------------
POST

RATE LIMIT:
-----------
True, see: [rate limiting](<link naar ratelimitpagina>)

AUTHENTICATION REQUIRED:
------------------------
True, see: [authentication](<link naar authenticationpagina>)

SUMMARY:
--------
This call adds an activity to the activity stream.

PARAMETERS:
-----------

**Required:**

 - **id**(*string*), sets the id of of the event or spot of the activity.
 - **type**(*string*), sets the type of the activity. Can be 'checkin' or 'event_checkin'.

**Optional:**

 - **message**(*string*), adds a message to the activity.
 - **push**(*bool*), if true, it pushes the activity to followers, does nothing otherwise.
 - **social**(*string*), sets to which social media the activity should be pushed. All media are separated by an ':'.
 
 
**Extra:**

 - None

RESPONSE FIELDS:
----------------

 -	**_id**, the id of the activity.
 -	**type**, the type of the activity. Can be checkin, king, medal, event_created or event_checkin.

 *If the activity type is "checkin" the following fields will be returned.* 

 -	**message**, shows the message that was put at the moment of checking in.
 -	**points**, shows the points that were earned with this checkin.
 -	**time**, shows the time of the check in(*timestamp*).
 -	**stats**,  shows the stats of the check in, see: [activity stats](<link naar stats pagina>)
 -	**user**, shows information about the user who checked in, see: [activity user](<link naar user pagina>)
 -	**spot**, shows information about the spot where the check in was, see: [activity spot](<link naar spot pagina>)

 *If the activity type is "king" the following fields will be returned.*

 -	**points**, shows the points that were earned by becoming king.
 -	**time**, shows the time that the user became king(*timestamp*).
 -	**user**, shows information about the user who became king, see: [activity king](<link naar user pagina>)
 -	**spot**, shows information about the spot where the user became king, see: [activity spot](<link naar spot pagina>)
 -	**stats**, shows the stats about the becoming of king, see: [activity stats](<link naar stats pagina>) 

 *If the activity type is "medal" the following fields will be returned.*

 -	**points**, shows the points that were earned by earning the medal.
 -	**time**, shows the time at which the medal was earned(*timestamp*).
 -	**user**, shows information about the user who earned the medal, see: [activity user](<link naar user pagina>)
 -	**medal**, shows information about the medal that was earned, see: [activity medal](<link naar medal pagina>)
 -	**stats**, shows the stats of the earning of the medal, see: [activity stats](<link naar stats pagina>)

 *If the activity type is "event_created" the following fields will be returned.*

 -	**points**, shows the points that were earned by creating the event.
 -	**time**, shows the time at which the event was created(*timestamp*).
 -	**user**, shows information about the user who created the event, see: [activity user](<link naar user pagina>)
 -	**event**, shows information about the event that was created, see: [activity event](<link naar event pagina>)
 -	**spot**, shows information about the spot where the event is located, see: [activity spot](<link naar spot pagina>)
 -	**stats**, shows the stats of the creation of the event, see: [activity stats](<link naar stats pagina>) 

 *If the activity type is "event_checkin" the following fields will be returned.*

 -	**message**, shows the message that was put at the moment of checking in.
 -	**points**, shows the points that were earned with this check in.
 -	**time**, shows the time of the check in(*timestamp*)
 -	**stats**, shows the stats of the check in, see: [activity stats](<link naar stats pagina>)
 -	**user**, shows information about the user who checked in, see: [activity user](<link naar user pagina>)
 -	**event**, shows information about the even where the user checked in, see: [activity event](<link naar event pagina>)
 -	**spot**, shows information about the spot where the user checked in, see: [activity spot](<link naar spot pagina>)


EXAMPLES:
---------
 - **user**, [http://api.feest.je/1/activity/get/?user=sinterklaas](http://api.feest.je/1/activity/get/?user=sinterklaas)
 - **spot**, [http://api.feest.je/1/activity/get/?spot=607582b687a1d3af4981e6467301ec20](http://api.feest.je/1/activity/get/?spot=607582b687a1d3af4981e6467301ec20)
 - **medal**, [http://api.feest.je/1/activity/get/?medal=dc157bce80c16939c676b4e81fe318b6](http://api.feest.je/1/activity/get/?medal=dc157bce80c16939c676b4e81fe318b6)
 - **event**, [http://api.feest.je/1/activity/get/?event=113421c0d5bf160a82755f501eb17fe8](http://api.feest.je/1/activity/get/?event=113421c0d5bf160a82755f501eb17fe8)
 - **lat & lng**, [http://api.feest.je/1/activity/get?lat=53.2159195&lng=6.5616468](http://api.feest.je/1/activity/get?lat=53.2159195&lng=6.5616468)
 - **activity**, [http://api.feest.je/1/activity/get?activity=c19ff03f75fa27948e8e15c04aa4e28c](http://api.feest.je/1/activity/get?activity=c19ff03f75fa27948e8e15c04aa4e28c)
 - **type**, [http://api.feest.je/1/activity/get?type=checkin](http://api.feest.je/1/activity/get?type=checkin)
 - **hasphoto**, [http://api.feest.je/1/activity/get?hasphoto=true](http://api.feest.je/1/activity/get?hasphoto=true)

 - **since**, [http://api.feest.je/1/activity/get/?user=sinterklaas&since=1290261031](http://api.feest.je/1/activity/get/?user=sinterklaas&since=1290261031)
 - **until**, [http://api.feest.je/1/activity/get/?user=sinterklaas&until=1290261031](http://api.feest.je/1/activity/get/?user=sinterklaas&until=1290261031)