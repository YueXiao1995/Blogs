# The Title of Artical

[![Example Picture](http://thyrsi.com/t6/661/1548166952x2728273531.png)](https://twitter.com/karaage_mayu?lang=en)

**Hello World!**
My name is **Yue Xiao**, this is may first Markdown document. The picture above is one of my favorite idols, **Mayuyu**. I just want to use her photo to practice.

To let more people know her, [here](https://twitter.com/karaage_mayu?lang=en) is the link of her personal pages on Tiwtter.

## Some Basic syntaxes
### 1. Line Breaks
Put two spaces and a newline(return) at the end of the line you want to break. For example:

* This is  
a breaked line.

### 2. Strong and Emphasize
**Strong**: `**Strong**` or `__Strong__`
*Emphasize*:`*Emphasize*` or `_Emphasize_`

### 3. Headers
**The first way**:

	# Header 1
	## Header 2
	### Header 3
	#### Header 4
	##### Header 5
	###### Header 6

**The first way**:
add `"======"` under the header text, equal to the `# Header 1`
"Example Header 1"
==================
or add `"------"` under the the header text, equal to the `## Header 2`
"Example Header 2"
------------------

### 4. Links and Email

Put angle brackets around an email to make it clickable.`<1995yuexiao@gmail.com>`.  
For example, here is my email: <1995yuexiao@gmail.com>


There are three ways to create a link.

We can directly show the link with angle brackets aroung. `<https://google.com>`.  
For example <https://google.com>

Or we can hide the link into text. `[google](https://google.com)`.  
For example: [google](https://google.com)

**Reference Style**: To make the maintaining work more easier, we can give each link an id, and details the urls of all of the links later. `[a link][link_id]`.  
For example here is a link:
[a link][link_id]


and we can detail the url of the link later.
`[link_id]: https://google.com`

[link_id]: https://google.com
 
### 5. Images
#### Inline
`![Alt Image Text](path/or/url/to.jpg)`


#### Reference Stytle
Give the image an id.  
`![Alt Image Text][image_id]`

then detail the link later

`[image_id]: path/or/url/to.jpg`.  

### 6. Lists
* Unordered lists start with a `*` or `-`
	- Intent a level to make a nested list:
		1. item 1
		2. item 2
		34. item 3
 
### 7. Block Quote
> Angle brackets `>` are used for block quote.  
> > block quote can be nested
> > > even multiple levels.  
> 
> most markdown syntaxes work inside block quotes


### 8. Code
#### Inline Code
`inline code` is surrounded by backticks: `` `Inline code` ``

#### Block Code
Indent at least four spaces or one tab, for example.

    print("Hello World!")
    print('This is a code block')
    print('The block must be preceeded by a blank line')
	print('Then indent at least 4 spaces or 1 tab')

### 9. Horizontal Lines
Use `***` or `---` we can create a horizontal line. For example
***
---

### 10. Table
First Header | Second Header | Thrid Header
------------ | ------------- | ------------
Content Cell a | Content Cell b | Content c
Content Cell d | Content Cell e | Content f

The algnment depends solely on `:` marks.  
`:-----` left most  
`:----:` medle
`-----:` right most
For example:

| Left Aligned | Center Aligned cell | Right Aligned |
| :----------- | :-----------------: | -------------:|
| 2            | 3                   | 4             |
### 11. Fenced Code Block
Use `~` or `` ` `` to create a fenced code block.  
For example:

```
print("Hello World")
```
or:

~~~
print("I am Yue")
~~~

Add an optional language ID at the end of the first line, for example `~~~python`, then the code will be highlighted.

~~~python
a = [1, 2, 3]
b = [4, 5, 6]
for i in a:
	print a + b
~~~ 

### 12. Inline Formatting
Option name | Markup | Result
-----------|--------|-------
Intra-word emphasis | A\*maz\*ing | A*maz*ing
Strikthrough | \~~Hello\~~ | ~~Hello~~
Underline | \_good job\_ | _goog job_
Highlight | \==so good\== | ==so good== 
Superscript | hoge\^(fuga) | hope^(fuga)
Footnotes | [\^4]word [\^4]:information | [^footnote1] word

[^footnote1]: footnote can be number or arbitrary things. 





