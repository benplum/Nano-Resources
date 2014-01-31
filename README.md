#Nano-Resources

Pico Plugin for handling JS and CSS resources.

Includes [CssMin](http://code.google.com/p/cssmin/) and [JShrink](https://github.com/tedivm/JShrink).

### Installation

Start by moving the <code>plugins/nano_resources.php</code> file and <code>vendor/nano_resources</code> directory into your existing Pico install. Then define the resources to combine, minify and cache in the <code>config</code> array.

### Configuration

	$config["nano_resources"] = array(
		"css" => array(
			/**
			 *	An array of files to generate. For example, "site" will produce
			 *	"site.css" file available at http://site.com/css/site.css
			 */
			"files" => array(
				/**
				 *	An array of the source files to combine, relative to the
				 *	current theme's directory. 
				 */
				"site" => array(
					"reset.css",
					"main.css"
				)
			),
			/**
			 *	An array of key->value pairs to replace on render. For example
			 *	"key" will replace all instances of '$key' with "value".
			 */
			"vars" => array(
				"key" => "value"
			),
			/**
			 *	Flag to minify output
			 */
			"minify" => true
		),
		"js" => array(
			/**
			 *	An array of files to generate. For example, "site" will produce
			 *	"site.js" file available at http://site.com/js/site.js
			 */
			"files" => array(
				/**
				 *	An array of the source files to combine, relative to the
				 *	current theme's directory. 
				 */
				"site" => array(
					"library.js",
					"main.js"
				)
			),
			/**
			 *	An array of key->value pairs to replace on render. For example
			 *	"key" will replace all instances of '$key' with "value".
			 */
			"vars" => array(
				"key" => "value"
			),
			/**
			 *	Flag to minify output
			 */
			"minify" => true
		),
		/**
		 *	Flag to ignore caching and force re-render
		 */
		"debug" => false
	);

### Usage

Once defined, you can request the resources relative to their type and filename:

	http://site.com/css/site.css
	
	http://site.com/js/site.js