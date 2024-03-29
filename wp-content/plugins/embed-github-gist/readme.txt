=== Embed GitHub Gist ===
Contributors: dflydev
Tags: github, gist, source, syntax, highlight, highlighter, embed
Requires at least: 2.8.6
Tested up to: 3.1
Stable tag: 0.10

Embed GitHub Gists into WordPress.

== Description ==

Follow here: [Embed GitHub Gist](http://dflydev.com/d2code/wordpress/embed-github-gist-plugin/)

Embed [GitHub](http://github.com/) [Gists](http://gist.github.com) into
WordPress. Provides a shortcode for posts and pages but also has the ability
to embed by hand in the event that a Gist needs to be embedded somewhere in
the page that does not pass through the shortcode filters.

Examples:

`[gist id=546764]`
`[gist id=546764 file=file.txt]`
`[gist id=546764 file=file.txt bump=1]`
`[gist]http://gist.github.com/546764[/gist]`


Cache is implemented with the Transients API to minimize delay on loading
content. Default TTL (time to live) is 86400 seconds or one day.

If `json_decode` is available, the HTML markup for the source code will be
injected into the post inline. This will ensure that the code is available to
spiders and feed readers.

If `json_decode` is not available, the standard GitHub Gist embed script
(JavaScript) is included and the raw content will be added into a `NOSCRIPT`
section wrapped as follows:

`<noscript>`
`<div class="embed-github-gist-source">`
`<code>`
`<pre>raw code here</pre>`
`</code >`
`</div>`
`</noscript>`


= Upcoming features: =

* Option for setting default TTL
* Option to bypass cache entirely
* Option to select CSS loading location preference
* Option to allow for preferring JavaScript over inline HTML
* Shortcode attribute to control inline vs. js preference
* Implement admin interface to control options

== Installation ==

1. Download the plugin zip file
1. Unzip contents of plugin zip file
1. Upload the embed-github-gist directory to the `/wp-content/plugins/` directory
1. Activate the plugin through the 'Plugins' menu in WordPress
1. Start using the plugin by adding Gists to posts!

== Frequently Asked Questions ==

= Can the cache be broken? =

Yes. Use a unique bump value to force cache to update. For instance, if you have
the following:

`[gist id=546764]`

The cache can be broken by specifying a bump value:

`[gist id=546764 bump=1]`

To break the cache again later, change to a new unique bump value:

`[gist id=546764 bump=2]`

= Can I change the TTL on a Gist-by-Gist basis? =

Yes. Specify a TTL (in seconds) like this:

`[gist id=546764 ttl=3600]`

= Can I embed a Gist outside of a post or a page? =

Yes.

`<?php echo embed_github_gist(546764); ?>`

= Can I display a specific file from my gist? =

Ues. You can use the `file` parameter:

`[gist id=546764 file=file.txt]`

== Screenshots ==

No screenshots now!

== Changelog ==

= 0.10 =
 * Bump release ("same as 0.9")

= 0.9 =
 * Fix js link bug. Thanks to wrightlabs.

= 0.8 =
 * Better handle SSL errors. Thanks to gabesumner and CaioProiete.

= 0.7 =
 * Edit to also include $file in cache key (thanks https://github.com/troufster)

= 0.6 =
 * Embed stylesheet is now cached locally by default
 * Fixed small file-bug when using json

= 0.5 =
 * Updates from oncletom (change default settings, works with new HTTPS URL from Gist)

= 0.4 =
 * Bump release ("same as 0.2")

= 0.3 =
 * Bump release ("same as 0.2")

= 0.2 =
 * Added to support passing a Gist URL as the content of the [gist] shortcode.

= 0.1 =
* First release.

== Upgrade Notice ==

= 0.5 =
Now defaults to using cache and embedding HTML directly.

= 0.4 =
No changes from previous release.

= 0.3 =
No changes from previous release.

= 0.2 =
Should have no negative impact.

= 0.1 =
First release.
