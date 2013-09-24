# FitVids.js for Kaltura
Kaltura doesn't have any tutorial (that I could find) on using their embed code in a responsive design, and FitVids wasn't working out-of-the-box with Kaltura. So, I dug a little and found only a couple small details that were hindering it. Also, FitVids needs to be run in Kaltura's callback function in the `kWidget.embed()` method:

```javascript
kWidget.embed({
	'targetId': 'myEmbedTarget',
	'wid': '_{partnerId}',
	'uiconf_id' : '{uiConfId}',
	'entry_id' : '{entryId}',
	flashvars: {},
	'readyCallback': function() { $("{YOUR_VIDEO_CONTAINER}").fitVids(); }
});
```

Easy, peasy.

I don't believe my changes to FitVids will cause it to break for using with any other video vendor it supports (YouTube, Vimeo, etc.), but I have not tested it thoroughly. (see the History on the js file to see my changes)
