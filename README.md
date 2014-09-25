Standard HTML meta tags
========

Title ``` <title> ```
---------

While technically not a ```<meta>``` tag it represents the title of the document/page.

Charset ``` <meta charset="UTF-8"> ```
---------
The charset attribute specifies the character encoding for the HTML document.

Although standardization would require UTF-8 to be default when in HTML5 mode, most of the browsers will default to `windows-1252` or `iso-8859` equivalent so it's advised to include this attribute.

In older versions of Internet Explorer, not setting the charset could lead to [UTF-7 XSS vulnerability].

This tag should be set in the first 512 bytes.

In HTML 4 complete tag was:

```<meta http-equiv="Content-Type" content="text/html;charset=UTF-8">```

Sandbox:

<i color="#fc0">charset="UTF-8"</i>
``` <meta <i color="#fc0">charset="UTF-8"</i>> ```


More about this tag:
 - [MDN: meta#attr-charset] Has recommendations about this tag
 - IANAs [Character sets] list reference. (*But do use UTF-8*)


[MDN: meta#attr-charset]:https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta#attr-charset
[Character sets]:http://www.iana.org/assignments/character-sets/character-sets.xhtml
[UTF-7 XSS vulnerability]:https://code.google.com/p/doctype-mirror/wiki/ArticleUtf7