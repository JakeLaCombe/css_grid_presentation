% title: CSS Grid Basics
% subtitle: Reworking Layouts for modern day browsers
% author: <b>Jake LaCombe</b>
% author: Senior Software Engineer
% author: HealtheIntent Infrastructure Frameworks Frontend
% thankyou: Thanks everyone!
% thankyou_details: Feel free to contact me with further questions!

---
title: In our previous Episode
subtitle: We got Flexible
build_lists: true

CSS3 gave us the Flexbox which made laying out elements easier on a page

- Easy access to equal height columns
- Very easy to build navigation menus width.
- Prevents a lot of the hacks that had to be done in previous browsers with floats and position styles
---
title: Not all can be flexed
subtitle: Try flexing frozen laffy taffy
build_lists: true

Flexbox gave us solutions, but it didn't address all of our concerns.

- Flexbox was designed to adjust space for content in it's individual container.
- Flexboxes only go one dimension. 
- This can make it tricky to align items that are on multiple rows/containers in a layout.
---
class: centered-title

<h1 class="large-text">Todays Solution - CSS Grid</h1> 
---
title: Introduction to CSS Grid

- CSS Grid is a specification in CSS3 that allows you declare a layout with 2 dimensions.
- Declaring a container as a gridded container allows for the alignment of children in regards to rows and columns

<footer class="source">
  <dl>
    <dt>A Complete Guide to Grid by CSS Tricks</dt>
    <dd>https://css-tricks.com/snippets/css/complete-guide-grid/</dd>
  </dl>
</footer>

---
title: Benefits of a CSS Grid

- You no longer need any extra containers to get your grid working.
- Very easy to flex your template on different breakpoints.

<pre class="prettyprint" data-lang="html">
  &lt;ul&gt;
    &lt;li&gt;Item 1&lt;/li&gt;
    &lt;li&gt;Item 2&lt;/li&gt;
    &lt;li&gt;Item 3&lt;/li&gt;
  &lt;/ul&gt;
</pre>
<pre class="prettyprint" data-lang="css">
  ul {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
</pre> 
---
title: Code Sample

<p data-height="265" data-theme-id="0" data-slug-hash="VMNKoE" data-default-tab="css,result" data-user="JakeLaCombe" data-embed-version="2" data-pen-title="VMNKoE" class="codepen">See the Pen <a href="https://codepen.io/JakeLaCombe/pen/VMNKoE/">VMNKoE</a> by Jake LaCombe (<a href="https://codepen.io/JakeLaCombe">@JakeLaCombe</a>) on <a href="https://codepen.io">CodePen</a>.</p>
---
title: Getting Started with the CSS Grid

- To get started, add <code>display: block</code> to your container.
- That's all you need to start a one column layout. If you want more columns, set <code>grid-template-columns</code> on the container, specifying a width for every column you wish to have in your grid.
- Once you have that setup, your gridding is good to go.
---
class: centered-title

<h1 class="large-text">Gridding Terminology</h1>
---
title: Gridding Terminology

<dl class="slide-definition-list">
  <dt>Grid Line</dt>
  <dd>Horizontal and Vertical Lines that define the grid</dd>
  <dt>Grid Track</dt>
  <dd>Space between two lines (row or column)</dd>
  <dt>Grid Cell</dt>
  <dd>Space between four lines</dd>
  <dt>Gutter</dt>
  <dd>Space Between Cells</dd>
</dl>

---
title: Gridding Terminology

<dl class="slide-definition-list">
  <dt>Grid Row</dt>
  <dd>Horizontal Arrangement in a grid</dd>
  <dt>Grid Column</dt>
  <dd>Vertical Arrangement in a grid</dd>
  <dt>Grid Area</dt>
  <dd>Rectangular arrangement in a Grid.</dd>
</dl>
---
title: Gridding Terminology
subtitle: Now you know

<img src="figures/the_grid.jpg"/>
---
class: centered-title

<h1 class="large-text">CSS Properties - The Parent</h1>
---
title: CSS Properties - The Parent

- <code>display:</code> - You have multiple choices for this category. <code>grid, inline-grid, or subgrid</code>
    - <code>subgrid</code> - This display tells a grid inside a grid to inherit it's template from it's parent.
---
title: CSS Properties - The Parent
subtitle: Structural Properties

- <code>grid-template-columns:</code> How many columns do you want, and how much space you want for each column. (Can be percentages, set widths, and fractals).
    - <code>grid-template-columns: 1fr 2fr 1fr 100px;</code>
    - <code>grid-template-columns: repeat(6, 1fr);</code>
- <code>grid-template-row:</code> How many row do you want, and how much space you want for each column.
    - <code>grid-template-row: 100px 1fr;</code>
    - <code>grid-template-columns: repeat(3, 1fr);</code>
---
title: Terminology Break - Grid Types!
subtitle: Previous properties define grid type

<dl class="slide-definition-list">
  <dt>Implicit Grid</dt>
  <dd>A grid that is infinitely repeating. Set by default, and configured with <code>grid-template-columns.</code></dd>
  <dt>Explicit Grid</dt>
  <dd>A grid that is finite. To configure this, set <code>grid-template-rows.</code></dd>
</dl>

<u>(Note: If you supply more cells than space available, any cells after the area turn into an implicit grid).</u>
---
title: CSS Properties - The Parent
subtitle: Structural Explicit Properties

- <code>grid-auto-columns:</code> Lengths for each auto generated column. Multiple can be provided. (Can be percentages, set widths, and fractals).
    - <code>grid-auto-columns: 1fr 2fr 1fr 100px;</code>
    - <code>grid-auto-columns: repeat(6, 1fr);</code>
- <code>grid-auto-rows:</code> Lengths for each auto generated row. Multiple can be provided.
    - <code>grid-auto-rows: 100px 1fr;</code>
    - <code>grid-auto-rows: repeat(3, 1fr);</code>
---
title: CSS Properties - The Parent
subtitle: Gaps

- <code>grid-row-gap:</code> Gap you want between cells on the vertical axis.
- <code>grid-column-gap:</code> Gap you want between cells on the horzontal axis.
- <code>grid-gap:</code> Short-handed notation <code>&lt;grid-row-gap grid-column-gap&gt;</code>. A single value can be provided as well that gets applied to both the row and the column gaps.
---
title: CSS Properties - The Parent
subtitle: Alignment of Children

- <code>align-items:</code> How items should be aligned on the column axis.
    - If you want to align an individual cell, use <code>align-self</code> property on the specific child.
- <code>justify-items:</code> How items should be aligned on the row axis.
    - If you want to align an individual cell, use <code>justify-self</code> property on the specific child.
- Values - <code>start | end | center | stretch</code>
---
title: CSS Properties - The Parent
subtitle: Alignment of the actual grid

- <code>align-content:</code> How the grid should be aligned on the column axis.
- <code>justify-content:</code> How the grid should be aligned on the row axis.
- Values - <code>start | end | center | stretch | space-around | space-between | space-evenly</code>
---
class: centered-title

<h1 class="large-text">CSS Properties - The Children</h1>
---
title: CSS Properties - The Children
subtitle: Positioning Properties

- <code>grid-row-start:</code> What row the child should be positioned at. Starts at 1.
- <code>grid-row-end:</code> What row the child should end at. Starts at 1.
- <code>grid-column-start:</code> What column the child should be positioned at. Starts at 1.
- <code>grid-column-end:</code> What column the child should end at. Starts at 1.
---
title: CSS Properties - The Children
subtitle: Short Handed Positioning Properties

- <code>grid-row:</code> - <code>&lt;grid-row-start&gt; / &lt;grid-row-end&gt;</code>.
- <code>grid-column:</code> - <code>&lt;grid-column-start&gt; / &lt;grid-column-end&gt;</code>.
---
title: CSS Properties - The Children
subtitle: Positioning End

- The end properties for position do not have to be specific column positions.
- Custom identifiers can be provided to these values as well.
    - <code>grid-row-end: span 4;</code> would take a cell and span it 4 rows.
    - <code>grid-column-end: span 4;</code> would take a cell and span it 4 columns.
---
title: CSS Properties - The Children
subtitle: Positioning End Example

<p data-height="135" data-theme-id="0" data-slug-hash="oGRawM" data-default-tab="css,result" data-user="JakeLaCombe" data-embed-version="2" data-pen-title="oGRawM" class="codepen">See the Pen <a href="https://codepen.io/JakeLaCombe/pen/oGRawM/">oGRawM</a> by Jake LaCombe (<a href="https://codepen.io/JakeLaCombe">@JakeLaCombe</a>) on <a href="https://codepen.io">CodePen</a>.</p>
---
class: centered-title

<h1 class="large-text">Grid Areas</h1>
---
title: CSS Properties - The Children
subtitle: Positioning End

- In addition to templating the rows and columns of a grid, you can template the entire grid area as well!
- You essentially give all of your grid cells an identifier, and then tell the cells to go to match those identifiers.
- To start, set <code>grid-template-areas</code> on the grid, and then set <code>grid-area</code> on the individual children.
- <b>Note:</b> You can only have an explicit area with grid-area. Any grid items that do not correspond to a cell identifier get placed on the implicit tracts of a grid.
---
title: Grid Area Example

<p data-height="265" data-theme-id="0" data-slug-hash="OxYBaP" data-default-tab="css,result" data-user="JakeLaCombe" data-embed-version="2" data-pen-title="OxYBaP" class="codepen">See the Pen <a href="https://codepen.io/JakeLaCombe/pen/OxYBaP/">OxYBaP</a> by Jake LaCombe (<a href="https://codepen.io/JakeLaCombe">@JakeLaCombe</a>) on <a href="https://codepen.io">CodePen</a>.</p>
---
class: centered-title

<h1 class="large-text">Browser Support</h1>
---
title: Browser Support for Grid

- All modern browsers (Chrome, Safari, Firefox, Edge < 16) support CSS Grid implementation
- IE 10, IE11, and early edge support an old implementation of CSS Grid
---
title: IE & Early Edge
subtitle: Worse than working at Amazon

- Sadly, grid isn't as easy as just adding vendor prefixes to the grid styles.
- <a href="https://rachelandrew.co.uk/archives/2016/11/26/should-i-try-to-use-the-ie-implementation-of-css-grid-layout/">Syntax</a> of IE and Edge have quite a different pair of mappings.
- In addition, grids in IE can only be declared explicitly. No infinite grids with the IE implementation.
- Gaps aren't fully supported as well. To get gaps, you have to include them in your column template.
---
title: Should we use it?

- Yes!!!!
- Browsers are starting to catch up to the grid implementation.
- Terra has a solution that assists with the IE grid differences as well. Checkout <a href="https://github.com/cerner/terra-core/tree/master/packages/terra-dynamic-grid">terra-dynamic-grid</a>.
- It'll make your markup look much better than it did before!
---
class: centered-title

<h1 class="large-text">Flexbox Layout vs Grid Layout</h1>
---
title: When to use one over the other
subtitle: It's not a black and white choice.

- First, remember the definition between the two
    - Flexbox is for having elements take as much space as needed for it's given container
    - Grid is for getting elements to align in a two dimensional system.
- There are cases for when you want to make sidebars as large as they need to be for example.
---
title: Layout done strictly with CSS Flexbox

<p data-height="265" data-theme-id="0" data-slug-hash="boXvXW" data-default-tab="css,result" data-user="JakeLaCombe" data-embed-version="2" data-pen-title="boXvXW" class="codepen">See the Pen <a href="https://codepen.io/JakeLaCombe/pen/boXvXW/">boXvXW</a> by Jake LaCombe (<a href="https://codepen.io/JakeLaCombe">@JakeLaCombe</a>) on <a href="https://codepen.io">CodePen</a>.</p>
---
title: Layout done strictly with CSS Grid

<p data-height="265" data-theme-id="0" data-slug-hash="LzwdoK" data-default-tab="css,result" data-user="JakeLaCombe" data-embed-version="2" data-pen-title="LzwdoK" class="codepen">See the Pen <a href="https://codepen.io/JakeLaCombe/pen/LzwdoK/">LzwdoK</a> by Jake LaCombe (<a href="https://codepen.io/JakeLaCombe">@JakeLaCombe</a>) on <a href="https://codepen.io">CodePen</a>.</p>
---
title: Combining Both Flexbox and Grid
subtitle: Both can be combined.

<p data-height="265" data-theme-id="0" data-slug-hash="MENVdG" data-default-tab="css,result" data-user="JakeLaCombe" data-embed-version="2" data-pen-title="MENVdG" class="codepen">See the Pen <a href="https://codepen.io/JakeLaCombe/pen/MENVdG/">MENVdG</a> by Jake LaCombe (<a href="https://codepen.io/JakeLaCombe">@JakeLaCombe</a>) on <a href="https://codepen.io">CodePen</a>.</p>
---
title: Case for Flexbox
subtitle: Great for Yoga Websites

- You don't care about aligning elements from line to line. 
- You just want stuff to take as much space as it needs.
- Your layout goes in just one dimension.
---
title: Case for Grid
subtitle: Great for Flynn and his Son

- You need elements to align from row to row.
- Your items span in two dimensions.
