Standard HTML meta tags
========

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

`<meta name="robots" content="">`
----------
This attribute, supported by several major search engines, including Google, Yahoo! and Bing, controls whether search engine spiders are allowed to index a page, or not, and whether they should follow links from a page, or not. The attribute can contain one or more comma-separate values. The `noindex` value prevents a page from being indexed, and `nofollow` prevents links from being crawled. Other values recognized by one or more search engines can influence how the engine indexes pages, and how those pages appear on the search results. These include `noarchive`, which instructs a search engine not to store an archived copy of the page, and `nosnippet`, which asks that the search engine not include a snippet from the page along with the page's listing in search results.

Defaults to: `index,follow`

**Values available:**
 - `none` - Shortcut for `noindex,nofollow`
 - `index`,`noindex` - Show (or don't) the page in search results
 - `noimageindex` - Disable image indexing (works with Google)
 -
 - `follow`, `nofollow` - Follow (or don't) the links on this page
 - `archive`, `noarchive` - Disable (or don't) a cached copy of the page
 - `nocache` - Same as `noarchive`, used by Bing
 - `nosnippet` - Prevents the search engine from showing the snippet in results.
 - `noodp` - Blocks search engines from using the description for this page in DMOZ (aka ODP) as the snippet for your page in the search results.
 - `noydir` - Blocks Yahoo! from using the description for this page in the Yahoo! directory as the snippet for your page in the search results. No other search engines use the Yahoo! directory for this purpose, so they don’t support the tag.

#### Example

```html
<meta name="robots" content="noindex,nofollow">
```