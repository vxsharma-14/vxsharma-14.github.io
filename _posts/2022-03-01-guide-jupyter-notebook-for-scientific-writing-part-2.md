---
title: "A Helpful Guide on using Jupyter Notebook for Scientific Documentation - Part 2"
excerpt: "Learn about markdown language and see the list of important markdown syntax."
header:
  image: /assets/images/posts/jupyter_nb_header1.jpg
  caption: "Photo by [Nick Morrison](https://unsplash.com/@nickmorrison) on [Unsplash](https://unsplash.com/)"
date: March 01, 2022
toc: true
toc_label: "Content"
tags:
  - Academic Writing
  - Jupyter Notebboks
  - Markdown
  - Tutorial
  - Grad students
category:
  - Jupyter Notebooks
---

This is Part 2 of the series on Jupyter Notebooks for Scientific Documentation. A brief introduction of Markdown language is presented along with useful Markdown syntaxes. See [Part 1](/jupyter%20notebooks/guide-jupyter-notebook-for-scientific-writing-part-1/) for introduction to Jupyter Notebook.
{: .notice}  

## What is Markdown?

Markdown is a markup language to convert plain text-to-HTML. It was created by [John Gruber](https://daringfireball.net/projects/markdown/) and is now one of the world's most popular markup language. Jupyter Notebook has the feature to render the plain text with markdown formatting written in its markdown cell as HTML. Additionally, within the JupyterLab environment you can create and edit a markdown document (with extension **.md** or **.markdown**) and preview the markdown contents as HTML. Read this [article](https://www.markdownguide.org/getting-started/) for additional information. 

## Why use Markdown?

* Markdown syntax is very intuitive and easy to learn with the help of only few examples.
* Create websites, documents, notebooks, tutorials, presentations, technical documentations and blog articles using markdown formatting.  

<i class="far fa-sticky-note"></i> All pages and blogs on my website are written as markdown files.
{: .notice--success}  

* Markdown file can be opened in any basic text editor.
* JupyterLab environment provides you the ability to efficiently work with markdown and render the output.
* Easily include LaTeX syntax to include greek letters, scientific notations and math equations in the notebook.
* GitHub supports markdown syntax and rendering. See [GitHub Flavored Markdown](https://github.github.com/gfm/) for more info.

## Markdown syntax

### Headings

Create a top-level heading by prefixing `#` to the heading text on a new line. Similarly, prefix `##` to sub-heading text, `###` for sub sub heading and so on.

```
# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6
```

{% capture notice-text %}
* Always insert a whitespace between the `#` character and the heading text for compatibility.
* Always insert blank lines before and after the heading elements.
{% endcapture %}

<div class="notice--warning">
  <b class="no_toc"><i class="far fa-thumbs-up"></i> Best Practices.</b>
  {{ notice-text | markdownify }}
</div>

### Paragraph

A paragraph consists of plain text sentences on a new line.

<i class="far fa-thumbs-up"></i> **Best Practice.** Always insert a blank line between paragraphs.
{: .notice--warning}  

### New line Character

Insert two blank whitespaces as a new line character at the end of the line and hit `Enter`.

*Example markdown input without two blank whitespaces at the end:*

```
This sentence does not end with the new line character (no whitespaces after period).
Thus, this line will continue on the first line.
```

*Output:*

This sentence does not end with the new line character (no whitespaces after period).
Thus, this line will continue on the same line.

*Example markdown input with two blank whitespaces at the end:*

```
This sentence ends with the new line character.  
Thus, this line will be on the new line.
```
    
*Output:*

This sentence ends with the new line character.  
Thus, this line will be on the new line.

### Text Emphasis

| Syntax | Output |
| :--- | :--- |
| `**Bold** Text` | **Bold** Text |
| `*Italicized* Text` | *Italicized* Text |
| `***Bold and Italicized*** Text` | ***Bold and Italicized*** Text |

<i class="far fa-sticky-note"></i> **Note.** There are no whitespaces between emphasis elements and the emphasized text.
{: .notice--info}  

### Creating a Table

Create a table using the syntax shown below. Pipe `|` character separates the columns of the table and dashes `---` are used to specify the table header row.

```
| Col. 1 Heading | Col.2 Heading | Col.3 Heading |
| --- | --- | --- |
| text in col. 1 | text in col. 2 | text in col. 3 |
```
    
*Output table:*

| Col. 1 Heading | Col.2 Heading | Col.3 Heading |
| --- | --- | --- |
| text in col. 1 | text in col. 2 | text in col. 3 |

<i class="fas fa-lightbulb"></i> **Tip.** Syntax `| :--- |` is used to left align the text. Similarly, right align and center align the text using syntax `| ---: |` and `| :---: |`, respectively.
{: .notice--success} 

<i class="far fa-thumbs-up"></i> **Best Practice.** Always insert blank lines before and after the table.
{: .notice--warning}  

### Ordered and Unordered Lists

**Ordered lists** are the numbered lists created by numbers (followed by a period `.` delimiter) prefixed to each list item.

*Markdown input for an ordered list:*

```
1. First list item.  
    1.1 Sub-list of first item.  
2. Second list item.  
    2.1 Sub-list of second item.  
3. Third list item.
```

*Output:*

1. First list item.  
    1.1 Sub-list of first item.
2. Second list item.  
    2.1 Sub-list of second item.
3. Third list item.

**Unordered lists** are the bulleted points that are created using either an asterisk `*`, a dash `-` or  a plus `+` character before the list items. Create a nested list by indenting each sub-list item by four whitespaces (or a tab character). 

*Markdown input for an unordered list:*

```
* List item.
    * Sub-list.
* Another list item.
    * Sub-list.
```

*Output:*

* List item.
    * Sub-list.
* Another list item.
    * Sub-list.

<i class="far fa-sticky-note"></i> **Note.** To create a nested list, indent each sublist item by four whitespaces (or a tab character).
{: .notice--info}  
    
<i class="far fa-sticky-note"></i> **Note.** Ordered list can be nested with unordered list and vice-versa.
{: .notice--info}  

{% capture notice-text %}
* Always insert a whitespace between the list delimiters and the text for compatibility.
* Always insert blank lines before and after the lists.
* Don't mix different delimiters `*`, `+`, `-` within the same unordered list.
{% endcapture %}

<div class="notice--warning">
  <b class="no_toc"><i class="far fa-thumbs-up"></i> Best Practices:</b>
  {{ notice-text | markdownify }}
</div>

### Links

Link a text with a URL using the syntax `[URl description](URL)`.

`[Twitter](https://twitter.com/DrVishal_aero)`

It will create the link to my [Twitter](https://twitter.com/DrVishal_aero).

<i class="fas fa-light-bulb"></i> **Tip.** You can also link to a section within your markdown file using the following syntax `[section description](#section-title)`
{: .notice--success}  

*Example markdown input:*

`[Ordered and Unordered Lists](#ordered-and-unordered-lists)`.

*Output:*

Click on this link to [Ordered and Unordered Lists](#ordered-and-unordered-lists).

### Images

Images are included using the syntax `[image description](path)`

`[SR-71](https://unsplash.com/photos/Tquhp9Kqkzk)`

See online image of an [SR-71](https://unsplash.com/photos/Tquhp9Kqkzk) by NASA on Unsplash.

<i class="far fa-sticky-note"></i> **Note.** Images locally stored on your computer are linked by providing the path to the image instead of a URL.
{: .notice--info}  

### Inline Codes and Code blocks

**Inline code** statements are created using the syntax `` `code statemtent` `` (write code between backticks). 

*Example input:*

``Slope of a line is given by the expression `y=mx+c` ``.

*Output:*

Slope of a line is given by the expression `y=mx+c`. 

A **Code block** consists of multiple lines of code statements or snippets. You may want to show a code block to your reader as codes instead of a plain texts. This can be done by placing the code block on a new line between three backtick characters at the beginning of the block and three at the end of the code block.

```
This is a
multiple line 
code block.
```

<i class="far fa-sticky-note"></i> **Note.** Alternatively, indent each line by four whitespaces (or a tab character) that you want to show as a code block.
{: .notice--info}  

<i class="far fa-thumbs-up"></i> **Best Practice.** Always insert blank lines before and after the code block.
{: .notice--warning}  

<i class="fas fa-lightbulb"></i> **Tip.** Code syntax can be color highlighted by specifying the code language immediately after the opening backticks.
{: .notice--success}  

```python
def sum_of_two_numbers(a, b):
    return a + b
```

### Blockquotes

Create blockquotes using the `>` character as a prefix to the paragraph text.

*Example markdown input:*

`> This is a blockquote.`

**Output:**

> This is a blockquote.

<i class="fas fa-lightbulb"></i> **Tip.** Create blockquotes for multiple paragraph using `>` character on the blank lines between the paragraphs. 
{: .notice--success}  

```
> This is paragraph 1 in a blockquote.
>
> This is paragraph 2 in the same blockquote.
```

> This is paragraph 1 in a blockquote.
>
> This is paragraph 2 in the same blockquote.

<i class="fas fa-lightbulb"></i> **Tip.** Create nested blockquotes using `>>` before paragraphs that you want to nest. 
{: .notice--success}  

```
> This is a paragraph in a blockquote.
>
>> This is a nested blockquote.
```

> This is a paragraph in a blockquote.
>
>> This is a nested blockquote.

<i class="far fa-thumbs-up"></i> **Best Practice.** Always insert blank lines before and after the blockquotes.
{: .notice--warning}  

### Create Checklists

Create checklists with checkboxes using the syntax: `- [ ] task title`. To select a checkbox, add an `x` in between the square brackets `[x]`.

*Example markdown input:*

```
- [x] Write an article on Jupyter Notebook.
- [x] Write an article on markdown syntax.
- [ ] Write an article on LaTeX in markdown.
```

*Output:*

- [x] Write an article on Jupyter Notebook.
- [x] Write an article on markdown syntax.
- [ ] Write an article on LaTeX in markdown.

### Horizontal Rules

Horizontal rules are created by using three or more asterisks `***`, dashes `---`, or underscores `___`.

---

<i class="far fa-thumbs-up"></i> **Best Practice.** Always insert blank lines before and after the horizontal rules.
{: .notice--warning}  

### Footnotes

In footnotes a clickable superscript number is created that is linked to the footnote reference. Readers can click the link to jump to the content of the footnote at the bottom of the page. Footnotes are created using two-part syntax. First part of the syntax is `[^id]` where `id` is an identifier which can be numbers or words. The second part of the syntax is `[^id]: footnote text`. You can put footnote text anywhere in the document.

*Example markdown input:*

```
Use of footnotes[^1].

[^1]: Add notes and references without cluttering the body of the document using footnotes.
```

Use of footnote[^1].

[^1]: Add notes and references without cluttering the body of the document using a footnote.


<i class="far fa-thumbs-up"></i> **Best Practice.** Don't put footnotes inside other elements -- lists, blockquotes, and tables.
{: .notice--warning}  

## Exercise

Create your resume in Jupyter Notebook using markdown syntax. Subsequently, import the Notebook as a .pdf file.
