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

  <link rel="alternate" type="text/html" href="https://dbudzik.github.io/project9_SHM/v/308463eef7c2f4ae81df46105f8a14998924e589/" />

  <meta name="manubot_html_url_versioned" content="https://dbudzik.github.io/project9_SHM/v/308463eef7c2f4ae81df46105f8a14998924e589/" />

  <meta name="manubot_pdf_url_versioned" content="https://dbudzik.github.io/project9_SHM/v/308463eef7c2f4ae81df46105f8a14998924e589/manuscript.pdf" />

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
([permalink](https://dbudzik.github.io/project9_SHM/v/308463eef7c2f4ae81df46105f8a14998924e589/))
was automatically generated
from [dbudzik/project9_SHM@308463e](https://github.com/dbudzik/project9_SHM/tree/308463eef7c2f4ae81df46105f8a14998924e589)
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
    [update_this](https://github.com/update_this)<br>
  <small>
  </small>

+ **Bolaji Lawal**<br>
    · ![GitHub icon](images/github.svg){.inline_icon}
    [update_this](https://github.com/update_this)<br>
  <small>
  </small>

+ **Abdullah Assaf**<br>
    · ![GitHub icon](images/github.svg){.inline_icon}
    [update_this](https://github.com/update_this)<br>
  <small>
  </small>



## Abstract {.page_break_before}




# 2. Exploratory Data Analysis

The goal of this EDA is to identify characteristics between damage and undamage conditions in order to perform data preparation and develope a model in the future steps.

## 2.1 Preparing the data
As the dataset shows, we have damage within our data. Therefore, Case 1 is not represented in train data.

The reason that there are accelerations values at the first row is because researchers started measuring the structure's response once it reached steady state. More details regarding the dynamic behavior of this structure will be discussed in the following sections.

Based on *Experimental Phase II of the Structural Health Monitoring Benchmark Problem* , accelerometers were placed throughout the structure to provide measurements of the structural response. For this Exploratory Data Analysis, three sensors from each floor of the 4-story structure were taken into consideration. Specifically,

Sensor 01 = Sensor located at the west side of the structure. 

Sensor 02 = Sensor located at the center of the structure.

Sensor 03 = Sensor located at the east side of the structure.

$Units = \frac{m}{s^2}$ 

- In the original data from the researchers, time is describe as,
$Time(seconds) = \frac{1 : Length_{DA04}}{fs_{days}}$ 

where fsdasy = 200 (Hz).


### Separating train data into damage and undamage dataset


*As shown above, the given data set contained a large quantity of NA data values which are all located in the undamaged portion.*

Between populating or removing the missing data, the missing results will be dropped. The reason for this decision is because populating the missing values with the mean of the training data will mostly develope a new dataset that does not have all the original parameters. 

## 2.2 Statistical Properties

We can learn certain details of the response of the structure by observing the data points that have a very drastic charnge in amplitude. In other words, there are common points in time among all sensors where the acceleration measured does a 180 degrees change. This phenomenon occurs as the dynamics response of structure is harmonic and it develops nodes. A simplification of this idea is to understand how the sensors in the 4th story will move back and forward while nodes underneath are ahead or behind that displacement.



The mean for all the sensors is very close to 0, which may indicate normalized normal distribution. Also, the standard deviation is not equal to 1 for any of the sensors, but a close value to 0 too. These characteristics are present for normal distributions of narrow dispersion.

In the case of undamaged dataset, the standard deviation values of the fourth floor are the largest among all floors. This indicates a flexibility in the structure as the dynamic response took place. Another very interesting fact that we can learn from the previous tables is how the maximum value of 0.01 takes place at two sensor in the 4 story, and the sensor located at the center for the 1st and 2nd floor. The absence of this value at the 3rd floor may indicate an anomaly. This value stays constant after the structure is considered damaged for the sensors located at the center of the second and fourth floor.


**Checking head, tail of data**

In the case of the undamaged dataset, all the graphs show normal distribution. However, they are not centered with an exact mean of value 0. Instead,

- Sensors located at the west side of the structure are skewed to the right in the first and fourth floor while the second and third floor are skewed to the left.
- Sensors located at the center of the structure behave symmetrically. The first and third floor have bell-shaped distribution with a mean of 0. The second and fourth floor are lightly skewed in opposite directions.
- Sensors located at the east side of the structure are all skewed except the one located at the second floor. The sensor at the 4th floor captured the most out of plane behavior as the '4th_story_03' sensor is significatly skewed to the left.

For the case of damage conditio, the normal distribution is not as smooth as shown for the undamaged condition. This behavior matches with the physical phenomenon that took place as the acceleration of the sensors will tend to be more extreme if the structure is damaged. 

- The first floor endured the most extreme values as the base is not static anymore during excitation. The three sensors are skewed to the right.
- The second and third floor has similar behavior since the center sensor is still normally distributed with mean very close to 0 and sensors on the west and east side are skewed to the left.
- The fourth floor now shows the most ccentered behavior. However, it is importqant to recall the statistical characteristics such as standard deviation. Now the 4th-floor values are significantly wider.

## 2.3 Exploring the dataframe that contains the undamaged condition**

Previously, we explored some characteristics of the undamaged dataset. Then, the dataset has been arranged and tidied to finally observe how there was a large amoung of non-available data points, which can be observed in the last row (index number > time_sec)

**Is the change in acceleration always the same?**

For the following inspection, recall that data acquisition was started several seconds after the excitation was turned on to ensure that the system had reached a steady state condition during the shaker testing.

Interestingly, the analysis has shown how the location of the sensor affects directly to the change in acceleration of the sensors. The y-axis has been kept constant throughout all the plots to ease comparison. Therefore, we can observe how though the distribution among sensors in different floor is different, the difference in acceleration values is very correlated to location.

Also note how the missing data produced zero values in the left portion of the data. Those values are not representing a constant acceleration.

**Correlation values**

The table above is with the purpose of locating the directly correlated and inversevely correlated sensors. Just as the difference in acceleration graphs showed, there is significant correlation between those sensors that are located in the same side of the structure. 

However, there is an inverse correlation in those sensors loccated at the fourth floor. The reason behind this behavior is that we are analyzing an elastic structure that is being excited by an harmonic input from the ground. Therefore, the top floor is swinging, which creates a driving behavior in one of the corners at a time.

**Boxplots**

Some final insight of the undamaged dataset shows how there are a large quantity of outliners in the sensors located at the center of the structure.

## 2.4 Exploring the dataframe that contains the undamaged condition**

**Is the change in acceleration always the same?**

There are certain conditions that we can observe by comparing the undamaged and damaged conditions. First of all, there is still a correlation in the change in acceleration with the location of the sensors. Also, the delta value has been significantly decreased over the length of the response. The largest change in acceleration is located at the center sensors for this particular condition, which might mean that the structure is not displacing as much once it reaches a damaged condition.

**Correlation values**

In this scenario, the correlation has changed greatly. Now, the 4th-story sensors display similarities with other sensors placed in the same side of the structure. However, the 3rd-story sensors are those that are inversely correlated. 

## 2.5 Conclussion

The training data obtained has been statistically explored, cleaned, and analyzed for the purpose of identifying parameters for modeling later on.

- Missing data has been removed.
- Datatype and Data Info has been discussed and visually listed.
- The distribution for the undamaged and damaged conditions proved to be normally distributed with skewness at different direction based on the sensors. This analysis portion showed how the skewness was correlated with the behavior that was taking place during excitation as the dynamic response of a steel frame structure is not rigid. Also, once the damaged condition was achieved, the distribution showed a larger standard deviation.
- The individual analysis of each condition proved to be succesful in correlating the behavior of each sensor among stories. 
    - The change in acceleration depended directly with the location on the sensor within the steel frame structure. 
    - There was a high correlation between sensors located at different floors that were place on the same side.    
- Due to the high symmetry among all the results and comparisons, it is probable that the training data belonged to Case 6, Case 7 or Case 8. However, the final information indicated how the 3rd story behaved differently, which potentially indicated that the training data has a higher probably of being Case 8.



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
