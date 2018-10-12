# PortableEmojiDatabases
OS, Browser, mobile apps, keyboards and more platform supported portable emojis databases

**[Emoji Source](https://unicode.org/emoji/charts/full-emoji-list.html)**
**[Jquery (JS Library / My prefer)](https://jquery.org/)**
**[Jquery inject to developer console (Optional)](https://stackoverflow.com/a/7474386/6940144)**

### Single Unicode Emojis

**Last Fetch Date:** *10.12.2018*
**Browser & Version:** *Opera 56.0.3051.36*
**Header:** *Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/69.0.3497.100 Safari/537.36 OPR/56.0.3051.36*

Jquery parser code
```javascript
var emojis = new Array();

$.each(tables, function(){
    var tr = $(this).find('tr');
    $.each(tr, function(){
		var code = $(this).find('.code').text();
		var chars = $(this).find('.chars').text();
		var name = $(this).find('.name').text();

		if (code.match(/^[U+A-Z0-9]+$/)){
            var emoji = {
                code: code,
                chars: chars,
				name: name
            };

			emojis.push(emoji);
		}
	});
});

console.log(emojis);
console.log(JSON.stringify(emojis));
```

JSON output (~1207 item)
```json
[
    {
        "code": "U+1F600",
        "chars": "😄",
        "name": "grinning face"
    },
    {
        "code": "U+1F603",
        "chars": "😃",
        "name": "grinning face with big eyes"
    },
    ...
]
```

**Tip:** "char" reserved field for MySQL, we can use "chars"