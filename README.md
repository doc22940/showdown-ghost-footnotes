# Showdown Footnotes Extension for Ghost

Add support for footnotes syntax in [ghost](https://github.com/TryGhost/Ghost/).
Compatible with [showdown standalone](https://github.com/showdownjs/showdown/)

## Installing 
`npm install showdown-ghost-footnotes`

## Usage extending Showdown
1. Require [Showdown](https://github.com/showdownjs/showdown/) `const showdown = require('showdown');`
2. Require Showdown Footnotes `const footnotes = require('showdown-ghost-footnotes');`
3. Extend Showdown to enable Footnotes `const converter = new showdown.Converter({ extensions: [footnotes] });`

## Example
```md
I have more [^1] to say up here.
```
Turns into

```html
<p>
  I have more <sup id="fnref-1"><a href="#fn-1" rel="footnote" title="go to footnote">1</a></sup> to say up here.
</p>
```
And at the bottom of the page
```md
[^1]: To say down here.
```
Turns into

```html
<div class="footnotes">
<hr>
  <ol>
    <li id="fn-1"><p>To say down here.
    <a href="#fnref-1" class="footnote-backref" title="return to article">↩</a></p></li>
  </ol>
</div>
```