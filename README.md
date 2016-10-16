# clipboard-button
[![Build status][travis-badge]][travis-url] [![Bower dependencies][bowerdeps-badge]][bowerdeps-url] ![Version][bower-badge]

Button that cuts/copies text to the user's clipboard

### Installation

Install clipboard-button with Bower

```sh
$ bower install seaneking/clipboard-button --save
```

Import it into the `<head>` of your page

```html
<link rel="import" href="/bower_components/clipboard-button/clipboard-button.html">
```

Then use the element in your 
```html
<clipboard-button></clipboard-button>
```

Note for cross-browser support you should also include the [Web Components Polyfill][webcomponents].

### Usage 

You can specify the content you want to copy as a plaintext or HTML string in the `content` property

```html
<clipboard-button content="Plain text or <strong>HTML</strong> content"></clipboard-button>
```

Or by providing a HTML element, which `clipboard-button` will parse and copy its contents to the clipboard

```html
<clipboard-button id="copy"></clipboard-button>

<script>
    document.querySelector('#copy').element = document.body;
</script>
```

Note that if both `content` and `element` are specified, `content` takes precedence.

#### Manual copying

Clipboard button automatically copies the target content to clipboard on tap/click, but you can also call `copy` imperatively

```html
<clipboard-button id="#copy" content=""></clipboard-button>

<script>
    document.querySelector('#copy').copy();
</script>
```

Note that most browsers only allow copying to clipboard in direct response to a user input, like clicking.

### Properties
Properties can be set as HTML attributes on `clipboard-button` or with Javascript

Property    | Type    | Default              | Description                                                                                                                
----------- | ------- | -----------------    | ------------                                                                                                               
`content`   | String  | `undefined`          | Text (or HTML string) content to copy to clipboard                                                                         
`element`   | Object  | `undefined`          | HTML element to parse and copy to clipboard                                                                                
`icon`      | String  | `icons:content-copy` | SVG definition of an icon. Use [`iron-icons`][iron-icons], or define your own iconset with [`iron-iconset`][iron-iconset]. 

### Events
Event       | Description                            
----------- | ------------                           
`copied`    | Fired on successful copying of content 


##### TODO
- Tests
--

MIT © Sean King <sean@seanking.org>

[webcomponents]: https://github.com/webcomponents/webcomponentsjs

[bower-badge]: https://img.shields.io/bower/v/clipboard-button.svg
[bowerlicense-badge]: https://img.shields.io/bower/l/clipboard-button.svg
[travis-badge]: https://img.shields.io/travis/seaneking/clipboard-button.svg
[travis-url]: https://travis-ci.org/seaneking/clipboard-button
[bowerdeps-badge]: https://img.shields.io/gemnasium/seaneking/clipboard-button.svg
[bowerdeps-url]: https://gemnasium.com/bower/clipboard-button
