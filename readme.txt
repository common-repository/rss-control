=== RSS Control ===
Contributors: emoxie, mattpramschufer, freemius
Tags: rss control, rss, filter rss
Requires at least: 4.0
Tested up to: 6.6.1
Requires PHP: 7.4
Stable tag: 3.0.10

Control your sites RSS feeds with additional query param options.

== Description ==
RSS Control is a simple plugin which allows you to control several aspects of your RSS feeds through the Feed URL. These work on all feed types including the main feed, category feeds, tag feeds, etc. Below is a list of options that are supported.

== Example ==
> https://yourdomain.com/feed/?cat=89&days_past=7&show_images=true&image_styles=border:4px; border-color:#000; float:left;

The example above will show posts from category 89 from the past 7 days. It will show featured images with a 4px black border floated to the left;

== Options ==
= cat =
This can be either a single category ID or a string of category ids that are separated by commas. You can find out more at https://developer.wordpress.org/reference/classes/wp_query/#category-parameters

**Example:**
> https://yourdomain.com/feed/?cat=-3,10,22
The use of the NEGATIVE in front of the category ID says DO NOT INCLUDE posts from category 3

= category_not_in =
This is an array of category IDs that you do NOT want to show in your feed. You can find out more at https://developer.wordpress.org/reference/classes/wp_query/#category-parameters

**Example:**
> https://yourdomain.com/feed/?category_not_in=3,10
Display posts that do not have any of the category ids 3 and 10

= tag =
This can be either a single tag ID or a string of tag ids that are separated by commas. You can find out more at https://developer.wordpress.org/reference/classes/wp_query/#tag-parameters

**Example:**
> https://yourdomain.com/feed/?tag=-3,10,22
The use of the NEGATIVE infront of the tag ID says DO NOT INCLUDE posts from tag 3

= tag_not_in =
This is an array of tags IDs that you do NOT want to show in your feed. You can find out more at https://developer.wordpress.org/reference/classes/wp_query/#tag-parameters

**Example:**
> https://yourdomain.com/feed/?tag_not_in=3,10
Display posts that do not have any of the two tag ids 3 and 10

= taxonomy =
**INCLUDED IN PREMIUM VERSION**
This the slug of your custom taxonomy.  This needs to be used in conjunction with a taxonomy_term, or a taxonomy_term_not_in parameter to work

**Example:**
> https://yourdomain.com/feed/?taxonomy=genres&taxonomy_term=2
You can NOT use the minus/negative id in taxonomy filtering.

= taxonomy_term =
**INCLUDED IN PREMIUM VERSION**
This can be either a single taxonomy ID or a string of taxonomy ids that are separated by commas.  Must be used in conjunction with taxonomy query parameter

**Example:**
> https://yourdomain.com/feed/?taxonomy=genres&taxonomy_term=2
You can NOT use the minus/negative id in taxonomy filtering.

= taxonomy_term_not_in =
**INCLUDED IN PREMIUM VERSION**
This can be either a single taxonomy ID or a string of taxonomy ids that are separated by commas.  Must be used in conjunction with taxonomy query parameter

**Example:**
> https://yourdomain.com/feed/?taxonomy=genres&taxonomy_term=2&taxonomy_term_not_in=1
You can NOT use the minus/negative id in taxonomy filtering.

= offset =
This is a number which you want to offset the feed by. You can find out more at https://developer.wordpress.org/reference/classes/wp_query/#pagination-parameters

**Example:**
> https://yourdomain.com/feed/?offset=3
This will skip the 3 latest posts and start the feed with post 4

= days_past =
This allows you to have your RSS feed so posts from past X number of days in the past.

**Example:**
> https://yourdomain.com/feed/?days_past=7
This will display the posts from the last 7 days in a feed.

= show_images =
This allows you to display the featured image in the content of the RSS feed.

**Example:**
> https://yourdomain.com/feed/?show_images=true
This will display featured image in the content of the RSS feed. The default image size is 696x385

= image_thumbnail_size =
**INCLUDED IN PREMIUM VERSION**

This allows you to specifically pull a dedicated thumbnail size from WordPress to include in your feed. A better way instead of manually setting width and height.

**Example:**
> http://localhost:10013/feed/?show_images=true&image_thumbnail_size=medium
This will use the medium size image for all of your featured images;


= image_width =
This allows you to set the image width for the featured image

**Example:**
> https://yourdomain.com/feed/?show_images=true&image_width=300
This will set the inline style of the image to have width: 300px;

= image_height =
This allows you to set the image height for the featured image

**Example:**
> https://yourdomain.com/feed/?show_images=true&image_height=300
This will set the inline style of the image to have height: 300px;

= image_size_unit =
This allows you to set the image size unit for the featured image. i.e. px, em, %, fr, etc

**Example:**
> https://yourdomain.com/feed/?show_images=true&image_width=100&image_size_unit=%
This will set the inline style of the image to have a width of 100%

= image_styles =
This allows you to set any additional image inline styles as you would like. These come before the width & height.

**Example:**
> https://yourdomain.com/feed/?show_images=true&image_styles=border:4px; border-color:#000; float:left;
This will set the inline style of the image to have a a black border of 4px and floating the image to the left.

= excerpt_length =
This allows you to control the length of the excerpt you have for the feed in number of WORDS

**Example:**
> https://yourdomain.com/feed/?excerpt_length=20
This will return all of the feed items with the content of only 20 words.

= excerpt_more_text =
This allows you to set the character that appears when content is truncated.  Normally it is either [...] or ...

**Example:**
> https://yourdomain.com/feed/?excerpt_length=20&excerpt_more_text=%5B...Read%20More%5D
This will return all of the feed items with the content of only 20 words ending the content with [...Read More].

= include_title_in_description =
This includes the post title in the description with the title being wrapped in h1 tag.

**Example:**
> https://yourdomain.com/feed/?include_title_in_description=true
This will return all of the feed items with the title present in the description.

= title_tag =
This allows you to change the tag that wraps the title.  I.E. h1, h2, h3, div, span, etc.  DO NOT include the < or >, just the name.

**Example:**
> https://yourdomain.com/feed/?include_title_in_description=true&title_tag=div
This will return all of the feed items with the title present in the description wrapped in a div tag.

= title_styles =
This allows you to apply inline styles to the title tag.

**Example:**
> https://yourdomain.com/feed/?include_title_in_description=true&title_tag=div&title_styles=float:left;%20margin-right:30px;%20border:1px%20solid%20red;
This will return all of the feed items with the title present in the description wrapped in a div tag with the styles added inline.

= include_button =
**INCLUDED IN PREMIUM VERSION**

This allows you to add a button below the excerpt that links to the post

**Example:**
> https://yourdomain.com/feed/?include_button=true
This will output a button that says Read More

= button_styles =
**INCLUDED IN PREMIUM VERSION**

This allows you to apply inline styles to your button.

**Example:**
> https://yourdomain.com/feed/?include_button=true&button_styles=border-radius:200px; background-color:%23e1005f; margin-top:20px;
Please note that if you are using colors like #000 then you will need to encode the # symbol to be <code>%23</code> instead of <code>#</code>

= button_text =
**INCLUDED IN PREMIUM VERSION**

This allows you to change the text on the button from Read More to whatever you would like.

**Example:**
> https://yourdomain.com/feed/?include_button=true&button_text=Click Me

= button_text_styles =
**INCLUDED IN PREMIUM VERSION**

This allows you to apply inline styles to your button text.

**Example:**
> https://yourdomain.com/feed/?include_button=true&button_text_styles=font-size: 18px;
Please note that if you are using colors like #000 then you will need to encode the # symbol to be <code>%23</code> instead of <code>#</code>

= type =
**INCLUDED IN PREMIUM VERSION**

This allows you to specify what type of RSS feed.  Currently, only Google Publisher Center and Google News Showcase is supported.

**Example:**
> https://yourdomain.com/feed/?type=gpc
This will add the needed media name space, along with create full box content in <content:encoded> section and adds featured image as <media:content> element

> https://yourdomain.com/feed/?type=gns
This will add the needed elements that are required by Google News Showcase.


== Frequently Asked Questions ==

= I wish this plugin had XZY feature =

While I try to do my best to incorporate new features all the time, I just implemented a new Feature Request board located at [https://emoxie.com/contact](https://emoxie.com/contact)

= Do you offer support? =

Yes, I do the absolute best I can to support the free version of the plugin.  If you upgrade to the premium version you will have priority support, Google Publisher Center feed, feed url generator, more feed options and much more.

== Installation ==
Upload plugin through Admin->Plugins->Add New or Upload directly to /wp-content/plugins via FTP and activate.

Once activated you can look at Admin->Settings->RSS Control for various options.

== Changelog ==

= 3.0.10 =
* UPDATE - Updated all third-party libraries.

= 3.0.9 =
* FEATURE - Added in Google News Showcase support for Premium users.

= 3.0.8 =
* UPDATE - Updated third-party vendor libraries to latest versions.

= 3.0.7 =
* FEATURE - Added ability to filter posts just for current month.
* FEATURE - Added images as media elements


= 3.0.6 =
* UPDATE - Removed the source=news.google.com parameter from GPC feeds as Google now no longer allows this.

= 3.0.5 =
* FEATURE - Added ability to change the order and order by values
* FEATURE - Added the ability to remove the excerpt
* UPDATE - Updated to latest version of vendor packages

= 3.0.4 =
* UPDATE - Google Analytics will not track encoded UTM variables, and without encoding the variables the RSS feeds will be invalid, so we are forced to remove the UTM tracking from feed URL and replace with a single ?source=news.google.com instead.

= 3.0.3 =
* BUG FIX - Updated UTM parameters in feed URLs to not be encoded.  Previously urls with UTM variables were being encoded which didn't allow for them to be picked up properly.

= 3.0.2 =
* BUG FIX - Fixed issue with image_thumbnail_size on edge case setups.

= 3.0.1 =
* BUG FIX - Fixed issue when using tag__not_in and category__not_in.

= 3.0.0 =
* UPDATE - Major Overhaul includes updated how-to section and optimized code.
* FEATURE - Implemented RSS Feed URL Generator for Premium Users
* UPDATE - Updated all vendor libraries to their latest versions

= 2.0.12 =
* UPDATE - Automatically append UTM variables to permalinks when using the GPC feed type.
* UPDATE - Updated third-party vendor libraries.

= 2.0.11 =
* UPDATE - Updated admin help docs to include link to urlencoder.org
* UPDATE - Added a default 10px margin top to email buttons.

= 2.0.10 =
* FEATURE - Added the ability to filter feed by custom taxonomies
* FEATURE - Added the ability to include a button to rss excerpts
* UPDATE - Updated to latest Freemius SDK

= 2.0.9 =
* FEATURE - Added the ability to specify type of feed for Google Publisher Console.
* FEATURE - Added in extra options for GPC feeds, namespaces, media elements, and full content

= 2.0.8 =
* UPDATE - Updated to the latest Freemius SDK

= 2.0.7 =
* UPDATE - Updated to the latest Freemius SDK

= 2.0.6 =
* UPDATE - Updated to the latest Freemius SDK
* BUG FIX - Fixed php warnings messages

= 2.0.5 =
* UPDATE - When displaying title in description include the permalink to link back to post
* BUG FIX - Adjusted priority on filter to account for when excerpt length and title in description are both active.

= 2.0.4 =
* FEATURE - Added in ability to include title in description
* FEATURE - Added in ability to change tag wrapping title
* FEATURE - Added in ability to apply inline styles to title tag
* UPDATE - Updated to latest Freemius SDK

= 2.0.3 =
* FEATURE - Added in ability to set the excerpt length
* FEATURE - Added in ability to set the more text when excerpts get truncated

= 2.0.2 =
* Implemented Freemius

= 2.0.1 =
* Initial WP.org version created and pushed to public

== Upgrade Notice ==