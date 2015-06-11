# Phonegap--Generic-Boilerplate
A generic boilerplate for constructing PhonegapApps

There are two (2) big differences to note between HTML5 and previous versions of HTML, and one (1) important point about Phonegap.

The first is the new opening element for [*html5*](http://www.w3schools.com/tags/tag_doctype.asp) is:

```
	<!DOCTYPE html>
```

The second important element sets the device parameters. It tells the mobile device I know how to detect the device screen size (and I don't assume the screen has a width of 1024px). Mozilla has a [bit to say](https://developer.mozilla.org/en-US/docs/Mozilla/Mobile/Viewport_meta_tag), but you'll also want to read [this technical essay](http://www.quirksmode.org/blog/archives/2010/04/a_pixel_is_not.html) from PPK. That element is:

```
	<meta name="viewport" content="width=device-width">
```

The third is the listener. Many beginners trip on this part. It is important for this listener to be added. It allows the phonegap library to prepare all the devices on the phone before you call any of the libraries. Details are available in the [phonegap documentation](http://docs.phonegap.com/en/4.0.0/cordova_events_events.md.html#deviceready)

```
	// Wait for PhoneGap to load
	document.addEventListener("deviceready", onDeviceReady, false);
	//
	function onDeviceReady() {
```

If however, you are not going to use the hardware on the mobile device, you should at least have an [onload=loaded()](http://www.w3schools.com/jsref/event_onload.asp); such as,

```
	<body onload=loaded()>
```