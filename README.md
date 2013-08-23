iOS-webapp
==========

iOS webapp testpage for icons and startupscreens

startupscreen Javascript
--------  
		
	if (window.screen.height==568) { // iPhone 4" Webapp Fullsize
		document.querySelector("meta[name=viewport]").content="width=320.1"; 
	}
	(function (w, d){
		var
		nav = w.navigator,
		gfxpath = '';
		pixelRatio = w.devicePixelRatio === 2 ? '@2x' : '',
		device = (/ipad/i).test(nav.platform) ? 'ipad' : (/iphone|ipod/i).test(nav.platform) ? 'iphone' : '',
		orient = device == 'ipad' && w.orientation % 180 ? 'landscape' : 'portrait';
		if(device == 'iphone' && w.screen.height==568) {
			device = 'iphone5';
			d.querySelector("meta[name=viewport]").content="width=320.1"; 
		}
		if ( device === '' ) return;
		if ( device == 'iphone' || device == 'iphone5' || nav.standalone ) {
			d.write('<link rel="apple-touch-startup-image" href="' + gfxpath + 'startup-' + device + '-' + orient + pixelRatio + '.png"' + ( device == 'ipad' ? ' media="screen and (orientation:' + orient + ')"' : '' ) + '>');
		} else {
			d.write('<link rel="apple-touch-startup-image" href="' + gfxpath + 'startup-' + device + '-landscape' + pixelRatio + '.png" media="screen and (orientation:landscape)">');
			d.write('<link rel="apple-touch-startup-image" href="' + gfxpath + 'startup-' + device + '-portrait' + pixelRatio + '.png" media="screen and (orientation:portrait)">');
		}
	})(window, document);

resources
--------
http://cubiq.org/dropbox/startup-image.html  
http://developer.apple.com/library/ios/#documentation/userexperience/conceptual/mobilehig/IconsImages/IconsImages.html  
http://www.mobilexweb.com/blog/iphone-5-ios-6-html5-developers  
