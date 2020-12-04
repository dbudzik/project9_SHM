---
author-meta:
- David Budzik
- Claudia Mederos
- Bolaji Lawal
- Abdullah Assaf
bibliography:
- content/manual-references.json
date-meta: '2020-12-04'
header-includes: '<!--

  Manubot generated metadata rendered from header-includes-template.html.

  Suggest improvements at https://github.com/manubot/manubot/blob/master/manubot/process/header-includes-template.html

  -->

  <meta name="dc.format" content="text/html" />

  <meta name="dc.title" content="Project 9: Structural Health Monitoring" />

  <meta name="citation_title" content="Project 9: Structural Health Monitoring" />

  <meta property="og:title" content="Project 9: Structural Health Monitoring" />

  <meta property="twitter:title" content="Project 9: Structural Health Monitoring" />

  <meta name="dc.date" content="2020-12-04" />

  <meta name="citation_publication_date" content="2020-12-04" />

  <meta name="dc.language" content="en-US" />

  <meta name="citation_language" content="en-US" />

  <meta name="dc.relation.ispartof" content="Manubot" />

  <meta name="dc.publisher" content="Manubot" />

  <meta name="citation_journal_title" content="Manubot" />

  <meta name="citation_technical_report_institution" content="Manubot" />

  <meta name="citation_author" content="David Budzik" />

  <meta name="citation_author" content="Claudia Mederos" />

  <meta name="citation_author" content="Bolaji Lawal" />

  <meta name="citation_author" content="Abdullah Assaf" />

  <link rel="canonical" href="https://dbudzik.github.io/project9_SHM/" />

  <meta property="og:url" content="https://dbudzik.github.io/project9_SHM/" />

  <meta property="twitter:url" content="https://dbudzik.github.io/project9_SHM/" />

  <meta name="citation_fulltext_html_url" content="https://dbudzik.github.io/project9_SHM/" />

  <meta name="citation_pdf_url" content="https://dbudzik.github.io/project9_SHM/manuscript.pdf" />

  <link rel="alternate" type="application/pdf" href="https://dbudzik.github.io/project9_SHM/manuscript.pdf" />

  <link rel="alternate" type="text/html" href="https://dbudzik.github.io/project9_SHM/v/c42493100e2a443c73fd08044d21f81255f99fa5/" />

  <meta name="manubot_html_url_versioned" content="https://dbudzik.github.io/project9_SHM/v/c42493100e2a443c73fd08044d21f81255f99fa5/" />

  <meta name="manubot_pdf_url_versioned" content="https://dbudzik.github.io/project9_SHM/v/c42493100e2a443c73fd08044d21f81255f99fa5/manuscript.pdf" />

  <meta property="og:type" content="article" />

  <meta property="twitter:card" content="summary_large_image" />

  <link rel="icon" type="image/png" sizes="192x192" href="https://manubot.org/favicon-192x192.png" />

  <link rel="mask-icon" href="https://manubot.org/safari-pinned-tab.svg" color="#ad1457" />

  <meta name="theme-color" content="#ad1457" />

  <!-- end Manubot generated metadata -->'
keywords:
- markdown
- publishing
- manubot
lang: en-US
manubot-clear-requests-cache: false
manubot-output-bibliography: output/references.json
manubot-output-citekeys: output/citations.tsv
manubot-requests-cache-path: ci/cache/requests-cache
title: 'Project 9: Structural Health Monitoring'
...






<small><em>
This manuscript
([permalink](https://dbudzik.github.io/project9_SHM/v/c42493100e2a443c73fd08044d21f81255f99fa5/))
was automatically generated
from [dbudzik/project9_SHM@c424931](https://github.com/dbudzik/project9_SHM/tree/c42493100e2a443c73fd08044d21f81255f99fa5)
on December 4, 2020.
</em></small>

## Authors



+ **David Budzik**<br>
    · ![GitHub icon](images/github.svg){.inline_icon}
    [dbudzik](https://github.com/dbudzik)<br>
  <small>
  </small>

+ **Claudia Mederos**<br>
    · ![GitHub icon](images/github.svg){.inline_icon}
    [cr25](https://github.com/cr25)<br>
  <small>
  </small>

+ **Bolaji Lawal**<br>
    · ![GitHub icon](images/github.svg){.inline_icon}
    [bolajilawal](https://github.com/bolajilawal)<br>
  <small>
  </small>

+ **Abdullah Assaf**<br>
    · ![GitHub icon](images/github.svg){.inline_icon}
    [aboo12](https://github.com/aboo12)<br>
  <small>
  </small>



## Abstract {.page_break_before}




# 1. Introduction

## 1.1 Motivation behind the research experiment
Identification of damage from the analysis of vibration signals has received significant attention in the civil, mechanical and aerospace fields.
Structural health monitoring allows the engineer to use sensing of the structural responses in conjunction with appropriate analysis and modeling techniques, to monitor the condition of a structure. The problem most commonly considered is that where data is recorded at two different times and it is of interest to determine if the structure suffered damage in the time interval between the two observations. The behavior of the system during the observation periods is typically assumed linear and the damage is identified as changes in system parameters. A solution can be obtained in principle by using the measured data to optimize a model of the structure in the two states and inspecting the differences. 
The goal of the experiment was to develope an automated structural health monitoring system capable of providing early warnings against structural damage. In order to achieve this, damage was simulated by removing bracing within the structure in nine different ways as shown in the following sections.

## 1.2 Literature Review
Due to the importance of this research, there have been multiple papers regarding how to optimize the recollection of the data and quantity needed for training the machine learning algorithm. Examination of the literature reveals, however, that the assumptions used to establish the various approaches vary widely and it is unclear what is the true capability of the current state of the art in damage detection of civil engineering structures. 

### 1-D CNNs for structural damage detection: Verification on a structural health monitoring benchmark data
Nowadays, a large number of measurement scenarios are needed to generate training data before placing the sensors in large civil structures. The paper “1-D CNNs for structural damage detection: Verification on a structural health monitoring benchmark data” provides an enhanced CNN-based algorithm which only requires two training sessions, ensuring accuracy and speed. 
The damage was estimated successfully by applying a CNN-based approach only requiring two measurement datasets. The overall structural health monitoring procedure for this paper took place on a very short amount of time, around 5000x faster than the conventional procedure. The authors indicated that this approach can be utilized on any structures, regardless of the size of the structure. Yet, the data processed was based exclusively on a monitored structure, and one may wonder how the fully damaged scenario data could be obtained on a large civil structure that needs to be monitored. Also, other difficulties become more apparent if we take into consideration how large civil structures do not behave precisely as the replica in which accelerometers were placed. It is almost impossible to repeat the measurement procedure that took place for the Phase II benchmark study on any other structure. And finally, although anomaly detection is obtained using CNNs algorithms, the cause of such anomaly or the location is completely a mystery. It is important to know the state of a structure for public safety, but it is also very important to locate the damage in order to take action. 

## 1.3 Structure & experiment descriptions:

**Benchmark Structure**

The benchmark structure is a 2-bay by 2-bay, 4 story steel frame structure at the University of British Columbia.
![Benchmark Structure](images/Screen%20Shot%202020-12-03%20at%208.59.34%20PM.png){height="13px"}
![
**Benchmark Structure.**
Loaded from the latest version of image on GitHub.
](https://github.com/dbudzik/project9_SHM/blob/master/content/images/Screen Shot 2020-12-03 at 8.59.34 PM.png "Square image"){#fig:square-image}

Cases with known and unknown input and damage scenarios including symmetrical and unsymmetrical loss of stiffness in the bracing system were considered.  The experiment in question is regarding how damage can be simulated by removing bracing or loosening bolts within a four-story steel frame structure. Complete details of the damage cases, input excitation and other pertinent aspects of the study of phase I can be found below. To obtain the data, accelerometers were placed throughout the structure to provide measurements of the structural responses. In particular, three sensors per floor. One located at the center, one at the west side and one at the east side, as the MATLAB files indicate. Then, different cases took place in which members were loosen or removed to analyze the output and correlate the difference in acceleration values with the difference in setup.
 
**The different cases**
* Case 1 - Fully braced configuration.
* Case 2 - All east side braces removed.
* Case 3 - Removed braces on all floors in one bay on southeast corner.
* Case 4 - Removed braces on 1st and 4th floors in one bay on southeast corner.
* Case 5 - Removed braces on 1st floor in one bay on southeast corner.
* Case 6 - Removed braces on all floors on east face, and 2nd floor braces on north faces.
* Case 7 - All braces removed on all faces.
* Case 8 - Configuration 7 + loosened bolts on all floors at both ends of beam on east face, north side.
* Case 9 - Configuration 7 + loosened bolts on floors 1 and 2 at both ends of beam on east face, north side.

![Cases 2-5](content/images/1-s2.0-S0925231217315886-gr4.jpg){height="10px"}
![Cases 6-8](content/images/1-s2.0-S0925231217315886-gr5.jpg){height="10px"}

**Excitation**
Ambient vibration was inputted into the structure by two types of forced excitations. The forced exci- tation cases consider both impact hammer tests, and broadband excitations provided by an electrodynamic shaker. 
The choice of these two methods is to simulate the structure's response during an earthquake.

## 1.4 Motivation behind the project on structural damage detection
Numerous structural health monitoring algorithms have been developed and been implemented on experimental and full-scale structure.Because the techniques are applied to different structures under various conditions, the relative merits of each algorithm are not obvious. Thus, the community would benefit from a comparison of several algorithms when applied to the same problems.





## Machine Learning Methods

Methods go here


## Results

Results go here


## Discussion of Results

Discussion goes here


## Conclusion

Conclusion goes here


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>


This manuscript is a template (aka "rootstock") for [Manubot](https://manubot.org/ "Manubot"), a tool for writing scholarly manuscripts.
Use this template as a starting point for your manuscript.

The rest of this document is a full list of formatting elements/features supported by Manubot.
Compare the input (`.md` files in the `/content` directory) to the output you see below.

## Basic formatting

**Bold** __text__

[Semi-bold text]{.semibold}

[Centered text]{.center}

[Right-aligned text]{.right}

*Italic* _text_

Combined *italics and __bold__*

~~Strikethrough~~

1. Ordered list item
2. Ordered list item
    a. Sub-item
    b. Sub-item
        i. Sub-sub-item
3. Ordered list item
    a. Sub-item

- List item
- List item
- List item

subscript: H~2~O is a liquid

superscript: 2^10^ is 1024.

[unicode superscripts](https://www.google.com/search?q=superscript+generator)⁰¹²³⁴⁵⁶⁷⁸⁹

[unicode subscripts](https://www.google.com/search?q=superscript+generator)₀₁₂₃₄₅₆₇₈₉

A long paragraph of text.
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Putting each sentence on its own line has numerous benefits with regard to [editing](https://asciidoctor.org/docs/asciidoc-recommended-practices/#one-sentence-per-line) and [version control](https://rhodesmill.org/brandon/2012/one-sentence-per-line/).

Line break without starting a new paragraph by putting  
two spaces at end of line.

## Document organization

Document section headings:

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6

### A heading centered on its own printed page{.center .page_center}

<!-- an arbitrary comment. visible in input, but not visible in output. -->

Horizontal rule:

---

`Heading 1`'s are recommended to be reserved for the title of the manuscript.

`Heading 2`'s are recommended for broad sections such as *Abstract*, *Methods*, *Conclusion*, etc.

`Heading 3`'s and `Heading 4`'s are recommended for sub-sections.

## Links

Bare URL link: <https://manubot.org>

[Long link with lots of words and stuff and junk and bleep and blah and stuff and other stuff and more stuff yeah](https://manubot.org)

[Link with text](https://manubot.org)

[Link with hover text](https://manubot.org "Manubot Homepage")

[Link by reference][manubot homepage]

[Manubot Homepage]: https://manubot.org

## Citations

Citation by DOI [@doi:10.7554/eLife.32822].

Citation by PubMed Central ID [@pmc:PMC6103790].

Citation by PubMed ID [@pubmed:30718888].

Citation by Wikidata ID [@wikidata:Q56458321].

Citation by ISBN [@isbn:9780262517638].

Citation by URL [@https://greenelab.github.io/meta-review/].

Citation by alias [@deep-review].

Multiple citations can be put inside the same set of brackets [@doi:10.7554/eLife.32822; @deep-review; @isbn:9780262517638].
Manubot plugins provide easier, more convenient visualization of and navigation between citations [@doi:10.1371/journal.pcbi.1007128; @pubmed:30718888; @pmc:PMC6103790; @deep-review].

Citation tags (i.e. aliases) can be defined in their own paragraphs using Markdown's reference link syntax:

[@deep-review]: doi:10.1098/rsif.2017.0387

## Referencing figures, tables, equations

Figure @fig:square-image

Figure @fig:wide-image

Figure @fig:tall-image

Figure @fig:vector-image

Table @tbl:bowling-scores

Equation @eq:regular-equation

Equation @eq:long-equation

## Quotes and code

> Quoted text

> Quoted block of text
>
> Two roads diverged in a wood, and I—  
> I took the one less traveled by,  
> And that has made all the difference.

Code `in the middle` of normal text, aka `inline code`.

Code block with Python syntax highlighting:

```python
from manubot.cite.doi import expand_short_doi

def test_expand_short_doi():
    doi = expand_short_doi("10/c3bp")
    # a string too long to fit within page:
    assert doi == "10.25313/2524-2695-2018-3-vliyanie-enhansera-copia-i-insulyatora-gypsy-na-sintez-ernk-modifikatsii-hromatina-i-svyazyvanie-insulyatornyh-belkov-vtransfetsirovannyh-geneticheskih-konstruktsiyah"
```

Code block with no syntax highlighting:

```
Exporting HTML manuscript
Exporting DOCX manuscript
Exporting PDF manuscript
```

## Figures

![
**A square image at actual size and with a bottom caption.**
Loaded from the latest version of image on GitHub.
](https://github.com/manubot/resources/raw/15493970f8882fce22bef829619d3fb37a613ba5/test/square.png "Square image"){#fig:square-image}

![
**An image too wide to fit within page at full size.**
Loaded from a specific (hashed) version of the image on GitHub.
](https://github.com/manubot/resources/raw/15493970f8882fce22bef829619d3fb37a613ba5/test/wide.png "Wide image"){#fig:wide-image}

![
**A tall image with a specified height.**
Loaded from a specific (hashed) version of the image on GitHub.
](https://github.com/manubot/resources/raw/15493970f8882fce22bef829619d3fb37a613ba5/test/tall.png "Tall image"){#fig:tall-image height=3in}

![
**A vector `.svg` image loaded from GitHub.**
The parameter `sanitize=true` is necessary to properly load SVGs hosted via GitHub URLs.
White background specified to serve as a backdrop for transparent sections of the image.
](https://raw.githubusercontent.com/manubot/resources/master/test/vector.svg?sanitize=true "Vector image"){#fig:vector-image height=2.5in .white}

## Tables

| *Bowling Scores* | Jane          | John          | Alice         | Bob           |
|:-----------------|:-------------:|:-------------:|:-------------:|:-------------:|
| Game 1 | 150 | 187 | 210 | 105 |
| Game 2 |  98 | 202 | 197 | 102 |
| Game 3 | 123 | 180 | 238 | 134 |

Table: A table with a top caption and specified relative column widths.
{#tbl:bowling-scores}

|         | Digits 1-33                        | Digits 34-66                      | Digits 67-99                      | Ref.                                                        |
|:--------|:-----------------------------------|:----------------------------------|:----------------------------------|:------------------------------------------------------------|
| pi      | 3.14159265358979323846264338327950 | 288419716939937510582097494459230 | 781640628620899862803482534211706 | [`piday.org`](https://www.piday.org/million/)               |
| e       | 2.71828182845904523536028747135266 | 249775724709369995957496696762772 | 407663035354759457138217852516642 | [`nasa.gov`](https://apod.nasa.gov/htmltest/gifcity/e.2mil) |

Table: A table too wide to fit within page.
{#tbl:constant-digits}

|          | **Colors** <!-- $colspan="2" --> |                      |
|:--------:|:--------------------------------:|:--------------------:|
| **Size** | **Text Color**                   | **Background Color** |
| big      | blue                             | orange               |
| small    | black                            | white                |

Table: A table with merged cells using the `attributes` plugin.
{#tbl: merged-cells}

## Equations

A LaTeX equation:

$$\int_0^\infty e^{-x^2} dx=\frac{\sqrt{\pi}}{2}$$ {#eq:regular-equation}

An equation too long to fit within page:

$$x = a + b + c + d + e + f + g + h + i + j + k + l + m + n + o + p + q + r + s + t + u + v + w + x + y + z + 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9$$ {#eq:long-equation}

## Special

<i class="fas fa-exclamation-triangle"></i> [WARNING]{.semibold} _The following features are only supported and intended for `.html` and `.pdf` exports._
_Journals are not likely to support them, and they may not display correctly when converted to other formats such as `.docx`._

[Link styled as a button](https://manubot.org "Manubot Homepage"){.button}

Adding arbitrary HTML attributes to an element using Pandoc's attribute syntax:

::: {#some_id_1 .some_class style="background: #ad1457; color: white; margin-left: 40px;" title="a paragraph of text" data-color="white" disabled="true"}
Manubot Manubot Manubot Manubot Manubot.
Manubot Manubot Manubot Manubot.
Manubot Manubot Manubot.
Manubot Manubot.
Manubot.
:::

Adding arbitrary HTML attributes to an element with the Manubot `attributes` plugin (more flexible than Pandoc's method in terms of which elements you can add attributes to):

Manubot Manubot Manubot Manubot Manubot.
Manubot Manubot Manubot Manubot.
Manubot Manubot Manubot.
Manubot Manubot.
Manubot.
<!-- $id="element_id" class="some_class" $style="color: #ad1457; margin-left: 40px;" $disabled="true" $title="a paragraph of text" $data-color="red" -->

Available background colors for text, images, code, banners, etc:  

`white`{.white}
`lightgrey`{.lightgrey}
`grey`{.grey}
`darkgrey`{.darkgrey}
`black`{.black}
`lightred`{.lightred}
`lightyellow`{.lightyellow}
`lightgreen`{.lightgreen}
`lightblue`{.lightblue}
`lightpurple`{.lightpurple}
`red`{.red}
`orange`{.orange}
`yellow`{.yellow}
`green`{.green}
`blue`{.blue}
`purple`{.purple}

Using the [Font Awesome](https://fontawesome.com/) icon set:

<!-- include the Font Awesome library, per: https://fontawesome.com/start -->
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.7.2/css/all.css">

<i class="fas fa-check"></i> <i class="fas fa-question"></i> <i class="fas fa-star"></i> <i class="fas fa-bell"></i> <i class="fas fa-times-circle"></i> <i class="fas fa-ellipsis-h"></i>

[
<i class="fas fa-scroll fa-lg"></i> **Light Grey Banner**<br>
useful for *general information* - [manubot.org](https://manubot.org/)
]{.banner .lightgrey}

[
<i class="fas fa-info-circle fa-lg"></i> **Blue Banner**<br>
useful for *important information* - [manubot.org](https://manubot.org/)
]{.banner .lightblue}

[
<i class="fas fa-ban fa-lg"></i> **Light Red Banner**<br>
useful for *warnings* - [manubot.org](https://manubot.org/)
]{.banner .lightred}
