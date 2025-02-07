# Contributing to the 3D Artist's Handbook

First off, thanks for taking the time to contribute!

The following is a set of guidelines and helpful information for contributing to the 3D Artist's Handbook, which is
hosted on [GitHub](https://github.com/sidney-eliot/3d-artists-handbook). These are mostly guidelines, not rules. Use
your best judgment, and feel free to propose changes to this document in a pull request.

#### Table of Contents

- [Code of Conduct](#code-of-conduct)
- [What Should I Know Before I Get Started?](#what-should-i-know-before-i-get-started)
   - [Set-up for Contributing](#set-up-for-contributing)
   - [How Can I Contribute?](#how-can-i-contribute)
   - [Work in Progress Sections](#work-in-progress-sections)
- [Styleguides](#styleguides)
   - [General](#general)
   - [Specific](#specific)
   - [Markdown](#markdown)

## Code of Conduct

This project and everyone participating in it is governed by the
[3D Artist's Handbook Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## What Should I Know Before I Get Started?

### Set-up for Contributing

1. You will need to have [Node.js](https://nodejs.org/en/download). To check the current version and see if it's
   properly installed, use `node - v` & `npm - v` in your terminal of choice. _(The minimum required node version is v20
   and the minimum npm version is v9.3.1. If this is outdated for whatever reason, look at
   [quartz](https://quartz.jzhao.xyz/).)_

2. In addition to that, it's also recommended to use a version control software, like
   [GitHub Desktop](https://desktop.github.com/download/).

2. Next, create your [own fork](https://github.com/sidney-eliot/3d-artists-handbook/fork) of this repository.

3. Then, inside a version control software like GitHub Desktop, add the repository you just forked via the clone
   function (_File > Clone repository_. The HTTPS link can be copied from the main repository page with the _<> Code_ button).

4. Inside the repository folder, navigate into the "_src_" folder and inside it, using any terminal, execute the following commands:

   ```shell
   npm i
   npx quartz build --serve
   ```

6. Now, open a new browser window with the address: [https://localhost:8080](https://localhost:8080)  
   Note: If the above commands worked properly, you should see a prompt with this address as a result.

Congratulations! Everything is set up, and you can start authoring pages, preferable in [Obsidian](https://obsidian.md/). 
Also, before you get started with writing, please try to familiarize yourself with the [styleguides](#styleguides) below.
And finally, when you are ready to share your changes via a
[pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests),
it's a good idea to first test the page locally in your browser to see if your changes are as you expected.

### How Can I Contribute?

There are quite a bit of ways to contribute; here are a few examples:

- General proofreading and grammar.
- Improving on topics you are very knowledgeable in.
- Making or answering [Issues](https://github.com/sidney-eliot/3d-artists-handbook/issues).
- Making [Pull Requests](https://github.com/sidney-eliot/3d-artists-handbook/pulls).
- Suggesting ideas or asking / answering questions in the repo's
  [Discussions](https://github.com/sidney-eliot/3d-artists-handbook/discussions).

The owner of this repo, Sidney, can also be contacted on Discord with the username `epicrex`.

### Work in Progress Sections

Work in progress pages are in the `src/content/work_in_progress` folder and are hidden from the website, meaning they can
contain rough drafts. Inside this folder, you can create your own folder, like `YourName-wip`.
You can, of course, also keep your work in progress local or in your fork, but some like to share their work in progress
pages with others so that others might take over and continue fine-tuning them.

Some pages, however, will contain a work in progress section at the bottom of the page with the header "🚧 Work in
Progress 🚧". The stuff here is in a state that is readable and mostly factually correct, but just not integrated into
the page yet.

_It's very possible that in the future no more work in progress stuff will be allowed on the live handbook pages, and
instead all go into the work_in_progress folder, but for now, it will be this way._

## Styleguides

Keeping keywords and key terms consistent is important. There are two key reasons:

Firstly, inconsistencies can lead to confusion. For example, ZBrush has something called a "Tool" emphasis on the
capital T. Seeing this immediately shows the reader that the ZBush Tool is being talked about and not the English word
"tool".

The second reason is the searchability of terms when using the Quartz built-in search bar or your browser's `Ctrl` + `F`
page search.

### General

|                                | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                 Examples                 |
| :----------------------------: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------------------: |
|          **Language**          | Use American English and not British English.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |            color, not colour             |
| **How to Address the Readers** | It has not been decided yet if the reader is to be addressed with "you" or if one rather uses "one". Currently, most of the handbook uses "one". (Trying not to address the reader as much as possible is also an option.)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                You or One                |
|       **Writing Style**        | Be concise and informative with what you write, trying to keep sentences only as long as they have to bey to convey the point that is being made. Treat the writing style more like a scientific research paper and less like some article. <br><br>Your north star should be to not unnecessarily waste the reader's time while at the same time not skimping out on detailed information.<br><br>There are many ways of doing this, and often restructuring a sentence can make it a lot shorter while still keeping the important information. It can also be a good idea to try to get to the point relatively quickly and to go into more detail in subsections like admonition blocks.<br><br>3D is quite a complex subject, and the oversight can often be lost, so keeping things intuitively structured is also important. |                                          |
|     **Showing Menu Paths**     | Use the greater-than angle brackets `>` to show the flow of navigation through menus. Make sure to keep a space between the arrows and words. Lastly´, make the entire path Italic (Italics are done with `_`).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |            _Settings > Path_             |
|      **Showing Hotkeys**       | Use [inline code](https://help.obsidian.md/Editing+and+formatting/Basic+formatting+syntax#Inline+code) _(or inline literals)_, separated with a `+`, to format each keystroke in a certain shortcut _(hotkey)_. (Inline code: <code>`</code>)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |               `Ctrl` + `F`               |
|       **Units Denoter**        | The unit value and the denoter should be together without a spacing. In addition, the denoter should be lowercase.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |    16px, 16bit, 16cm, 16m, 16km, 16kg    |
|        **Unit System**         | Use the metric system (no inches or feet, for example).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                                          |
|          **Headings**          | The biggest heading a page should have is H2. Furthermore, don't add hashtags `#` behind headers.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                ## Heading                |
|       **Capitalization**       | Besides using basic English grammar for capitalization, there are some other things worth mentioning. Headers in pages should follow the [Chicago capitalization](https://en.wikipedia.org/wiki/Title_case) guideline. (If unsure, this [Capitalize My Title](https://capitalizemytitle.com/style/Chicago/) website can help format headers. Always capitalize software and tool names.) Lastly, for the headers of admonitions / callout blocks, use normal sentence capitalization.                                                                                                                                                                                                                                                                                                                                               |                                          |
|           **Links**            | Links to articles or YouTube videos should, if possible, include the name or some information, so that if the link is broken because the website or video is taken down, the reader can maybe still find it through some searching.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |        [Descriptive Link Name]()         |
|           **Images**           | Never ever add images via links. Always download the image and add it to the "_.../content/images_" folder. This is because it's quite likely that in a couple of years that image will not exist anymore at its source (e.g., the recent Imgur collapse).<br><br>Also, try keeping the image at reasonable file sizes (like under 500kb) and, if possible, in the JPG image format, to not affect page load times.                                                                                                                                                                                                                                                                                                                                                                                                                 |                                          |
|      **File Extensions**       | When writing out a file name that includes a file extension, write the extension in lowercase. However, when talking about a file extension in a general sense, remove the dot and capitalize all letters.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |   .png, .blend, .zpr / PNG, BLEND, ZPR   |
|  **Abbreviations & Acronyms**  | Try not to use abbreviations, except if they are very commonly used. Like the term UDIM which stands for U DIMension but is only ever used in its abbreviated form.<br><br>Using common abbreviations like: etc. (Et Cetera), i.e. (in other words), e.g. (for example), c.a. (circa / about) is ok, but writing it out is just as valid.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |       UDIM, etc., i.e., e.g., c.a.       |
|        **Contraction**         | Use contractions whenever possible, as they will mostly make sentences sound more fluent and pretty (e.g. "has not" becomes "hasn't").                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | doesn't, don't, hasn't, he'll, it's, ... |
|          **Slashes**           | When using slashes, always leave a space before and after the slash.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |          1 / 2, Blender / Maya           |
|            **Bold**            | No standards yet. May be good for highlighting key terms, but try to use it sparingly.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |                                          |

### Specific

| Recommended spelling |                                                                                                                                    What it refers to                                                                                                                                     | Names often used                                                                             |
| :------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | -------------------------------------------------------------------------------------------- |
|        SubDiv        | Most 3D software uses the Subdivision Surface Algorithm, and nearly all of them use different names to refer to it. If one doesn't want to abbreviate it in a specific context for whatever reason, then one should call it: **Subdivision Surface** or **Subdivision Surface Algorithm** | Subdivision Surface, Subdivision Surface Algorithm, Subdivision Surface Modifier, SDiv, SubD |
|         Tool         |                                                                                            The entire model in ZBrush is referred to as a Tool (It's, so to speak, a container for SubTools).                                                                                             |                                                                                              |
|       SubTool        |                                                                                                                      Objects in ZBrush are referred to as SubTools.                                                                                                                      |                                                                                              |
|      polypaint       |                                                                                                                                                                                                                                                                                          |                                                                                              |
|       topology       |                                                                                                                                                                                                                                                                                          | topo                                                                                         |
|      real-time       |                                                                                                                                                                                                                                                                                          | Real-time, Realtime, realtime                                                                |
|   hyper-realistic    |                                                                                                                                                                                                                                                                                          |                                                                                              |
|        MatCap        |                                                                                                                 Capitalized M and C, as it's short for Material Capture.                                                                                                                 | Matcap, matcap                                                                               |
|  vertex & vertices   |                                                                                                         Properly use the plural (vertices) and singular (vertex) form of vertex.                                                                                                         |                                                                                              |
|      triangles       |                                                                                          This is a tricky one and not yet decided, so for now, it's ok to say either 30k triangles or 30k tris.                                                                                          |                                                                                              |

### Markdown

Nearly all Markdown syntax and most of the Obsidian Markdown syntax is supported (HTML works as well). Here's a quick
refresher.

#### Basic Formatting

**BOLD** `**BOLD**`, _Italic_ `_Italic_`, `Inline code` with back ticks <code>`</code>, code blocks with triple back
ticks <code>```</code> above and below text.

####  Headings

```
# H1 <<< Reserved for the page `title:` property inside the YAML. Don't use it in the content (markdown).

## H2 <<< Will be visible in table of contents
### H3 <<< Will be visible in table of contents
#### H4 <<< Won't be visible in table of contents
```

#### Images

```
![[image-name.jpg]]
```

#### Admonitions / Callout blocks

```
> [!note] Title of note
>
> Note content
```

#### Internal Links

When linking to internal pages, **always** give them a name as not doing so can lead to issues.

```diff
- [[Page Name]] <<< Don't do this

+ [[Page Name|Name of Link to Page]]
+ [[Page Name#Header Name|Name of Link to Page Header]]
```

#### External Links

Descriptive URL names are important as one doesn't know if the URL might become unavailable over time.

```
[Descriptive URL Name](https://www.google.com)
```

#### Some useful HTML

```
Line Break:
<br>
```

#### YouTube Video Embedding

Under a YouTube video, click _Share > Embed > Copy_. Always make sure to check "Enable privacy-enhanced mode" and if
desired check start "Start at ..." to skip to the vital point in the video.

For example:

```
<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/dQw4w9WgXcQ?si=rZWhyUfBwWCAb52p&amp;start=8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
```

Sadly, HTML iframes are a thing of the past as most websites nowadays block themselves from being framed, YouTube
however, allows it.

#### Tables

```
Center-aligned table content:

|Name 1|Name 2|Name 3|
|:-:|:-:|:-:|
|Value 1|Value 2|Value 3|

Left and right aligned table content:

|Name 1|Name 2|
|:-|-:|
|Left aligned value|Right aligned value|
```

> [!tip]
> Obsidian makes it easy to add new columns and rows to a table via a + button at the very bottom / right of tables
> (assuming you aren't currently in the source code view mode).

For more complex tables (e.g. tables with cell merging, advanced styling, etc.), please consider using HTML.

#### Segment Line

Sometimes it's helpful to create splits that make information more digestible; try not to overuse it.
Seperating the two logical concepts you are writing about into two separate pages is something to ponder before
committing to using this.

```
---
```

---

_(Helpful links for writing a CONTRIBUTING.md: https://mozillascience.github.io/working-open-workshop/contributing/, https://github.com/atom/atom/blob/master/CONTRIBUTING.md)_
