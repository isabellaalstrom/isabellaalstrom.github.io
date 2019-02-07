One of the most important things in a home automation setup is presence detection. You can do so much and so much can fail if it doesn't work properly.

### Presence detection methods I use
* [iOS app for Hass](https://itunes.apple.com/us/app/home-assistant-companion/id1099568401?mt=8) - gps
* [Nmap](https://www.home-assistant.io/components/device_tracker.nmap_tracker/) - wifi
* [BT tracking](https://github.com/andrewjfreyer/monitor) - bluetooth

None of these methods are 100 % on their own (even though the iOS app have been almost there since the release of v1.5). For example the wifi on phones tend to go into sleep mode when not used. Add some automations to that and you have all your lights go on as if you just came home, in the middle of the night.
This is why I use three different methods, combining them into one sensor that I then use for my automations.

Rudimentary this can be done with putting all trackers in a group, the group will always be "home" if one of the devices is home. But I wanted more. I read [Phil Hawthornes blog post about presence](https://philhawthorne.com/making-home-assistants-presence-detection-not-so-binary/) and tried his idea out. It still wasn't 100 %, even though having your automations fire at "Just arrived" instead of "Home" makes a difference (read the blog post if you don't understand what I'm talking about). I needs some more logic to it.

### Better presence detection
I've been using the ["Better presence" Appdaemon app from helto4real](https://github.com/helto4real/hassio/tree/master/appdaemon/apps/presence), that knits gps, bt and wifi tracking together into one tracker, with some advanced logic. For example bt and wifi trackers immediately sets the combined tracker to "Just arrived" if you are away and one of them shows home. If both of them are away, but gps is still home, it checks how long ago it was that the gps tracker last reported you were home before deciding what to do. This kind of logic is what gets it as close to 100 % as possible. Things can still go wrong of course, it's "only" technology, but I think this is about as good as it gets.

The same guy recently released a beta of an Hass.io addon that does the same thing. Get it here: [A better presence](https://github.com/helto4real/hassio-add-ons/tree/master/presence).

I'm trying it out right now!