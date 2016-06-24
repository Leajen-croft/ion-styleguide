![alt tag](logo.png)

The aim of Ion is to create a style guide that could be used on sites not using a task runner like gulp or grunt which is what is need for most of the styleguide generators out there. Being built in polymer meant that custom HTML tags could be created that would be styled correctly and easier to used the just div structures. It has been built to be separate from drupal so it could be used within multiple workflows and as such is only in essence plain HTML.  


## Using The Style Guide ##
As custom polymer tags have to be hyphenated and can't be single words, as such each is named ion-*. How each of these work is detailed below.

### Note ###
```html
<ion-note> </ion-note>
```

The note tag is used to added notes to the other tags. It only takes one attribute, <code>classes</code>, this attribute is only needed if the note needs a class declaration adding the the front of the note text.

#### Example ####
```html
<ion-note classes=".title">The primary heading used on the site.</ion-note>
```

### Colour Palette
```html
<ion-colour-palette> </ion-colour-palette>
```

The colour palette tag is used to create a block with the colour and the colours data. The tag is has the follow attributes on it:

<code>colour-name</code> - This is used to set the name for the colour.

<code>hex-value</code> - This is used to set the hex value for the colour.

<code>rgb-value</code> - - This is used to set the RGB value for the colour.

<code>colour-variable</code> - This used to set a variable for the colour, used mostly on customs but it's useful even on smaller site not using a CSS preprocessor.

#### Example ####
```html
<ion-colour-palette colour-name="Scooter" hex-value="#37bec6" rgb-value="55,190,198" colour-variable="scooter"></ion-colour-palette>
```

**Note: The colour palette tag can not take the ion note tag.**

### Font ###
```html
<ion-font> </ion-font>
```

The font tag is used to create a block that displays the fonts being used on the site (depending on where the style guide is being used this may mean adding the font declaration directly into the style guide's index.html of custom.css file). The font tag only has one attribute, <code>font-family</code>, this takes the font family declaration needed for the font. 


#### Example ####
```html
<ion-font font-family="font-family: 'PT Serif', serif;">
   <ion-note>
      notes about font
   </ion-note>
</ion-font>
```

### Button ###
```html
<ion-button> </ion-button>
```

The button tag creates a block with the three button types that can be found on a site, a with the class button, the vanilla button tag and the input type button tag. The tag takes two attributes:

<code>element-title</code> - Used to give the block a title.

<code>class-name</code> - Used to designate the classes the buttons need to have on them.

#### Example ####
```html
<ion-button element-title="default button" class-name="button--default">
   <ion-note classes=".button-default">The default button style used on the site.</ion-note>
</ion-button>
```

### Input ###
```html
<ion-input> </ion-input>
```

The input tag creates a block with two input tags in it. it will put out two inputs one with a note beside it and one without. The tag takes a few attributes:

<code>element-title</code> - Used to give the block a title.

<code>class-name</code> - Used to designate the classes the inputs need to have on them.

<code>type</code> - Set to the type of inputs

<code>place-holder</code> - the placeholder the inputs will have.

<code>label-text</code> - The text used for the labels

#### Example ####
```html
<ion-input element-title="default form text field" class-name="default" type="text" place-holder="Placeholder text" label-text="label text">
  <ion-note>The default text field style used on the site.</ion-note>
</ion-input>
```

### Text ###
```html
<ion-text> </ion-text>
```

The text tag is used to create a text block to show the different styles of text used on the site. The text part of the element is set to editable so even though to set a default value the text can be edited on the style guide to see test for the style looks with different words. The tag takes two attributes:

<code>element-title</code> - Used to give the block a title.

<code>class-name</code> - Used to designate the classes the text needs to have on it.

In addition to the attributes above to get a text value to display in the block require a vanilla HTML tag to be added with the class text.

#### Example ####
```html
<ion-text element-title="heading 1" class-name="title">
  <ion-note classes=".title">The primary heading used on the site.</ion-note>
  <h2 class="text">title</h2>
</ion-text>
```

### Custom Block ###
```html
<ion-custom-block> </ion-custom-block>
```

The custom block tag is used of any other content which does not currently have a ion tag or is one of a kind set up. The tag takes one attribute,<code>element-title</code>, which is used to give the block a title.

#### Example ####
```html
<ion-custom-block element-title="default unordered list">
  <ion-note>The default unordered list styles.</ion-note>
    <ul>
      <li>one</li>
      <li>two</li>
      <li>three</li>
    </ul>
</ion-custom-block>
```

### Markdown block ###
```html
<ion-markdown> </ion-markdown>
```

The markdown tag is used to link to and render a markdown document, this make it easier to create and comment custom styled elements. The latest version of the ion style guide template actually uses this more then any other tag due to the easier control it offers.

#### Example ####
```html
<ion-markdown file="partials/colours.md"></ion-markdown>
```


