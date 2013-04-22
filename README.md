tweet-plotter
=============

    Plots tweets in real-time using Google maps - Node.js.

    Tweet-plotter subscribes to a particular keyword and shows tweets in real-time. 
    It uses the geo-coding service from Google to lookup the user address before plotting. 

    So the sequence of events are like so: 

    1)  Receives an event from Twitter using the streaming API.
    2)  Looks up the address using Geo-coding api. Note that there is a limit to this 2500 requests per day for free usage.
    3)  Send the event over websockets to the browser. 
    4)  Browser plots the tweet on Google maps using the latitude and longitude information looked up already from Google Maps.

    TODO:
    -------------
    1)  When the lat, lon info is in the tweet don't lookup the address using geo-coding service.
    2)  When using web sockets it now services only the most recent client. Make it broadcast to all clients.
    3)  Make the keywords per user. Currently it is hard coded in the streamer. Twitters event streaming API does not let more than 
        one connection i guess. 
    
