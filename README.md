Standard HTML meta tags
========

``` <title> ```
-----

While technically not a ```<meta>``` tag it represents the title of the document/page.

``` <meta charset="UTF-8"> ```
---------
The charset attribute specifies the character encoding for the HTML document.

Although standardization would require UTF-8 to be default when in HTML5 mode, most of the browsers will default to `windows-1252` or `iso-8859-1` equivalent so it's advised to include this attribute.

In older versions of Internet Explorer, not setting the charset could lead to [UTF-7 XSS vulnerability].

This tag should be set in the first 512 bytes.

In HTML 4 complete tag was:

```<meta http-equiv="Content-Type" content="text/html;charset=UTF-8">```

#### Example of use

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

`<meta name="robots" content="">`
----------
