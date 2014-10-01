Standard meta tags and defined names
========
These tags are W3C standard tags, or as W3C *defined meta names*.

``` <title> ```
-----

While technically not a ```<meta>``` tag it represents the title of the document/page. The contents of this tag are generally shown as the title in search results (and of course in the user's browser as titles in tabs).

``` <meta charset="UTF-8"> ```
---------
The charset attribute specifies the character encoding for the HTML document.

Although standardization would require UTF-8 to be default when in HTML5 mode, most of the browsers will default to `windows-1252` or `iso-8859-1` equivalent so it's advised to include this attribute.

In older versions of Internet Explorer, not setting the charset could lead to [UTF-7 XSS vulnerability].

This tag should be set in the first 512 bytes.

In HTML 4 complete tag was:

```html
<meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
```

#### Example

```html
<meta charset="UTF-8"> <!-- It's only logical -->
```


More about this tag:

 - [MDN: meta#attr-charset] Has recommendations about this tag
 - All [character sets] - IANAs reference list. (*But do use UTF-8*)

[MDN: meta#attr-charset]:https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta#attr-charset
[character sets]:http://www.iana.org/assignments/character-sets/character-sets.xhtml
[UTF-7 XSS vulnerability]:https://code.google.com/p/doctype-mirror/wiki/ArticleUtf7

`<meta name="description" content="">`
-----------
This tag provides a short description of the page. In some situations this description is used as a part of the snippet shown in the search results. Your actual description literal is the value of the *content* attribute.

The optimal length of the description varies. Google uses pixel count to cut off the description when it's too long. Don't count. If you can keep it at 100-110 chars, even better test it with Google Snippets Tool. Don't use quotes in the description, apply escaping logic.

#### Example

```html
<meta name="description" content="Meta tags repository contains a comprehensive list of meta tags for you to read, learn and implement in your web pages and web applications.">
```

More about this tag:

 - Google's advice on how to [create good meta descriptions]

[create good meta descriptions]:https://support.google.com/webmasters/answer/35624?rd=1#1

`<meta name="generator" content="">`
----------
The generator meta tag is used to denote software that generated the document. It's usually found in various CMS implementations to display the CMS that runs the website. Most notable user of the generator tag is Wordpress.

#### Example

```html
<meta name="generator" content="GitHub's Markdown parser">
```
`<meta name="application-name" content="">`
----------
This value represents the name of the web application. The value must be a short free-form string giving the name of the Web application that the page represents.

If the page is not a Web application, the application-name metadata name must not be used. Translations of the Web application's name may be given, using the lang attribute to specify the language of each name.

There must not be more than one meta element with a given language and with its name attribute set to the value application-name per document.

Microsoft implements it for pinning sites in Internet Explorer and Windows 8+ along with its proprietery tags.

#### Example
```html
<meta name="application-name" content="GitHub">
```



`<meta name="author" content="">`
----------
The author meta tag is a meta tag used to define the author of the content on the web page. This meta tag allows you to credit the writer(s) of the content on the page.

The value of this tag is disputed nowadays. It's recommended to leave this tag out of your page if you have no specific requirement for its occurance.

#### Example

```html
<meta name="author" content="Marko Kazhich">
```


`<meta name="keywords" content="">`
----------
A meta keywords tag is supposed to be a brief and concise list of the most important themes of your page. The value of implementing this element in the page is highly disputed.

[Google doesn't use keywords meta], and still it's a general recommendation not to leave it blank. However, it's noted that [Baidu takes keywords in account], so if you have a large visit count from China, think about putting `keywords` to use.

[Google doesn't use keywords meta]:http://googlewebmastercentral.blogspot.com/2009/09/google-does-not-use-keywords-meta-tag.html
[Baidu takes keywords in account]:http://searchengineland.com/the-b2b-marketers-guide-to-baidu-seo-180658

#### Example

```html
<meta name="keywords" content="meta,tags,html,meta tags,tags list,list tags,keywords,seo">
```

HTTP-Equiv
=========
These tags are used to simulate a HTTP response in various ways.

`<meta http-equiv="refresh" content="">`
--------
This meta tag is used as a refresh/URL redirection method. It's use is extremely rare nowadays. Use of meta refresh is discouraged by the W3C.

*Note*: I used this meta tag inside an IE conditional comment to redirect users of IE 8 and lower to a lite version of a website. In any case, when thinking about using this, be sure to talk to someone first.

#### Example

```html
<meta http-equiv="refresh" content="0; url=http://marxo.me">
```
Redirects to `http://marxo.me` upon page load.

```html
<meta http-equiv="refresh" content="10">
```

Refreshes the current page after 10 seconds.

**More about this tag:**

 - [Meta refresh](http://en.wikipedia.org/wiki/Meta_refresh) on Wikipedia is a great resource
 - W3C has specification on [http-equiv=refresh](http://www.w3.org/TR/html-markup/meta.http-equiv.refresh.html)


Extension tags
=========
These tags are extension or unofficial and their usage is no standardized as part of the HTML standard, however some or most of them have been accepted as [MetaExtensions](https://wiki.whatwg.org/wiki/MetaExtensions) by @whatwg

`<meta name="robots" content="">`
----------
This attribute, supported by several major search engines, including Google, Yahoo! and Bing, controls whether search engine spiders are allowed to index a page, or not, and whether they should follow links from a page, or not. The attribute can contain one or more comma-separate values. The `noindex` value prevents a page from being indexed, and `nofollow` prevents links from being crawled. Other values recognized by one or more search engines can influence how the engine indexes pages, and how those pages appear on the search results. These include `noarchive`, which instructs a search engine not to store an archived copy of the page, and `nosnippet`, which asks that the search engine not include a snippet from the page along with the page's listing in search results.

Defaults to: `index,follow`

**Values available:**

 - `none` - Alias for `noindex,nofollow`
 - `index`,`noindex` - Show (or don't) the page in search results
 - `noimageindex` - Disable image indexing (works with Googlebot)
 - `follow`, `nofollow` - Follow (or don't) the links on this page
 - `archive`, `noarchive` - Disable (or don't) a cached copy of the page
 - `nocache` - Same as `noarchive` but used by Bing
 - `nosnippet` - Prevents the search engine from showing the snippet in results.
 - `noodp` - Blocks search engines from using the description for this page in DMOZ (aka ODP) as the snippet for your page in the search results.
 - `noydir` - Blocks Yahoo! from using the description for this page in the Yahoo! directory as the snippet for your page in the search results. No other search engines use the Yahoo! directory for this purpose, so they don’t support the tag.

#### Example

```html
<meta name="robots" content="noindex,nofollow">
```

`<meta name="viewport" content="">`
---------
Provides a way for documents to specify (using markup rather than CSS) the size, zoom factor, and orientation of the viewport that is used as the base for the document's initial containing block.

[CSS Device Adaptation](http://www.w3.org/TR/css-device-adapt/) specification suggest `@viewport` to be used instead of the tag, however, until fully implemented, you should use the meta tag.

**Options available:**

 - `width` - Sets the width of the initial viewport
 - `height` - Sets the height of the initial viewport
 - `initial-scale` - Sets the inital zoom (*numeric value*)
 - `minimum-scale`- Sets the minimum available zoom level
 - `maximum-scale` - Sets the maximum available zoom level
 - `user-scalable` - Enable or disable user zooming (*boolean value*)

#### Example

Set the width of initial view to 480px, initial zoom to 200% and let user control the scale/zoom.
```html
<meta name="viewport" content="width=480, initial-scale=2.0, user-scalable=1">
```

or more commonly used:

```html
<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
```

Read the CSS Device Adaptation specification to learn more about options and values.

More about this tag:

 - [An introduction to meta viewport and @viewport](https://dev.opera.com/articles/an-introduction-to-meta-viewport-and-viewport/) by @andreasbovens

`<meta name="bitcoin" content="">`
---------
Allows users to declare their BTC address which can be used when donating to the user. The community suggests using `bitcoin:` BIP-21 URI schema as a better approach.

[FireCoin](http://www.youtube.com/watch?v=E31bcPr2gr8) for Firefox implements this tag.

#### Example

```html
<meta name="bitcoin" content="1KVmMLp5MHm1R3iM7Kprp1rUShinzLVtrV">
```

More about this tag:

 - [Bitcoin meta tag](https://jokenetwork.de/faq/bitcoin/) description with links to discussion topics

## Google specific tags
Google has a page with a list of [tags they supports](https://support.google.com/webmasters/answer/79812?hl=en) so you can keep your info up to date.

`<meta name="google" content="notranslate">`
---------
This meta tag tells Google that you don't want Google Translate to provide a translation for this page.

>When we recognize that the contents of a page are not in the language that the user is likely to want to read, we often provide a link to a translation in the search results. In general, this gives you the chance to provide your unique and compelling content to a much larger group of users. However, there may be situations where this is not desired.

#### Example

```html
<meta name="google" content="notranslate">
```

Content attribute in this tag doesn't have other possible values.

`<meta name="googlebot" content="">`
----------
Same as `robots` only applies to Googlebot.

### Example
```html
<meta name="googlebot" content="noimageindex">
```
For content attribute values check `robots` tag.
## Microsoft specific tags