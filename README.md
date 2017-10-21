# ISS_Tracker

This website provides the current location of the international space station (ISS). Additionally, the user can enter his or her location and find the next five best times to view the ISS. This is accomplished using NASA's API which delivers the coordinates of the ISS and also the next 100 times when the ISS's altitude will be greater than 10 degrees over the horizon (90 degrees being the Zenith). The coordinates of the ISS are fed directly into Google's maps API and updated every 120 seconds.

All times are given in the user's inputed location's local time. This is accomplished by using Google's timezone API to find the hour difference from GMT given the user's inputted location and account for daylight savings time. Using moment.js, these hours are converted to milliseconds and added to the Unixtime of when the ISS will pass overhead. This is done for the top five passes by longest duration above 10 degrees over the horizon. Nested promises are used to manage the call stream.

Furthermore, a weather API and a sunset API is used to determine if the sky will be clear and it will be night for the best possible viewing conditions. The weather API takes the user location and time of passover as arguments and delivers the weather. The Sunset api will provide a threshold response, day or night, for if the local time of the overhead pass is before astronomical sunrise and after astronomical sunset respecively.

I would love to include an automatic text with this application and an algorithm to rank the best overhead pass time by weather, visibility, and duration.

