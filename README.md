#Xpath

[![Build Status](https://travis-ci.org/h0gar/xpath.svg?branch=master)](https://travis-ci.org/h0gar/xpath)

A lightweight package for xpath manipulations.

- [Installation](#installation)
- [Usage](#usage)
- [Access a node](#access-a-node)
- [Access multiple nodes](#access-multiple-nodes)
- [Navigation](#navigation)
- [Get a node inner html](#inner-html)
- [Get a node inner text](#inner-text)
- [Get an attribute](#attribute)
- [\DOMElement and \DOMXpath](#domelement-domxpath)

<a name="installation"></a>
##Installation

	composer require h0gar/xpath *

<a name="usage"></a>
##Usage

**HTML**

	$html = file_get_contents('page.html');
	$doc = new \H0gar\Xpath\Doc($html, 'html');

**XML**

	$xml = file_get_contents('page.xml');
	$doc = new \H0gar\Xpath\Doc($xml, 'xml');

<a name="access-a-node"></a>
##Access a node

	$item = $doc->item('/html/body/div[1]/div/div[2]/ul/li[0]');
	#or
	$item = $doc->item('/html/body/div[1]')->item('div/div[2]/ul/li', 1);

<a name="access-multiple-nodes"></a>
##Access multiple nodes

	$items = $doc->items('/html/body/div[1]/div/div[2]/ul/li');
	foreach($items as $item)
		//...

<a name="navigation"></a>
##Navigation

	$next = $item->next();
	$prev = $item->prev();
	$parent = $item->parent();

<a name="inner-html"></a>
##Get a node inner html

	$html = $item->html();
	#or
	$html = $doc->html('/html/body/div[1]/div/div[2]/ul/li[0]');
	#or
	$html = $doc->html('/html/body/div[1]/div/div[2]/ul/li', 1);

<a name="inner-text"></a>
##Get a node inner text

	$text = $item->text();
	#or
	$text = $doc->text('/html/body/div[1]/div/div[2]/ul/li[0]');
	#or
	$text = $doc->text('/html/body/div[1]/div/div[2]/ul/li', 1);

<a name="attribute"></a>
##Get an attribute

	$href = $item->attr('href');

<a name="domelement-domxpath"></a>
##\DOMElement and \DOMXpath

	$domelement = $item->getNode();
	$domxpath = $item->getXpath();

##Contributing

Please submit all issues and pull requests to the [h0gar/xpath](http://github.com/h0gar/xpath) repository.

##License

Open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)