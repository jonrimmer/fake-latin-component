Fake Latin
=========

Fake Latin is a web component for generating placeholder latin text (e.g. "Lorem ipsum..."). It is uses the [Polymer library](http://polymer-project.org). It can be used to generate small fragments of text, or entire psuedo-structured articles.

I originally wrote the component as a simple project to experiment with Polymer, but hopefully it may prove useful to others for rapid prototyping.

The component is distributed under the [Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0). The list of latin words and some implementation ideas are courtesy of [Fredrik Bridell's Lorem Ipsum Generator](http://bridell.com/loremipsum/) (CC-BY). The Gaussian function is courtesy of [Vincenzo Liberatore](http://engr.case.edu/liberatore_vincenzo/software/gauss.html).

## Basic Usage

To use the component, you will need to include Polymer and import fake-latin.html.

```html
<script src="polymer/polymer.js"></script>
<link ref="import" href="fake-latin.html">
```

To get some generated text, just drop a `<fake-latin>` element into you HTML wherever you want it.

```html
<span><fake-latin></fake-latin></span>
```

This will add a single sentence of randomly generated latin, giving you something like:

```html
<span>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</span>
```

If you want more than one sentence, you can use the `repeat` attribute:

```html
<span><fake-latin repeat="3"></fake-latin></span>
```

Which will produce something like

```html
<span>Ardentior ambitae animalibus terrarum. Quem onus pugnabant siccis. Imagine homo sive terra caesa
obliquis, fuerant flexi obsistitur animalibus supplex exemit obstabatque corpore mare animalibus origine
militis illas duas.</span>
```

## Paragraphs

You can use the ```type``` attribute with a value of ```p``` or ```paragraph``` to generate a random paragraph of latin, contained in a ```<p>``` element.

```html
<fake-latin type="paragraph"></fake-latin>
```
or
```html
<fake-latin type="p"></fake-latin>
```

Which will produce something like:

```html
<p>Inclusum lapidosos quae duris onus deducite, regat cognati habendum totidemque. Proximus matutinis
parte invasit iners inminet mutatas seductaque nullus solum nullaque secant super astra pluvialibus.
Vindice suis onerosior dixere ventos erat. Septemque dextra. Caelo terrenae, margine nondum oppida
mutastis fidem formaeque fulminibus nabataeaque tanta</p>
```

The ```repeat``` attribute can be used to produce multiple paragraphs.

## Unordered Lists

You can use the ```type``` attribute with a value of ```list```, ```unordered list``` or ```ul``` to generate a randomly sized list:

```html
<fake-latin type="list"></fake-latin>
```

Which will get you something like this:

```html
<ul>
    <li>Dominari quicquam inmensa deerat mundi</li>
    <li>Fert triones temperiemque adspirate partim matutinis, dei induit terrarum undae animus dedit os</li>
    <li>Habitandae pugnabant quin coeperunt cuncta caecoque recessit turba invasit eodem bracchia</li>
    <li>Pace illis, fabricator diversa librata</li>
    <li>His indigestaque</li>
</ul>
```

The ```repeat``` attribute can be used to produce multiple unordered lists.

## Ordered Lists

Similarly, you can use the ```type``` attribute with a value of ```ordered list``` or ```ol``` to create an ordred list:

```html
<fake-latin type="ol"></fake-latin>
```

Which will produce something like this:

```html
<ol>
    <li>Homini ligavit quicquam</li>
    <li>Peragebant, iunctarum traxit</li>
    <li>Dispositam nullo margine utque illic tumescere, mentisque totidem ventos totidemque</li>
    <li>Vis iudicis pinus aere turba</li>
</ul>
```
    
## List Item Type

If you need to, you can control the content of list items with the ```list-item-type``` attribute. A value of ```p``` or ```paragraph``` will produce a ```<p>``` element containing a few sentences of latin, exactly as if you have an ```<fake-latin type="paragraph"></fake-latin>``` element in there.

Any other value, or if the attribute is not specified, will default to a single sentence.

## Headings

You can use the ```type``` attribute with a value of ```heading``` or ```h1``` to generate an ```<h1>``` element containing header-capitalised random text. Other heading sizes up to ```h4``` are also supported.

## Articles

You can use the ```type``` attribute with a value of ```article``` to generate an ```<article>``` element containing a large body of text. The generated text will begin with an ```<h1>``` element, and will continue with a random number of paragraphs. ```<h2>``` subheadings will be added every mod(3) paragraphs, and ```<h3>``` subheadings every mod(5) paragraphs.

## Size Control

If necessary, the size of the generated content can be contolled via the ```sentence-size```, ```paragraph-size```, ```list-size```, ```heading-size``` and ```article-size``` attributes. These attributes accept values in three forms:

### &lt;size&gt;

E.g. ```sentence-size="10"```

This will specify a fixed size value.

### &lt;min&gt;,&lt;max&gt;

E.g. ```paragraph-size="5,15"```

This will produce a random size that is uniformly distributed between the minimum and maximum values.

### n&lt;mean&gt;,&lt;std-dev&gt;

E.g. ```list-size="n8,2"```

This will produce a random size this is approximately normally distributed with the supplied mean and standard deviation.

The default sizes of each type is as follows:

 * Sentences: ```n12,4```
 * Pararaphs: ```n8,3```
 * Lists: ```n8,2```
 * Headings: ```n6,2```
 * Articles: ```n6,2```

## Repeat

The ```repeat``` attribute is used to repeat the output of the element some number of times. It accepts the same syntax as the size control elements.

E.g. ```repeat="5"```, ```repeat="6,12"``` or ```repeat="n9,3"```







