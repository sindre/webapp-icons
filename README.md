iOS-webapp
==========

iOS webapp testpage for icons and startupscreens - <a href="http://sindre.at/ios-webapp/">Demo</a>

images sizes - pixel (device)
--------
icon-iphone.png - 58x58 (iPhone 3/3s / iPod Touch)  
icon-iphone-retina.png - 114x114 (iPhone 4/4s/5 / iPod Touch)  
icon-ipad.png - 72x72 (iPad / iPad 2)  
icon-ipad-retina.png - 144x144 (iPad 3 / ipad mini)  
startup-iphone-portrait.png - 320x460 (iPhone 3Gs / iPod Touch)  
startup-iphone-portrait@2x.png - 640x920 (iPhone 4/4s / iPod Touch)  
startup-iphone5-portrait@2x.png - 640x1096  (iPhone 5 / iPod Touch)  
startup-ipad-portrait.png - 768x1004 (iPad / iPad 2)  
startup-ipad-portrait@2x.png - 1536x2008 (iPad 3 / ipad mini)  
startup-ipad-landscape.png - 748x1024 (iPad / iPad 2)  
startup-ipad-landscape@2x.png - 1496x2048 (iPad 3 / ipad mini)  

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
