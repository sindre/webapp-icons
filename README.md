iOS-webapp
==========

iOS webapp testpage for icons and startupscreens

images sizes - pixel
--------
icon-iphone.png - 58x58  
icon-iphone-retina.png - 114x114  
icon-ipad.png - 72x72  
icon-ipad-retina.png - 144x144  
startup-iphone-portrait.png - 320x460  
startup-iphone-portrait@2x.png - 640x920  
startup-iphone5-portrait@2x.png - 640x1096  
startup-ipad-portrait.png - 768x1004  
startup-ipad-portrait@2x.png - 1536x2008  
startup-ipad-landscape.png - 748x1024  
startup-ipad-landscape@2x.png - 1496x2048  

startupscreen Javascript
--------  
		
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

resources
--------
http://cubiq.org/dropbox/startup-image.html  
http://developer.apple.com/library/ios/#documentation/userexperience/conceptual/mobilehig/IconsImages/IconsImages.html  
http://www.mobilexweb.com/blog/iphone-5-ios-6-html5-developers  
