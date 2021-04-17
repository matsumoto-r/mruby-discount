# Markdown Class for mruby

[![Build Status](https://travis-ci.org/matsumoto-r/mruby-discount.svg?branch=master)](https://travis-ci.org/matsumoto-r/mruby-discount)

mruby Markdown class. Convert Markdown to HTML using [discount](https://github.com/Orc/discount)

## Install by mrbgems
 - add conf.gem line to `build_config.rb`
```ruby
MRuby::Build.new do |conf|

    # ... (snip) ...

    conf.gem :github => 'matsumoto-r/mruby-discount'
end
```

## Example

```ruby
m = Discount.new("http://kevinburke.bitbucket.org/markdowncss/markdown.css", "titlehoge")

markdown = '
# title
title
## subtitle
- hoge
- fuga
'

puts m.header
puts markdown.to_html
puts "## subtitle2".to_html
puts "- foo".to_html
puts m.footer

# # Or
# puts m.md2html(markdown + "\n" + "## subtitle2" + "- foo")
```


 ```html
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
<meta http-equiv="Content-Style-Type" content="text/css" />
<title>titlehoge</title>
<link rel="stylesheet" href="http://kevinburke.bitbucket.org/markdowncss/markdown.css" type="text/css" />
</head>
<body>
<a name="title"></a>
<h1>title</h1>

<p>title</p>

<a name="subtitle"></a>
<h2>subtitle</h2>

<ul>
<li>hoge</li>
<li>fuga</li>
</ul>
<a name="subtitle2"></a>
<h2>subtitle2</h2>
<ul>
<li>foo</li>
</ul>

</body>
</html>
 ```

# License
under the MIT License:

* http://www.opensource.org/licenses/mit-license.php


