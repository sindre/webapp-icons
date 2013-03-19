iOS-webapp
==========

iOS webapp testpage for icons and startupscreens

Startupscreen Javascript
--------

<script>		
	(function (w, d){
		var
		nav = w.navigator,
		pixelRatio = w.devicePixelRatio === 2 ? 'high-resolution' : '',
		device = (/ipad/i).test(nav.platform) ? 'ipad' : (/iphone|ipod/i).test(nav.platform) ? 'iphone' : '',
		orientation = device == 'ipad' && w.orientation % 180 ? 'landscape' : 'portrait';
		if(device == 'iphone' && w.screen.height==568) {
			device = 'iphone5';
		}
	if ( device === '' ) return;
	if ( device == 'iphone' || device == 'iphone5' || nav.standalone ) {
		d.write(device + '-' + orientation + '-' + pixelRatio);
	} else {
		d.write(device + '-' + orientation + '-' + pixelRatio);
	}
	})(window, document);
</script>

Links:
--------
http://cubiq.org/dropbox/startup-image.html 
http://developer.apple.com/library/ios/#documentation/userexperience/conceptual/mobilehig/IconsImages/IconsImages.html
http://www.mobilexweb.com/blog/iphone-5-ios-6-html5-developers