Web App icons und startupscreens
==========

Web App icons und startupscreens for iOS and Android

Web App testpage for icons and startupscreens - <a href="http://sindre.at/lab/ios-webapp/">Demo</a>

icon sizes - pixel (device)
--------
icon196.png - 196x196 (Web App Icon Android Chrome)
icon58.png - 58x58 (non-retina iPhone pre iOS 7) 
icon72.png - 72x72 (non-retina iPad pre iOS 7)  
icon76.png - 76x76 (non-retina iPad iOS 7)   
icon114.png - 114x114 (retina iPhone pre iOS 7)  
icon120.png - 120x120 (retina iPhone iOS 7) 
icon144.png - 144x144 (retina iPad pre iOS 7)  
icon152.png - 152x152 (retina iPad iOS 7)  
startup-iphone-portrait.png - 320x460 (non-retina iPhone)  
startup-iphone-portrait@2x.png - 640x920 (retina iPhone)  
startup-iphone5-portrait@2x.png - 640x1096  (retina iPhone5+)  
startup-ipad-portrait.png - 768x1004 (non-retina iPad)  
startup-ipad-portrait@2x.png - 1536x2008 (retina iPad / iPad mini)  
startup-ipad-landscape.png - 748x1024 (non-retina iPad)  
startup-ipad-landscape@2x.png - 1496x2048 (retina iPad / iPad mini)  

icon HTML code (put into HEAD)
--------  
	<!-- Web App Icon Android Chrome -->
	<link rel="shortcut icon" href="icon196.png" sizes="196x196" />
	<!-- non-retina iPhone pre iOS 7 -->
	<link rel="apple-touch-icon" href="icon58.png" sizes="58x58" />
	<!-- non-retina iPad pre iOS 7 -->
	<link rel="apple-touch-icon" href="icon72.png" sizes="72x72" />
	<!-- non-retina iPad iOS 7 -->
	<link rel="apple-touch-icon" href="icon76.png" sizes="76x76" />
	<!-- retina iPhone pre iOS 7 -->
	<link rel="apple-touch-icon" href="icon114.png" sizes="114x114" />
	<!-- retina iPhone iOS 7 -->
	<link rel="apple-touch-icon" href="icon120.png" sizes="120x120" />
	<!-- retina iPad pre iOS 7 -->
	<link rel="apple-touch-icon" href="icon144.png" sizes="144x144" />
	<!-- retina iPad iOS 7 -->
	<link rel="apple-touch-icon" href="icon152.png" sizes="152x152" />

iOS startupscreen javascript
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

Web App HTML code (put into HEAD)
--------
	<!-- Web App Android Chrome -->
	<meta name="mobile-web-app-capable" content="yes" />
	<!-- Web App iOS -->
	<meta name="apple-mobile-web-app-capable" content="yes" />

one icon for all sizes
--------
Using only one Apple Touch Icon saves time and is enough in some cases.   
https://github.com/h5bp/html5-boilerplate/commit/71ca9fb7a06bfcd2359c924ca261d41d1dd03e8d

resources
--------
http://cubiq.org/dropbox/startup-image.html  
http://developer.apple.com/library/ios/#documentation/userexperience/conceptual/mobilehig/IconsImages/IconsImages.html  
http://www.mobilexweb.com/blog/iphone-5-ios-6-html5-developers  
http://www.mobilexweb.com/blog/safari-ios7-html5-problems-apis-review   
http://www.mobilexweb.com/blog/home-screen-web-apps-android-chrome-31   
https://github.com/h5bp/html5-boilerplate/commit/71ca9fb7a06bfcd2359c924ca261d41d1dd03e8d   
https://npmjs.org/package/grunt-favicons
