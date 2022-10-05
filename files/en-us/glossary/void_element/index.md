---
title: Void element
slug: Glossary/Void_element
tags:
  - CodingScripting
  - HTML
  - Intermediate
---

A **void element** is an {{Glossary("element")}} in HTML that **cannot** have any child nodes (i.e., nested elements or text nodes). Void elements only have a start tag; end tags must not be specified for void elements.

In HTML, a void element must not have an end tag. For example, `<input type="text"></input>` is invalid HTML. In contrast, SVG or MathML elements that cannot have any child nodes may use an end tag instead of XML self-closing-tag syntax in their start tag.

The [HTML](https://html.spec.whatwg.org/multipage/), [SVG](https://www.w3.org/TR/SVG2/), and [MathML](https://www.w3.org/TR/MathML3/) specifications define very precisely what each element can contain. So, some combinations of tags have no semantic meaning.

Although there is no way to mark up a void element as having any children, child nodes can be added programmatically to the element in the DOM using JavaScript. But that is not a good practice, as the outcome will not be reliable.

The void elements in HTML are as follows:

- {{HTMLElement("area")}}
- {{HTMLElement("base")}}
- {{HTMLElement("br")}}
- {{HTMLElement("col")}}
- {{HTMLElement("embed")}}
- {{HTMLElement("hr")}}
- {{HTMLElement("img")}}
- {{HTMLElement("input")}}
- {{HTMLElement("keygen")}}(HTML 5.2 Draft removed)
- {{HTMLElement("link")}}
- {{HTMLElement("meta")}}
- {{HTMLElement("param")}}
- {{HTMLElement("source")}}
- {{HTMLElement("track")}}
- {{HTMLElement("wbr")}}

## The curious case of self-closing tags

_Self-closing tags (`<tag />`) do not exist in HTML._\
However, the start tags of SVG and MathML elements that cannot have any child nodes are allowed to be marked as self-closing. In such cases, if an element's start tag is marked as self-closing, the element must not have an end tag.

If a trailing `/` (slash) character is present in the start tag of an HTML element, HTML parsers ignore that slash character. However, some code formatters add a trailing slash character to the start tags of void elements to make them XHTML compatible and more readable. For example, some code formatters will convert `<input type="text">` to `<input type="text" />`.

> **Note:** If a trailing `/` (slash) character in a start tag is directly preceded by an unquoted attribute value — with no space between — the slash becomes a part of the attribute value rather than being discarded by the parser. For example, the markup `<img src=http://www.example.com/logo.svg/>` results in the `src` attribute having the value `http://www.example.com/logo.svg/` — which makes the URL wrong.