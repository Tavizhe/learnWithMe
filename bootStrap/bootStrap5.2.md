# bootStrap 5.2 Learning

Bootstrap is the most popular CSS Framework for developing responsive and mobile-first websites. ==Bootstrap== is a more widely used framework that ==uses CSS and JavaScript==.

## Layouts:

---

### Containers:

Containers are for building blocks of Bootstrap that ==contain, pad, and align== your content within a given device or viewport.
Our default .container class is a responsive, fixed-width container, meaning its max-width changes at each breakpoint.

**Bootstrap comes with three different containers**:

- ==.container==, which sets a max-width at each responsive breakpoint
- ==.container-{breakpoint}==, which is width: 100% until the specified breakpoint
- ==.container-fluid==, which is width: 100% at all breakpoints

For example, .container-sm is 100% wide to start until the sm breakpoint is reached, where it will scale up with md, lg, xl, and xxl.

| max-width        | Extra small <576px | Small ≥576px | Medium ≥768px | Large ≥992px | X-Large ≥1200px | XX-Large ≥1400px |
| ---------------- | ------------------ | ------------ | ------------- | ------------ | --------------- | ---------------- |
| .container       | 100%               | 540px        | 720px         | 960px        | 1140px          | 1320px           |
| .container-sm    | 100%               | 540px        | 720px         | 960px        | 1140px          | 1320px           |
| .container-md    | 100%               | 100%         | 720px         | 960px        | 1140px          | 1320px           |
| .container-lg    | 100%               | 100%         | 100%          | 960px        | 1140px          | 1320px           |
| .container-xl    | 100%               | 100%         | 100%          | 100%         | 1140px          | 1320px           |
| .container-xxl   | 100%               | 100%         | 100%          | 100%         | 100%            | 1320px           |
| .container-fluid | 100%               | 100%         | 100%          | 100%         | 100%            | 100%             |

You may customize these predefined container classes by modifying the Sass map (found in \_variables.scss) that powers them:

```Sass
$container-max-widths: (
  sm: 540px,
  md: 720px,
  lg: 960px,
  xl: 1140px,
  xxl: 1320px
);
```

in order to add size checker in html add this:

```html
<div>
  <div class="js-sidebar">
    <div class="card d-none">
      <h5 class="card-header">Page Navigation:</h5>
      <div class="list-group list-group-flush" id="page-navigation"></div>
    </div>
  </div>
</div>
<script src="bootstrap.bundle.min.js"></script>
<script src="/Learning Kit/js/jquery.min.js"></script>
<script>
  //for adding size checker
  function currentBreakpoint() {
    var breakpointMarkup =
      '<div class="card bg-light mb-3"><div class="card-body"><div class="btn-group btn-group-sm flex-wrap mb-3"><span class="pe-none btn btn-primary d-inline-block d-sm-none">XS</span><span class="pe-none btn btn-secondary d-none d-sm-inline-block">XS</span><span class="pe-none btn btn-primary d-none d-sm-inline-block d-md-none">SM</span><span class="pe-none btn btn-secondary d-sm-none d-md-inline-block">SM</span><span class="pe-none btn btn-primary d-none d-md-inline-block d-lg-none">MD</span><span class="pe-none btn btn-secondary d-md-none d-lg-inline-block">MD</span><span class="pe-none btn btn-primary d-none d-lg-inline-block d-xl-none">LG</span><span class="pe-none btn btn-secondary d-lg-none d-xl-inline-block">LG</span><span class="pe-none btn btn-primary d-none d-xl-inline-block d-xxl-none">XL</span><span class="pe-none btn btn-secondary d-xl-none d-xxl-inline-block">XL</span><span class="pe-none btn btn-primary d-none d-xxl-inline-block">XXL</span><span class="pe-none btn btn-secondary d-xxl-none">XXL</span></div><small class="d-block d-sm-none">Extra small: &lt;576px</small><small class="d-none d-sm-block d-md-none">Small: ≥576px</small><small class="d-none d-md-block d-lg-none">Medium: ≥768px</small><small class="d-none d-lg-block d-xl-none">Large: ≥992px</small><small class="d-none d-xl-block d-xxl-none">Extra large: ≥1200px</small><small class="d-none d-xxl-block">Extra extra large: ≥1400px</small></div></div></div>';
    $(".js-sidebar").prepend(breakpointMarkup);
  }
  currentBreakpoint();
</script>
```

### Grid system:

powerful mobile-first flex box grid that can build layouts of all shapes and sizes thanks to a twelve column system, uses a series of containers, rows, and columns to layout and align content. It’s built with flex box and is fully responsive.

simple example:

```html
<div class="container text-center">
  <div class="row">
    <div class="col">Column</div>
    <div class="col">Column</div>
    <div class="col">Column</div>
  </div>
</div>
```

will be :
![](/images/1.PNG)
in every viewport.

> grid supports six responsive breakpoints. Breakpoints are based on ==min-width==. This means you can control container and column sizing and behavior by each breakpoint. So remember:
>
> - Rows are wrappers for columns. Each column has horizontal padding (called a gutter) for controlling the space between them.
>   will be like this:
>   ![](/images/12.PNG)

```html
<div class="container px-4 text-center">
  <div class="row gx-5">
    <div class="col">
      <div class="p-3 border bg-light">Custom column padding</div>
    </div>
    <div class="col">
      <div class="p-3 border bg-light">Custom column padding</div>
    </div>
  </div>
</div>
```

> - There are 12 template columns available per row, allowing you to create different combinations of elements that span any number of columns. Column classes indicate the number of template columns to span `col-4 //spans four`.

#### Grid options:

1. Extra small (xs)
2. Small (sm)
3. Medium (md)
4. Large (lg)
5. Extra large (xl)
6. Extra extra large (xxl)

| Grid Table          | xs <576px  | sm ≥576px | md ≥768px | lg ≥992px | xl ≥1200px | xxl ≥1400px |
| ------------------- | ---------- | --------- | --------- | --------- | ---------- | ----------- |
| Container max-width | None(auto) | 540px     | 720px     | 960px     | 1140px     | 1320px      |
| Class prefix        | .col-      | .col-sm-  | .col-md-  | .col-lg-  | .col-xl-   | .col-xxl-   |

#### Auto-layout columns:

easy column sizing without an explicit numbered class like .col-sm-6.

##### Equal-width

```html
<div class="container text-center">
  <div class="row">
    <div class="col">1 of 2</div>
    <div class="col">2 of 2</div>
  </div>
  <div class="row">
    <div class="col">1 of 3</div>
    <div class="col">2 of 3</div>
    <div class="col">3 of 3</div>
  </div>
</div>
```

will be:
![](/images/2.PNG)

##### Setting one column width

```html
<div class="container text-center">
  <div class="row">
    <div class="col">1 of 3</div>
    <div class="col-6">2 of 3 (wider)</div>
    <div class="col">3 of 3</div>
  </div>
  <div class="row">
    <div class="col">1 of 3</div>
    <div class="col-5">2 of 3 (wider)</div>
    <div class="col">3 of 3</div>
  </div>
</div>
```

will be:
![](/images/3.PNG)

##### Variable width content

Use `col-{breakpoint}-auto` classes to size columns based on the natural width of their content.

```html
<div class="container text-center">
  <div class="row justify-content-md-center">
    <div class="col col-lg-2">1 of 3</div>
    <div class="col-md-auto">Variable width content</div>
    <div class="col col-lg-2">3 of 3</div>
  </div>
  <div class="row">
    <div class="col">1 of 3</div>
    <div class="col-md-auto">Variable width content</div>
    <div class="col col-lg-2">3 of 3</div>
  </div>
</div>
```

will be:
![](/images/4.PNG)

#### Responsive classes

##### Stacked to horizontal

Using a single set of `col-sm` classes, you can create a basic grid system that starts out stacked and becomes horizontal at the small breakpoint (sm).

```html
<div class="container text-center">
  <div class="row">
    <div class="col-sm-8">col-sm-8</div>
    <div class="col-sm-4">col-sm-4</div>
  </div>
  <div class="row">
    <div class="col-sm">col-sm</div>
    <div class="col-sm">col-sm</div>
    <div class="col-sm">col-sm</div>
  </div>
</div>
```

will be:
![](/images/5.PNG)

#### Mix and match

```html
<div class="container text-center">
  <!-- Stack the columns on mobile by making one full-width and the other half-width -->
  <div class="row">
    <div class="col-md-8">.col-md-8</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
  </div>

  <!-- Columns start at 50% wide on mobile and bump up to 33.3% wide on desktop -->
  <div class="row">
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
    <div class="col-6 col-md-4">.col-6 .col-md-4</div>
  </div>

  <!-- Columns are always 50% wide, on mobile and desktop -->
  <div class="row">
    <div class="col-6">.col-6</div>
    <div class="col-6">.col-6</div>
  </div>
</div>
```

will be like below in xxl:
![](/images/6.PNG)

will be like below in md:
![](/images/7.PNG)

#### Row columns

Use the responsive `.row-cols-*` classes to quickly set the number of columns that best render your content and layout.

```html
<div class="container text-center">
  <div class="row row-cols-2">
    <div class="col">Column</div>
    <div class="col">Column</div>
    <div class="col">Column</div>
    <div class="col">Column</div>
  </div>
</div>
```

will be:
![](/images/8.PNG)

```html
<div class="container text-center">
  <div class="row row-cols-auto">
    <div class="col">Column</div>
    <div class="col">Column</div>
    <div class="col">Column</div>
    <div class="col">Column</div>
  </div>
</div>
```

will be:
![](/images/9.PNG)

> You can also use the accompanying Sass mixin, `row-cols()`:

```css
.element {
  // Three columns to start
  @include row-cols(3);

  // Five columns from medium breakpoint up
  @include media-breakpoint-up(md) {
    @include row-cols(5);
  }
}
```

#### Nesting

To nest your content with the default grid, add a new .row and set of .col-sm-_ columns within an existing .col-sm-_ column.

```html
<div class="container text-center">
  <div class="row">
    <div class="col-sm-3">Level 1: .col-sm-3</div>
    <div class="col-sm-9">
      <div class="row">
        <div class="col-8 col-sm-6">Level 2: .col-8 .col-sm-6</div>
        <div class="col-4 col-sm-6">Level 2: .col-4 .col-sm-6</div>
      </div>
    </div>
  </div>
</div>
```

will be in md:
![](/images/10.PNG)

will be in sm:
![](/images/11.PNG)

---

## Content

### Typography

#### Headings

there is always html tags

```html
<h1>Bootstrap heading</h1>
<h6>Bootstrap heading</h6>
```

then there is classes:

```html
<p class="h1">Bootstrap heading</p>
<p class="h6">Bootstrap heading</p>
```

When you need a heading to stand out, consider using a display heading—a larger, slightly more opinionated heading style.

```html
<h1 class="display-1">Display</h1>
<h6 class="display-6">Display</h6>
```

##### Customizing headings

```html
<h3>
  Fancy display heading
  <small class="text-muted">With faded secondary text</small>
</h3>
```

Make a paragraph stand out by adding `.lead`.

```html
<p class="lead">
  This is a lead paragraph. It stands out from regular paragraphs.
</p>
```

#### Inline text elements

```html
<p>You can use the mark tag to <mark>highlight</mark> text.</p>
<p><del>This line of text is meant to be treated as deleted text.</del></p>
<p><s>This line of text is meant to be treated as no longer accurate.</s></p>
<p>
  <ins
    >This line of text is meant to be treated as an addition to the
    document.</ins
  >
</p>
<p><u>This line of text will render as underlined.</u></p>
<p><small>This line of text is meant to be treated as fine print.</small></p>
<p><strong>This line rendered as bold text.</strong></p>
<p><em>This line rendered as italicized text.</em></p>
```

will be:
![](/images/13.PNG)

#### Abbreviations

```html
<p><abbr title="attribute">attr</abbr></p>
<p><abbr title="HyperText Markup Language" class="initialism">HTML</abbr></p>
```

#### Blockquote

```html
<blockquote class="blockquote">
  <p>A well-known quote, contained in a blockquote element.</p>
</blockquote>
```

#### Naming a source

```html
<figure>
  <blockquote class="blockquote">
    <p>A well-known quote, contained in a blockquote element.</p>
  </blockquote>
  <figcaption class="blockquote-footer">
    Someone famous in <cite title="Source Title">Source Title</cite>
  </figcaption>
</figure>
```

will be:
![](/images/14.PNG)

#### Alignment

Use text utilities as needed to change the alignment of your blockquote.

```html
<figure class="text-center text-end">
  <blockquote class="blockquote">
    <p>A well-known quote, contained in a blockquote element.</p>
  </blockquote>
  <figcaption class="blockquote-footer">
    Someone famous in <cite title="Source Title">Source Title</cite>
  </figcaption>
</figure>
```

will be:
![](/images/15.PNG)
and will be:
![](/images/16.PNG)

### Lists

#### Unstyled

```html
<ul class="list-unstyled">
  <li>This is a list.</li>
  <li>It appears completely unstyled.</li>
  <li>Structurally, it's still a list.</li>
  <li>However, this style only applies to immediate child elements.</li>
  <li>
    Nested lists:
    <ul>
      <li>are unaffected by this style</li>
      <li>will still show a bullet</li>
      <li>and have appropriate left margin</li>
    </ul>
  </li>
  <li>This may still come in handy in some situations.</li>
</ul>
```

will be:
![](/images/17.PNG)

#### Inline list

```html
<ul class="list-inline">
  <li class="list-inline-item">This is a list item.</li>
  <li class="list-inline-item">And another one.</li>
  <li class="list-inline-item">But they're displayed inline.</li>
</ul>
```

will be:
![](/images/18.PNG)

### Images

Documentation and examples for opting images into responsive behavior (so they never become wider than their parent)

#### Responsive images

Images in Bootstrap are made responsive with .img-fluid. This applies max-width: 100%; and height: auto; to the image so that it scales with the parent width.

```html
<img src="..." class="img-fluid" alt="..." />
```

#### Image thumbnails

you can use .img-thumbnail to give an image a rounded 1px border appearance.

```html
<img src="..." class="img-thumbnail" alt="..." />
```

#### Aligning images

Align images with the helper float classes or text alignment classes.

```html
<img src="..." class="rounded float-start" alt="..." />
<img src="..." class="rounded float-end" alt="..." />
```

will be:
![](/images/19.PNG)

### Picture

If you are using the `<picture>` element to specify multiple `<source>` elements for a specific `<img>`, make sure to add the `.img-\*` classes to the `<img>` and not to the `<picture>` tag.

```html
<picture>
  <source srcset="..." type="image/svg+xml" />
  <img src="..." class="img-fluid img-thumbnail" alt="..." />
</picture>
```

### Tables

A simple table:

```html
<table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">First</th>
      <th scope="col">Last</th>
      <th scope="col">Handle</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
```

will be:
![](/images/20.PNG)

#### Colorizing

```html
<!-- On tables or on rows with <tr> or on cells <td> <th>-->
<table class="table-primary">
  ...
</table>
<table class="table-secondary">
  ...
</table>
<table class="table-success">
  ...
</table>
<table class="table-danger">
  ...
</table>
<table class="table-warning">
  ...
</table>
<table class="table-info">
  ...
</table>
<table class="table-light">
  ...
</table>
<table class="table-dark">
  ...
</table>
```

#### zebra-striping

```html
<table class="table table-striped">
  <!--or class="table table-dark table-striped"-->
  <!--or class="class="table table-success table-striped"-->
  ...
</table>
```

#### Hover able Rows

```html
<table class="table table-hover">
  ...
</table>
```

#### Active tables

Highlight a table row or cell by adding a `.table-active` class.

```html
<table class="table">
  <thead>
    ...
  </thead>
  <tbody>
    <tr class="table-active">
      ...
    </tr>
    <tr>
      ...
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2" class="table-active">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
```

will be:
![](/images/21.PNG)

#### Bordered tables

we can colorize them with `border-primary`and ...

```html
<table class="table table-bordered">
  ...
</table>
```

#### Captions

```html
<table class="table table-sm">
  <caption>
    List of users
  </caption>
  <thead>
    ...
  </thead>
  <tbody>
    ...
  </tbody>
</table>
```

will be:
![](/images/22.PNG)

#### Responsive tables

all viewpoint's by wrapping a `.table` with `.table-responsive`. Or, pick a maximum breakpoint with which to have a responsive table up to by using `.table-responsive{-sm|-md|-lg|-xl|-xxl}`.

### Figures

Anytime you need to display a piece of content—like an image with an optional caption, consider using a `<figure>`.

```html
<figure class="figure">
  <img src="..." class="figure-img img-fluid rounded" alt="..." />
  <figcaption class="figure-caption">A caption for the above image.</figcaption>
</figure>
```

## Forms

### Form controls

```html
<div class="mb-3">
  <label for="exampleFormControlInput1" class="form-label">Email address</label>
  <input
    type="email"
    class="form-control"
    id="exampleFormControlInput1"
    placeholder="name@example.com"
  />
</div>
<div class="mb-3">
  <label for="exampleFormControlTextarea1" class="form-label"
    >Example textarea</label
  >
  <textarea
    class="form-control"
    id="exampleFormControlTextarea1"
    rows="3"
  ></textarea>
</div>
```

will be:
![](/images/23.PNG)

#### Sizing

Set heights using classes like `.form-control-lg` and `.form-control-sm`.

```html
<input
  class="form-control form-control-lg"
  type="text"
  placeholder=".form-control-lg"
  aria-label=".form-control-lg example"
/>
<input
  class="form-control"
  type="text"
  placeholder="Default input"
  aria-label="default input example"
/>
<input
  class="form-control form-control-sm"
  type="text"
  placeholder=".form-control-sm"
  aria-label=".form-control-sm example"
/>
```

will be:
![](/images/24.PNG)

#### Disabled

```html
<input
  class="form-control"
  type="text"
  placeholder="Disabled input"
  aria-label="Disabled input example"
  disabled
/>
<input
  class="form-control"
  type="text"
  value="Disabled readonly input"
  aria-label="Disabled input example"
  disabled
  readonly
/>
```

will be:
![](/images/25.PNG)

#### Readonly

```html
<input
  class="form-control"
  type="text"
  value="Readonly input here..."
  aria-label="readonly input example"
  readonly
/>
```

will be:
![](/images/26.PNG)

#### Readonly plain text

If you want to have `<input readonly>` elements in your form styled as plain text, replace `.form-control` with .`form-control-plaintext` to remove the default form field styling and preserve the correct margin and padding.

```html
<div class="mb-3 row">
  <label for="staticEmail" class="col-sm-2 col-form-label">Email</label>
  <div class="col-sm-10">
    <input
      type="text"
      readonly
      class="form-control-plaintext"
      id="staticEmail"
      value="email@example.com"
    />
  </div>
</div>
<div class="mb-3 row">
  <label for="inputPassword" class="col-sm-2 col-form-label">Password</label>
  <div class="col-sm-10">
    <input type="password" class="form-control" id="inputPassword" />
  </div>
</div>
```

will be:
![](/images/27.PNG)

#### File input

```html
<div class="mb-3">
  <label for="formFile" class="form-label">Default file input example</label>
  <input class="form-control" type="file" id="formFile" />
</div>
<div class="mb-3">
  <label for="formFileMultiple" class="form-label"
    >Multiple files input example</label
  >
  <input class="form-control" type="file" id="formFileMultiple" multiple />
</div>
<div class="mb-3">
  <label for="formFileDisabled" class="form-label"
    >Disabled file input example</label
  >
  <input class="form-control" type="file" id="formFileDisabled" disabled />
</div>
<div class="mb-3">
  <label for="formFileSm" class="form-label">Small file input example</label>
  <input class="form-control form-control-sm" id="formFileSm" type="file" />
</div>
<div>
  <label for="formFileLg" class="form-label">Large file input example</label>
  <input class="form-control form-control-lg" id="formFileLg" type="file" />
</div>
```

will be:
![](/images/28.PNG)

#### Color

Set the `type="color"` and add `.form-control-color` to the `<input>`.

```html
<label for="exampleColorInput" class="form-label">Color picker</label>
<input
  type="color"
  class="form-control form-control-color"
  id="exampleColorInput"
  value="#563d7c"
  title="Choose your color"
/>
```

will be:
![](/images/29.PNG)

#### Datalist

Datalist allow you to create a group of `<option>`s that can be accessed (and autocompleted) from within an `<input>`.

```html
<label for="exampleDataList" class="form-label">Datalist example</label>
<input
  class="form-control"
  list="datalistOptions"
  id="exampleDataList"
  placeholder="Type to search..."
/>
<datalist id="datalistOptions">
  <option value="San Francisco"></option>
  <option value="New York"></option>
  <option value="Seattle"></option>
  <option value="Los Angeles"></option>
  <option value="Chicago"></option>
</datalist>
```

will be:
![](/images/30.PNG)

### Select

```html
<select class="form-select" aria-label="Default select example">
  <option selected>Open this select menu</option>
  <option value="1">One</option>
  <option value="2">Two</option>
  <option value="3">Three</option>
</select>
```

will be:
![](/images/31.PNG)

we can do Sizing with: `form-select-lg` and `form-select-sm` as classes.
The multiple attribute is also supported:

```html
<select class="form-select" multiple aria-label="multiple select example">
  <option selected>Open this select menu</option>
  <option value="1">One</option>
  <option value="2">Two</option>
  <option value="3">Three</option>
</select>
```

will be:
![](/images/32.PNG)

as we can do Disabled with: `<select class="form-select" aria-label="Disabled select example" disabled>`

### Checks and radios

Checks

```html
<div class="form-check">
  <input
    class="form-check-input"
    type="checkbox"
    value=""
    id="flexCheckDefault"
  />
  <label class="form-check-label" for="flexCheckDefault">
    Default checkbox
  </label>
</div>
<div class="form-check">
  <input
    class="form-check-input"
    type="checkbox"
    value=""
    id="flexCheckChecked"
    checked
  />
  <label class="form-check-label" for="flexCheckChecked">
    Checked checkbox
  </label>
</div>
```

will be:
![](/images/33.PNG)

#### Indeterminate

Checkboxes can utilize the `:indeterminate` pseudo class when manually

```html
<div class="form-check">
  <input
    class="form-check-input"
    type="checkbox"
    value=""
    id="flexCheckIndeterminate"
  />
  <label class="form-check-label" for="flexCheckIndeterminate">
    Indeterminate checkbox
  </label>
</div>
```

will be:
![](/images/34.PNG)

we can use Disabled too: `<input class="form-check-input" type="checkbox" value="" id="flexCheckDisabled" disabled>`

#### Radios

```html
<div class="form-check">
  <input
    class="form-check-input"
    type="radio"
    name="flexRadioDefault"
    id="flexRadioDefault1"
  />
  <label class="form-check-label" for="flexRadioDefault1">
    Default radio
  </label>
</div>
<div class="form-check">
  <input
    class="form-check-input"
    type="radio"
    name="flexRadioDefault"
    id="flexRadioDefault2"
    checked
  />
  <label class="form-check-label" for="flexRadioDefault2">
    Default checked radio
  </label>
</div>
```

will be:
![](/images/35.PNG)

and the disabled version: `<input class="form-check-input" type="radio" name="flexRadioDisabled" id="flexRadioDisabled" disabled>`

#### Switches

```html
<div class="form-check form-switch">
  <input
    class="form-check-input"
    type="checkbox"
    role="switch"
    id="flexSwitchCheckDefault"
  />
  <label class="form-check-label" for="flexSwitchCheckDefault"
    >Default switch checkbox input</label
  >
</div>
<div class="form-check form-switch">
  <input
    class="form-check-input"
    type="checkbox"
    role="switch"
    id="flexSwitchCheckChecked"
    checked
  />
  <label class="form-check-label" for="flexSwitchCheckChecked"
    >Checked switch checkbox input</label
  >
</div>
<div class="form-check form-switch">
  <input
    class="form-check-input"
    type="checkbox"
    role="switch"
    id="flexSwitchCheckDisabled"
    disabled
  />
  <label class="form-check-label" for="flexSwitchCheckDisabled"
    >Disabled switch checkbox input</label
  >
</div>
<div class="form-check form-switch">
  <input
    class="form-check-input"
    type="checkbox"
    role="switch"
    id="flexSwitchCheckCheckedDisabled"
    checked
    disabled
  />
  <label class="form-check-label" for="flexSwitchCheckCheckedDisabled"
    >Disabled checked switch checkbox input</label
  >
</div>
```

will be:
![](/images/36.PNG)

#### Inline

Group checkboxes or radios on the same horizontal row by adding `.form-check-inline` to any `.form-check`.

```html
<div class="form-check form-check-inline">
  <input
    class="form-check-input"
    type="checkbox"
    id="inlineCheckbox1"
    value="option1"
  />
  <label class="form-check-label" for="inlineCheckbox1">1</label>
</div>
<div class="form-check form-check-inline">
  <input
    class="form-check-input"
    type="checkbox"
    id="inlineCheckbox2"
    value="option2"
  />
  <label class="form-check-label" for="inlineCheckbox2">2</label>
</div>
<div class="form-check form-check-inline">
  <input
    class="form-check-input"
    type="checkbox"
    id="inlineCheckbox3"
    value="option3"
    disabled
  />
  <label class="form-check-label" for="inlineCheckbox3">3 (disabled)</label>
</div>
```

will be:
![](/images/37.PNG)

#### Reverse

Put your checkboxes, radios, and switches on the opposite side with the .form-check-reverse modifier class.

```html
<div class="form-check form-check-reverse">
  <input class="form-check-input" type="checkbox" value="" id="reverseCheck1" />
  <label class="form-check-label" for="reverseCheck1"> Reverse checkbox </label>
</div>
<div class="form-check form-check-reverse">
  <input
    class="form-check-input"
    type="checkbox"
    value=""
    id="reverseCheck2"
    disabled
  />
  <label class="form-check-label" for="reverseCheck2">
    Disabled reverse checkbox
  </label>
</div>

<div class="form-check form-switch form-check-reverse">
  <input class="form-check-input" type="checkbox" id="flexSwitchCheckReverse" />
  <label class="form-check-label" for="flexSwitchCheckReverse"
    >Reverse switch checkbox input</label
  >
</div>
```

will be:
![](/images/38.PNG)

#### Checkbox toggle buttons

```html
<input type="checkbox" class="btn-check" id="btn-check" autocomplete="off" />
<label class="btn btn-primary" for="btn-check">Single toggle</label>
```

will be:
![](/images/39.PNG)

### Range

Create custom `<input type="range">` controls with .form-range.

```html
<label for="customRange1" class="form-label">Example range</label>
<input type="range" class="form-range" id="customRange1" />
```

will be:
![](/images/40.PNG)

we can use disabled too: `<input type="range" class="form-range" id="disabledRange" disabled>`

#### Min and max

```html
<label for="customRange2" class="form-label">Example range</label>
<input type="range" class="form-range" min="0" max="5" id="customRange2" />
```

will be:
![](/images/41.PNG)

we can use steps too: `<input type="range" class="form-range" min="0" max="5" step="0.5" id="customRange3">`

### Input group

```html
<div class="input-group mb-3">
  <span class="input-group-text" id="basic-addon1">@</span>
  <input
    type="text"
    class="form-control"
    placeholder="Username"
    aria-label="Username"
    aria-describedby="basic-addon1"
  />
</div>

<div class="input-group mb-3">
  <input
    type="text"
    class="form-control"
    placeholder="Recipient's username"
    aria-label="Recipient's username"
    aria-describedby="basic-addon2"
  />
  <span class="input-group-text" id="basic-addon2">@example.com</span>
</div>

<label for="basic-url" class="form-label">Your vanity URL</label>
<div class="input-group mb-3">
  <span class="input-group-text" id="basic-addon3"
    >https://example.com/users/</span
  >
  <input
    type="text"
    class="form-control"
    id="basic-url"
    aria-describedby="basic-addon3"
  />
</div>

<div class="input-group mb-3">
  <span class="input-group-text">$</span>
  <input
    type="text"
    class="form-control"
    aria-label="Amount (to the nearest dollar)"
  />
  <span class="input-group-text">.00</span>
</div>

<div class="input-group mb-3">
  <input
    type="text"
    class="form-control"
    placeholder="Username"
    aria-label="Username"
  />
  <span class="input-group-text">@</span>
  <input
    type="text"
    class="form-control"
    placeholder="Server"
    aria-label="Server"
  />
</div>

<div class="input-group">
  <span class="input-group-text">With textarea</span>
  <textarea class="form-control" aria-label="With textarea"></textarea>
</div>
```

will be:
![](/images/42.PNG)

we can size them too with:
` div class="input-group input-group-sm mb-3">` and `<div class="input-group input-group-lg">`

#### Checkboxes and radios

```html
<div class="input-group mb-3">
  <div class="input-group-text">
    <input
      class="form-check-input mt-0"
      type="checkbox"
      value=""
      aria-label="Checkbox for following text input"
    />
  </div>
  <input
    type="text"
    class="form-control"
    aria-label="Text input with checkbox"
  />
</div>

<div class="input-group">
  <div class="input-group-text">
    <input
      class="form-check-input mt-0"
      type="radio"
      value=""
      aria-label="Radio button for following text input"
    />
  </div>
  <input
    type="text"
    class="form-control"
    aria-label="Text input with radio button"
  />
</div>
```

will be:
![](/images/43.PNG)

#### Multiple inputs

```html
<div class="input-group">
  <span class="input-group-text">First and last name</span>
  <input type="text" aria-label="First name" class="form-control" />
  <input type="text" aria-label="Last name" class="form-control" />
</div>
```

will be:
![](/images/44.PNG)

#### Multiple addons

```html
<div class="input-group mb-3">
  <span class="input-group-text">$</span>
  <span class="input-group-text">0.00</span>
  <input
    type="text"
    class="form-control"
    aria-label="Dollar amount (with dot and two decimal places)"
  />
</div>

<div class="input-group">
  <input
    type="text"
    class="form-control"
    aria-label="Dollar amount (with dot and two decimal places)"
  />
  <span class="input-group-text">$</span>
  <span class="input-group-text">0.00</span>
</div>
```

will be:
![](/images/45.PNG)

and lot more like:

buttons

```html
<div class="input-group mb-3">
  <button class="btn btn-outline-secondary" type="button" id="button-addon1">
    Button
  </button>
  <input
    type="text"
    class="form-control"
    placeholder=""
    aria-label="Example text with button addon"
    aria-describedby="button-addon1"
  />
</div>
```

dropdown buttons:

```html
<div class="input-group mb-3">
  <button
    class="btn btn-outline-secondary dropdown-toggle"
    type="button"
    data-bs-toggle="dropdown"
    aria-expanded="false"
  >
    Dropdown
  </button>
  <ul class="dropdown-menu">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another action</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
    <li><hr class="dropdown-divider" /></li>
    <li><a class="dropdown-item" href="#">Separated link</a></li>
  </ul>
  <input
    type="text"
    class="form-control"
    aria-label="Text input with dropdown button"
  />
</div>
```

Segmented buttons:

```html
<div class="input-group mb-3">
  <button type="button" class="btn btn-outline-secondary">Action</button>
  <button
    type="button"
    class="btn btn-outline-secondary dropdown-toggle dropdown-toggle-split"
    data-bs-toggle="dropdown"
    aria-expanded="false"
  >
    <span class="visually-hidden">Toggle Dropdown</span>
  </button>
  <ul class="dropdown-menu">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another action</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
    <li><hr class="dropdown-divider" /></li>
    <li><a class="dropdown-item" href="#">Separated link</a></li>
  </ul>
  <input
    type="text"
    class="form-control"
    aria-label="Text input with segmented dropdown button"
  />
</div>
```

### Floating labels

```html
<div class="form-floating mb-3">
  <input
    type="email"
    class="form-control"
    id="floatingInput"
    placeholder="name@example.com"
  />
  <label for="floatingInput">Email address</label>
</div>
<div class="form-floating">
  <input
    type="password"
    class="form-control"
    id="floatingPassword"
    placeholder="Password"
  />
  <label for="floatingPassword">Password</label>
</div>
```

before click:
![](/images/46.PNG)
after click:
![](/images/47.PNG)

we can also use validation:

```html
<input
  type="email"
  class="form-control is-invalid"
  id="floatingInputInvalid"
  placeholder="name@example.com"
  value="test@example.com"
/>
```

### validation

```html
<form class="row g-3 needs-validation" novalidate>
  <div class="col-md-4">
    <label for="validationCustom01" class="form-label">First name</label>
    <input
      type="text"
      class="form-control"
      id="validationCustom01"
      value="Mark"
      required
    />
    <div class="valid-feedback">Looks good!</div>
  </div>
  <div class="col-md-4">
    <label for="validationCustom02" class="form-label">Last name</label>
    <input
      type="text"
      class="form-control"
      id="validationCustom02"
      value="Otto"
      required
    />
    <div class="valid-feedback">Looks good!</div>
  </div>
  <div class="col-md-4">
    <label for="validationCustomUsername" class="form-label">Username</label>
    <div class="input-group has-validation">
      <span class="input-group-text" id="inputGroupPrepend">@</span>
      <input
        type="text"
        class="form-control"
        id="validationCustomUsername"
        aria-describedby="inputGroupPrepend"
        required
      />
      <div class="invalid-feedback">Please choose a username.</div>
    </div>
  </div>
  <div class="col-md-6">
    <label for="validationCustom03" class="form-label">City</label>
    <input type="text" class="form-control" id="validationCustom03" required />
    <div class="invalid-feedback">Please provide a valid city.</div>
  </div>
  <div class="col-md-3">
    <label for="validationCustom04" class="form-label">State</label>
    <select class="form-select" id="validationCustom04" required>
      <option selected disabled value="">Choose...</option>
      <option>...</option>
    </select>
    <div class="invalid-feedback">Please select a valid state.</div>
  </div>
  <div class="col-md-3">
    <label for="validationCustom05" class="form-label">Zip</label>
    <input type="text" class="form-control" id="validationCustom05" required />
    <div class="invalid-feedback">Please provide a valid zip.</div>
  </div>
  <div class="col-12">
    <div class="form-check">
      <input
        class="form-check-input"
        type="checkbox"
        value=""
        id="invalidCheck"
        required
      />
      <label class="form-check-label" for="invalidCheck">
        Agree to terms and conditions
      </label>
      <div class="invalid-feedback">You must agree before submitting.</div>
    </div>
  </div>
  <div class="col-12">
    <button class="btn btn-primary" type="submit">Submit form</button>
  </div>
</form>
```

with this JavaScript:

```JavaScript
// Example starter JavaScript for disabling form submissions if there are invalid fields
(() => {
  'use strict'

  // Fetch all the forms we want to apply custom Bootstrap validation styles to
  const forms = document.querySelectorAll('.needs-validation')

  // Loop over them and prevent submission
  Array.from(forms).forEach(form => {
    form.addEventListener('submit', event => {
      if (!form.checkValidity()) {
        event.preventDefault()
        event.stopPropagation()
      }

      form.classList.add('was-validated')
    }, false)
  })
})()
```

![](/images/48.PNG)

#### Tooltips

```html
<form class="row g-3 needs-validation" novalidate>
  <div class="col-md-4 position-relative">
    <label for="validationTooltip01" class="form-label">First name</label>
    <input
      type="text"
      class="form-control"
      id="validationTooltip01"
      value="Mark"
      required
    />
    <div class="valid-tooltip">Looks good!</div>
  </div>
  <div class="col-md-4 position-relative">
    <label for="validationTooltip02" class="form-label">Last name</label>
    <input
      type="text"
      class="form-control"
      id="validationTooltip02"
      value="Otto"
      required
    />
    <div class="valid-tooltip">Looks good!</div>
  </div>
  <div class="col-md-4 position-relative">
    <label for="validationTooltipUsername" class="form-label">Username</label>
    <div class="input-group has-validation">
      <span class="input-group-text" id="validationTooltipUsernamePrepend"
        >@</span
      >
      <input
        type="text"
        class="form-control"
        id="validationTooltipUsername"
        aria-describedby="validationTooltipUsernamePrepend"
        required
      />
      <div class="invalid-tooltip">
        Please choose a unique and valid username.
      </div>
    </div>
  </div>
  <div class="col-md-6 position-relative">
    <label for="validationTooltip03" class="form-label">City</label>
    <input type="text" class="form-control" id="validationTooltip03" required />
    <div class="invalid-tooltip">Please provide a valid city.</div>
  </div>
  <div class="col-md-3 position-relative">
    <label for="validationTooltip04" class="form-label">State</label>
    <select class="form-select" id="validationTooltip04" required>
      <option selected disabled value="">Choose...</option>
      <option>...</option>
    </select>
    <div class="invalid-tooltip">Please select a valid state.</div>
  </div>
  <div class="col-md-3 position-relative">
    <label for="validationTooltip05" class="form-label">Zip</label>
    <input type="text" class="form-control" id="validationTooltip05" required />
    <div class="invalid-tooltip">Please provide a valid zip.</div>
  </div>
  <div class="col-12">
    <button class="btn btn-primary" type="submit">Submit form</button>
  </div>
</form>
```

will be:

![](/images/49.PNG)

---

## Components

### Accordion

```html
<div class="accordion" id="accordionExample">
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingOne">
      <button
        class="accordion-button"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#collapseOne"
        aria-expanded="true"
        aria-controls="collapseOne"
      >
        Accordion Item #1
      </button>
    </h2>
    <div
      id="collapseOne"
      class="accordion-collapse collapse show"
      aria-labelledby="headingOne"
      data-bs-parent="#accordionExample"
    >
      <div class="accordion-body">
        <strong>This is the first item's accordion body.</strong> It is shown by
        default, until the collapse plugin adds the appropriate classes that we
        use to style each element. These classes control the overall appearance,
        as well as the showing and hiding via CSS transitions. You can modify
        any of this with custom CSS or overriding our default variables. It's
        also worth noting that just about any HTML can go within the
        <code>.accordion-body</code>, though the transition does limit overflow.
      </div>
    </div>
  </div>
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingTwo">
      <button
        class="accordion-button collapsed"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#collapseTwo"
        aria-expanded="false"
        aria-controls="collapseTwo"
      >
        Accordion Item #2
      </button>
    </h2>
    <div
      id="collapseTwo"
      class="accordion-collapse collapse"
      aria-labelledby="headingTwo"
      data-bs-parent="#accordionExample"
    >
      <div class="accordion-body">
        <strong>This is the second item's accordion body.</strong> It is hidden
        by default, until the collapse plugin adds the appropriate classes that
        we use to style each element. These classes control the overall
        appearance, as well as the showing and hiding via CSS transitions. You
        can modify any of this with custom CSS or overriding our default
        variables. It's also worth noting that just about any HTML can go within
        the <code>.accordion-body</code>, though the transition does limit
        overflow.
      </div>
    </div>
  </div>
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingThree">
      <button
        class="accordion-button collapsed"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#collapseThree"
        aria-expanded="false"
        aria-controls="collapseThree"
      >
        Accordion Item #3
      </button>
    </h2>
    <div
      id="collapseThree"
      class="accordion-collapse collapse"
      aria-labelledby="headingThree"
      data-bs-parent="#accordionExample"
    >
      <div class="accordion-body">
        <strong>This is the third item's accordion body.</strong> It is hidden
        by default, until the collapse plugin adds the appropriate classes that
        we use to style each element. These classes control the overall
        appearance, as well as the showing and hiding via CSS transitions. You
        can modify any of this with custom CSS or overriding our default
        variables. It's also worth noting that just about any HTML can go within
        the <code>.accordion-body</code>, though the transition does limit
        overflow.
      </div>
    </div>
  </div>
</div>
```

will be:
![](/images/50.PNG)

Add `.accordion-flush` to remove the default `background-color`. Omit the `data-bs-parent` attribute on each `.accordion-collapse` to make accordion items stay open when another item is opened.

### Alerts

```html
<div class="alert alert-primary" role="alert">
  A simple primary alert—check it out!
</div>
<div class="alert alert-secondary" role="alert">
  A simple secondary alert—check it out!
</div>
<div class="alert alert-success" role="alert">
  A simple success alert—check it out!
</div>
<div class="alert alert-danger" role="alert">
  A simple danger alert—check it out!
</div>
<div class="alert alert-warning" role="alert">
  A simple warning alert—check it out!
</div>
<div class="alert alert-info" role="alert">
  A simple info alert—check it out!
</div>
<div class="alert alert-light" role="alert">
  A simple light alert—check it out!
</div>
<div class="alert alert-dark" role="alert">
  A simple dark alert—check it out!
</div>
```

will be:
![](/images/51.PNG)

Use the .alert-link utility class to quickly provide matching colored links within any alert.]

#### Additional content

```html
<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">Well done!</h4>
  <p>
    Aww yeah, you successfully read this important alert message. This example
    text is going to run a bit longer so that you can see how spacing within an
    alert works with this kind of content.
  </p>
  <hr />
  <p class="mb-0">
    Whenever you need to, be sure to use margin utilities to keep things nice
    and tidy.
  </p>
</div>
```

will be:
![](/images/52.PNG)

```html
<svg xmlns="http://www.w3.org/2000/svg" style="display: none;">
  <symbol id="check-circle-fill" viewBox="0 0 16 16">
    <path
      d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zm-3.97-3.03a.75.75 0 0 0-1.08.022L7.477 9.417 5.384 7.323a.75.75 0 0 0-1.06 1.06L6.97 11.03a.75.75 0 0 0 1.079-.02l3.992-4.99a.75.75 0 0 0-.01-1.05z"
    />
  </symbol>
  <symbol id="info-fill" viewBox="0 0 16 16">
    <path
      d="M8 16A8 8 0 1 0 8 0a8 8 0 0 0 0 16zm.93-9.412-1 4.705c-.07.34.029.533.304.533.194 0 .487-.07.686-.246l-.088.416c-.287.346-.92.598-1.465.598-.703 0-1.002-.422-.808-1.319l.738-3.468c.064-.293.006-.399-.287-.47l-.451-.081.082-.381 2.29-.287zM8 5.5a1 1 0 1 1 0-2 1 1 0 0 1 0 2z"
    />
  </symbol>
  <symbol id="exclamation-triangle-fill" viewBox="0 0 16 16">
    <path
      d="M8.982 1.566a1.13 1.13 0 0 0-1.96 0L.165 13.233c-.457.778.091 1.767.98 1.767h13.713c.889 0 1.438-.99.98-1.767L8.982 1.566zM8 5c.535 0 .954.462.9.995l-.35 3.507a.552.552 0 0 1-1.1 0L7.1 5.995A.905.905 0 0 1 8 5zm.002 6a1 1 0 1 1 0 2 1 1 0 0 1 0-2z"
    />
  </symbol>
</svg>

<div class="alert alert-primary d-flex align-items-center" role="alert">
  <svg class="bi flex-shrink-0 me-2" role="img" aria-label="Info:">
    <use xlink:href="#info-fill" />
  </svg>
  <div>An example alert with an icon</div>
</div>
<div class="alert alert-success d-flex align-items-center" role="alert">
  <svg class="bi flex-shrink-0 me-2" role="img" aria-label="Success:">
    <use xlink:href="#check-circle-fill" />
  </svg>
  <div>An example success alert with an icon</div>
</div>
<div class="alert alert-warning d-flex align-items-center" role="alert">
  <svg class="bi flex-shrink-0 me-2" role="img" aria-label="Warning:">
    <use xlink:href="#exclamation-triangle-fill" />
  </svg>
  <div>An example warning alert with an icon</div>
</div>
<div class="alert alert-danger d-flex align-items-center" role="alert">
  <svg class="bi flex-shrink-0 me-2" role="img" aria-label="Danger:">
    <use xlink:href="#exclamation-triangle-fill" />
  </svg>
  <div>An example danger alert with an icon</div>
</div>
```

will be:
![](/images/53.PNG)

### Badges

```html
<h1>Example heading <span class="badge bg-secondary">New</span></h1>
```

will be:
![](/images/54.PNG)

Badges can be used as part of links or buttons to provide a counter.

```html
<button type="button" class="btn btn-primary">
  Notifications <span class="badge text-bg-secondary">4</span>
</button>
```

will be:
![](/images/55.PNG)

Use utilities to modify a .badge and position it in the corner of a link or button.

```html
<button type="button" class="btn btn-primary position-relative">
  Inbox
  <span
    class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger"
  >
    99+
    <span class="visually-hidden">unread messages</span>
  </span>
</button>
```

will be:
![](/images/56.PNG)

or

```html
<button type="button" class="btn btn-primary position-relative">
  Profile
  <span
    class="position-absolute top-0 start-100 translate-middle p-2 bg-danger border border-light rounded-circle"
  >
    <span class="visually-hidden">New alerts</span>
  </span>
</button>
```

will be:
![](/images/57.PNG)

Set a `background-color` with contrasting foreground color with our `.text-bg-{color}` helpers.

```html
<span class="badge text-bg-primary">Primary</span>
<span class="badge text-bg-secondary">Secondary</span>
<span class="badge text-bg-success">Success</span>
<span class="badge text-bg-danger">Danger</span>
<span class="badge text-bg-warning">Warning</span>
<span class="badge text-bg-info">Info</span>
<span class="badge text-bg-light">Light</span>
<span class="badge text-bg-dark">Dark</span>
```

will be:
![](/images/58.PNG)

Use the `.rounded-pill` utility class to make badges more rounded with a larger `border-radius`.

### Breadcrumb

Indicate the current page’s location within a navigational hierarchy that automatically adds separators via CSS.

Example

```html
<nav aria-label="breadcrumb">
  <ol class="breadcrumb">
    <li class="breadcrumb-item active" aria-current="page">Home</li>
  </ol>
</nav>

<nav aria-label="breadcrumb">
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="#">Home</a></li>
    <li class="breadcrumb-item active" aria-current="page">Library</li>
  </ol>
</nav>

<nav aria-label="breadcrumb">
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="#">Home</a></li>
    <li class="breadcrumb-item"><a href="#">Library</a></li>
    <li class="breadcrumb-item active" aria-current="page">Data</li>
  </ol>
</nav>
```

will be:
![](/images/59.PNG)

#### Dividers

They can be changed by modifying a local CSS custom property `--bs-breadcrumb-divider`, or through the `$breadcrumb-divider` Sass variable — and `$breadcrumb-divider-flipped` for its RTL counterpart, if needed.

```html
<nav style="--bs-breadcrumb-divider: '>';" aria-label="breadcrumb">
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="#">Home</a></li>
    <li class="breadcrumb-item active" aria-current="page">Library</li>
  </ol>
</nav>
```

will be:
![](/images/60.PNG)

#### Using embedded SVG

```html
<nav
  style="--bs-breadcrumb-divider: url(&#34;data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='8' height='8'%3E%3Cpath d='M2.5 0L1 1.5 3.5 4 1 6.5 2.5 8l4-4-4-4z' fill='%236c757d'/%3E%3C/svg%3E&#34;);"
  aria-label="breadcrumb"
>
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="#">Home</a></li>
    <li class="breadcrumb-item active" aria-current="page">Library</li>
  </ol>
</nav>
```

You can also remove the divider setting `--bs-breadcrumb-divider: '';`

### Buttons

```html
<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-secondary">Secondary</button>
<button type="button" class="btn btn-success">Success</button>
<button type="button" class="btn btn-danger">Danger</button>
<button type="button" class="btn btn-warning">Warning</button>
<button type="button" class="btn btn-info">Info</button>
<button type="button" class="btn btn-light">Light</button>
<button type="button" class="btn btn-dark">Dark</button>

<button type="button" class="btn btn-link">Link</button>
```

will be:
![](/images/61.PNG)

#### Outline buttons

```html
<button type="button" class="btn btn-outline-primary">Primary</button>
<button type="button" class="btn btn-outline-secondary">Secondary</button>
<button type="button" class="btn btn-outline-success">Success</button>
<button type="button" class="btn btn-outline-danger">Danger</button>
<button type="button" class="btn btn-outline-warning">Warning</button>
<button type="button" class="btn btn-outline-info">Info</button>
<button type="button" class="btn btn-outline-light">Light</button>
<button type="button" class="btn btn-outline-dark">Dark</button>
```

will be:
![](/images/62.PNG)

Add `.btn-lg` or `.btn-sm` for additional sizes.
You can even roll your own custom sizing with CSS variables:

```html
<button
  type="button"
  class="btn btn-primary"
  style="--bs-btn-padding-y: .25rem; --bs-btn-padding-x: .5rem; --bs-btn-font-size: .75rem;"
>
  Custom button
</button>
```

Make buttons look inactive by adding the `disabled` boolean attribute to any `<button>` element.
`<button type="button" class="btn btn-primary" disabled>Primary button</button>`

#### Block buttons

```html
<div class="d-grid gap-2">
  <button class="btn btn-primary" type="button">Button</button>
  <button class="btn btn-primary" type="button">Button</button>
</div>
```

will be:
![](/images/63.PNG)

#### Toggle states

Add `data-bs-toggle="button"` to toggle a button’s `active` state. If you’re pre-toggling a button, you must manually add the `.active` class and `aria-pressed="true"` to ensure that it is conveyed appropriately to assistive technologies.

### Button group

```html
<div class="btn-group" role="group" aria-label="Basic example">
  <button type="button" class="btn btn-primary">Left</button>
  <button type="button" class="btn btn-primary">Middle</button>
  <button type="button" class="btn btn-primary">Right</button>
</div>
```

will be:
![](/images/64.PNG)

to make a button active simply add `.active` to it.

#### Checkbox and radio button groups

```html
<div
  class="btn-group"
  role="group"
  aria-label="Basic checkbox toggle button group"
>
  <input type="checkbox" class="btn-check" id="btncheck1" autocomplete="off" />
  <label class="btn btn-outline-primary" for="btncheck1">Checkbox 1</label>

  <input type="checkbox" class="btn-check" id="btncheck2" autocomplete="off" />
  <label class="btn btn-outline-primary" for="btncheck2">Checkbox 2</label>

  <input type="checkbox" class="btn-check" id="btncheck3" autocomplete="off" />
  <label class="btn btn-outline-primary" for="btncheck3">Checkbox 3</label>
</div>
```

will be:
![](/bootStrap5.2/images/65.PNG)

### Cards

```html
<div class="card" style="width: 18rem;">
  <img src="..." class="card-img-top" alt="..." />
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">
      Some quick example text to build on the card title and make up the bulk of
      the card's content.
    </p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

will be:
![](/bootStrap5.2/images/66.PNG)

#### Content types

##### Body

Cards support a wide variety of content, including images, text, list groups, links, and more. Below are examples of what’s supported.

```html
<div class="card">
  <div class="card-body">This is some text within a card body.</div>
</div>
```

will be:
![](/bootStrap5.2/images/67.PNG)

##### Images

```html
<div class="card" style="width: 18rem;">
  <img src="..." class="card-img-top" alt="..." />
  <div class="card-body">
    <p class="card-text">
      Some quick example text to build on the card title and make up the bulk of
      the card's content.
    </p>
  </div>
</div>
```

will be:
![](/bootStrap5.2/images/68.PNG)

##### List groups

```html
<div class="card" style="width: 18rem;">
  <ul class="list-group list-group-flush">
    <li class="list-group-item">An item</li>
    <li class="list-group-item">A second item</li>
    <li class="list-group-item">A third item</li>
  </ul>
</div>
```

will be:
![](/bootStrap5.2/images/69.PNG)

u can add cart header and footer with `.card-header` and `.card-footer`

##### Quote

```html
<div class="card">
  <div class="card-header">Quote</div>
  <div class="card-body">
    <blockquote class="blockquote mb-0">
      <p>A well-known quote, contained in a blockquote element.</p>
      <footer class="blockquote-footer">
        Someone famous in <cite title="Source Title">Source Title</cite>
      </footer>
    </blockquote>
  </div>
</div>
```

will be:
![](/bootStrap5.2/images/70.PNG)

##### Navigation

```html
<div class="card text-center">
  <div class="card-header">
    <ul class="nav nav-tabs card-header-tabs">
      <li class="nav-item">
        <a class="nav-link active" aria-current="true" href="#">Active</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled">Disabled</a>
      </li>
    </ul>
  </div>
  <div class="card-body">
    <h5 class="card-title">Special title treatment</h5>
    <p class="card-text">
      With supporting text below as a natural lead-in to additional content.
    </p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

will be:
![](/bootStrap5.2/images/71.PNG)

#### Images

##### Image caps

```html
<div class="card mb-3">
  <img src="..." class="card-img-top" alt="..." />
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">
      This is a wider card with supporting text below as a natural lead-in to
      additional content. This content is a little bit longer.
    </p>
    <p class="card-text">
      <small class="text-muted">Last updated 3 mins ago</small>
    </p>
  </div>
</div>
<div class="card">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">
      This is a wider card with supporting text below as a natural lead-in to
      additional content. This content is a little bit longer.
    </p>
    <p class="card-text">
      <small class="text-muted">Last updated 3 mins ago</small>
    </p>
  </div>
  <img src="..." class="card-img-bottom" alt="..." />
</div>
```

will be:
![](/bootStrap5.2/images/72.PNG)

##### Image overlays

```html
<div class="card text-bg-dark">
  <img src="..." class="card-img" alt="..." />
  <div class="card-img-overlay">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">
      This is a wider card with supporting text below as a natural lead-in to
      additional content. This content is a little bit longer.
    </p>
    <p class="card-text">Last updated 3 mins ago</p>
  </div>
</div>
```

will be:
![](/bootStrap5.2/images/73.PNG)

##### Horizontal

remove the grid gutters with .g-0 and use .col-md-\* classes to make the card horizontal at the md breakpoint.

```html
<div class="card mb-3" style="max-width: 540px;">
  <div class="row g-0">
    <div class="col-md-4">
      <img src="..." class="img-fluid rounded-start" alt="..." />
    </div>
    <div class="col-md-8">
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">
          This is a wider card with supporting text below as a natural lead-in
          to additional content. This content is a little bit longer.
        </p>
        <p class="card-text">
          <small class="text-muted">Last updated 3 mins ago</small>
        </p>
      </div>
    </div>
  </div>
</div>
```

will be:
![](/bootStrap5.2/images/74.PNG)

we can also use Background and color with `.text-bg-{color} helpers` and add border color with ` border-color` and .text-{color} plus `.bg-transparent`.

#### Card groups

```html
<div class="card-group">
  <div class="card">
    <img src="..." class="card-img-top" alt="..." />
    <div class="card-body">
      <h5 class="card-title">Card title</h5>
      <p class="card-text">
        This is a wider card with supporting text below as a natural lead-in to
        additional content. This content is a little bit longer.
      </p>
      <p class="card-text">
        <small class="text-muted">Last updated 3 mins ago</small>
      </p>
    </div>
  </div>
  <div class="card">
    <img src="..." class="card-img-top" alt="..." />
    <div class="card-body">
      <h5 class="card-title">Card title</h5>
      <p class="card-text">
        This card has supporting text below as a natural lead-in to additional
        content.
      </p>
      <p class="card-text">
        <small class="text-muted">Last updated 3 mins ago</small>
      </p>
    </div>
  </div>
  <div class="card">
    <img src="..." class="card-img-top" alt="..." />
    <div class="card-body">
      <h5 class="card-title">Card title</h5>
      <p class="card-text">
        This is a wider card with supporting text below as a natural lead-in to
        additional content. This card has even longer content than the first to
        show that equal height action.
      </p>
      <p class="card-text">
        <small class="text-muted">Last updated 3 mins ago</small>
      </p>
    </div>
  </div>
</div>
```

will be:
![](/bootStrap5.2/images/75.PNG)

#### Grid cards

here’s .row-cols-1 laying out the cards on one column, and .row-cols-md-2 splitting four cards to equal width across multiple rows, from the medium breakpoint up.

```html
<div class="row row-cols-1 row-cols-md-2 g-4">
  <div class="col">
    <div class="card">
      <img src="..." class="card-img-top" alt="..." />
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">
          This is a longer card with supporting text below as a natural lead-in
          to additional content. This content is a little bit longer.
        </p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card">
      <img src="..." class="card-img-top" alt="..." />
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">
          This is a longer card with supporting text below as a natural lead-in
          to additional content. This content is a little bit longer.
        </p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card">
      <img src="..." class="card-img-top" alt="..." />
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">
          This is a longer card with supporting text below as a natural lead-in
          to additional content.
        </p>
      </div>
    </div>
  </div>
  <div class="col">
    <div class="card">
      <img src="..." class="card-img-top" alt="..." />
      <div class="card-body">
        <h5 class="card-title">Card title</h5>
        <p class="card-text">
          This is a longer card with supporting text below as a natural lead-in
          to additional content. This content is a little bit longer.
        </p>
      </div>
    </div>
  </div>
</div>
```

will be:
![](/bootStrap5.2/images/76.PNG)

When you need equal height, add `.h-100` to the cards. If you want equal heights by default, you can set `$card-height: 100%` in Sass.

### Carousel

The `.active` class needs to be added to one of the slides otherwise the carousel will not be visible.Note the presence of the `.d-block` and `.w-100` on carousel images to prevent browser default image alignment. Adding in the previous and next controls. We recommend using `<button>` elements, but you can also use `<a>` elements with `role="button"`.With indicators `<div class="carousel-indicators">`. Add captions to your slides easily with the `.carousel-caption` element within any `.carousel-item`. Add `.carousel-fade` to your carousel to animate slides with a fade transition instead of a slide. Add `data-bs-interval=""` to a `.carousel-item` to change the amount of time to delay between automatically cycling to the next item. Carousels support swiping left/right on touchscreen devices to move between slides. This can be disabled using the `data-bs-touch` attribute. Add `.carousel-dark` to the `.carousel` for darker controls, indicators, and captions.

### Close button

Provide an option to dismiss or close a component with `.btn-close`. or mke it disabled with `<button type="button" class="btn-close" disabled aria-label="Close"></button>`. Change the default `.btn-close` to be white with the `.btn-close-white` class.

### Collapse

Click the buttons below to show and hide another element via class changes:

- `.collapse` hides content
- `.collapsing` is applied during transitions
- `.collapse.show` shows content

Generally, we recommend using a button with the `data-bs-target` attribute. the `data-bs-toggle="collapse"` is required. A `<button>` or `<a>` can show and hide multiple elements by referencing them with a selector in its `href` or `data-bs-target` attribute.
`<button class="btn btn-primary" type="button" data-bs-toggle="collapse" data-bs-target=".multi-collapse" aria-expanded="false" aria-controls="multiCollapseExample1 multiCollapseExample2">Toggle both elements</button> <div class="collapse multi-collapse" id="multiCollapseExample1">`

### Dropdowns

with Single button or `<a>` tag.

```html
<div class="dropdown">
  <button
    class="btn btn-secondary dropdown-toggle"
    type="button"
    data-bs-toggle="dropdown"
    aria-expanded="false"
  >
    Dropdown button
  </button>
  <ul class="dropdown-menu">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another action</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
  </ul>
</div>
```

can be split button with the addition of `.dropdown-toggle-split`. and can be used as navbar in phone or else...

```html
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Navbar</a>
    <button
      class="navbar-toggler"
      type="button"
      data-bs-toggle="collapse"
      data-bs-target="#navbarNavDarkDropdown"
      aria-controls="navbarNavDarkDropdown"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNavDarkDropdown">
      <ul class="navbar-nav">
        <li class="nav-item dropdown">
          <a
            class="nav-link dropdown-toggle"
            href="#"
            role="button"
            data-bs-toggle="dropdown"
            aria-expanded="false"
          >
            Dropdown
          </a>
          <ul class="dropdown-menu dropdown-menu-dark">
            <li><a class="dropdown-item" href="#">Action</a></li>
            <li><a class="dropdown-item" href="#">Another action</a></li>
            <li><a class="dropdown-item" href="#">Something else here</a></li>
          </ul>
        </li>
      </ul>
    </div>
  </div>
</nav>
```

will be:
![](/bootStrap5.2/images/77.PNG)

Directions have usage too: `.dropdown-center`, `.dropup`, `.dropup-center`, `.dropend`, `.dropstart`. Add `.active` to items in the dropdown to style them as active. Add `.disabled` to items in the dropdown to style them as disabled. To align right the dropdown menu with the given breakpoint or larger, add `.dropdown-menu{-sm|-md|-lg|-xl|-xxl}-end`. To align left the dropdown menu with the given breakpoint or larger, add `.dropdown-menu-end and .dropdown-menu{-sm|-md|-lg|-xl|-xxl}-start`.

#### Menu content

Add a header to label sections of actions in any dropdown menu. `<li><h6 class="dropdown-header">Dropdown header</h6></li>`. Separate groups of related menu items with a divider.`<li><hr class="dropdown-divider"></li>`. Put a form within a dropdown menu, or make it into a dropdown menu.

```html
<div class="dropdown">
  <button
    type="button"
    class="btn btn-primary dropdown-toggle"
    data-bs-toggle="dropdown"
    aria-expanded="false"
    data-bs-auto-close="outside"
  >
    Dropdown form
  </button>
  <form class="dropdown-menu p-4">
    <div class="mb-3">
      <label for="exampleDropdownFormEmail2" class="form-label"
        >Email address</label
      >
      <input
        type="email"
        class="form-control"
        id="exampleDropdownFormEmail2"
        placeholder="email@example.com"
      />
    </div>
    <div class="mb-3">
      <label for="exampleDropdownFormPassword2" class="form-label"
        >Password</label
      >
      <input
        type="password"
        class="form-control"
        id="exampleDropdownFormPassword2"
        placeholder="Password"
      />
    </div>
    <div class="mb-3">
      <div class="form-check">
        <input type="checkbox" class="form-check-input" id="dropdownCheck2" />
        <label class="form-check-label" for="dropdownCheck2">
          Remember me
        </label>
      </div>
    </div>
    <button type="submit" class="btn btn-primary">Sign in</button>
  </form>
</div>
```

### List group

The most basic list group is an unordered list with list items and the proper classes. Add `.active` to a `.list-group-item` to indicate the current active selection. Add `.disabled` to a `.list-group-item` to make it appear disabled. Use `<a>`s or `<button>`s to create actionable list group items. Add `.list-group-flush` to remove some borders and rounded corners to render list group items edge-to-edge in a parent container (e.g., cards). Add the `.list-group-numbered` modifier class group items. Add `.list-group-horizontal` to change the layout of list group items from vertical to horizontal across all breakpoints.

### Modal

```html
<!-- Button trigger modal -->
<button
  type="button"
  class="btn btn-primary"
  data-bs-toggle="modal"
  data-bs-target="#exampleModal"
>
  Launch demo modal
</button>

<!-- Modal -->
<div
  class="modal fade"
  id="exampleModal"
  tabindex="-1"
  aria-labelledby="exampleModalLabel"
  aria-hidden="true"
>
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
        <button
          type="button"
          class="btn-close"
          data-bs-dismiss="modal"
          aria-label="Close"
        ></button>
      </div>
      <div class="modal-body">...</div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">
          Close
        </button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>
```

You can also create a scrollable modal that allows scroll the modal body by adding `.modal-dialog-scrollable` to `.modal-dialog`. Add `.modal-dialog-centered` to `.modal-dialog` to vertically center the modal. Have a bunch of buttons that all trigger the same modal with slightly different contents? Use `event.relatedTarget` and `HTML data-bs-* attributes` to vary the contents of the modal depending on which button was clicked.
Optional sizes :

| Size    | Class           | Modal max-width |
| ------- | --------------- | --------------- |
| Small   | .modal-sm       | 300px           |
| Default | None            | 500px           |
| Large   | .modal-lg       | 800px           |
| Extra   | large .modal-xl | 1140px          |

Fullscreen Modal:

| Class                      | Availability |
| -------------------------- | ------------ |
| .modal-fullscreen          | Always       |
| .modal-fullscreen-sm-down  | 576px        |
| .modal-fullscreen-md-down  | 768px        |
| .modal-fullscreen-lg-down  | 992px        |
| .modal-fullscreen-xl-down  | 1200px       |
| .modal-fullscreen-xxl-down | 1400px       |

### Navbar

```html
<nav class="navbar navbar-expand-lg bg-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Navbar</a>
    <button
      class="navbar-toggler"
      type="button"
      data-bs-toggle="collapse"
      data-bs-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Link</a>
        </li>
        <li class="nav-item dropdown">
          <a
            class="nav-link dropdown-toggle"
            href="#"
            role="button"
            data-bs-toggle="dropdown"
            aria-expanded="false"
          >
            Dropdown
          </a>
          <ul class="dropdown-menu">
            <li><a class="dropdown-item" href="#">Action</a></li>
            <li><a class="dropdown-item" href="#">Another action</a></li>
            <li><hr class="dropdown-divider" /></li>
            <li><a class="dropdown-item" href="#">Something else here</a></li>
          </ul>
        </li>
        <li class="nav-item">
          <a class="nav-link disabled">Disabled</a>
        </li>
      </ul>
      <form class="d-flex" role="search">
        <input
          class="form-control me-2"
          type="search"
          placeholder="Search"
          aria-label="Search"
        />
        <button class="btn btn-outline-success" type="submit">Search</button>
      </form>
    </div>
  </div>
</nav>
```

will be:
![](/bootStrap5.2/images/78.PNG)

### Offcanvas

Below is an offcanvas example that is shown by default (via `.show` on `.offcanvas` and `.offcanvas.show` shows content).

```html
<a
  class="btn btn-primary"
  data-bs-toggle="offcanvas"
  href="#offcanvasExample"
  role="button"
  aria-controls="offcanvasExample"
>
  Link with href
</a>
<button
  class="btn btn-primary"
  type="button"
  data-bs-toggle="offcanvas"
  data-bs-target="#offcanvasExample"
  aria-controls="offcanvasExample"
>
  Button with data-bs-target
</button>

<div
  class="offcanvas offcanvas-start"
  tabindex="-1"
  id="offcanvasExample"
  aria-labelledby="offcanvasExampleLabel"
>
  <div class="offcanvas-header">
    <h5 class="offcanvas-title" id="offcanvasExampleLabel">Offcanvas</h5>
    <button
      type="button"
      class="btn-close"
      data-bs-dismiss="offcanvas"
      aria-label="Close"
    ></button>
  </div>
  <div class="offcanvas-body">
    <div>
      Some text as placeholder. In real life you can have the elements you have
      chosen. Like, text, images, lists, etc.
    </div>
    <div class="dropdown mt-3">
      <button
        class="btn btn-secondary dropdown-toggle"
        type="button"
        data-bs-toggle="dropdown"
      >
        Dropdown button
      </button>
      <ul class="dropdown-menu">
        <li><a class="dropdown-item" href="#">Action</a></li>
        <li><a class="dropdown-item" href="#">Another action</a></li>
        <li><a class="dropdown-item" href="#">Something else here</a></li>
      </ul>
    </div>
  </div>
</div>
```

will be:
![](/bootStrap5.2/images/79.PNG)

add `.text-bg-dark` to the `.offcanvas` and `.btn-close-white` to `.btn-close` for proper styling with a dark offcanvas. Scrolling the `<body>` element is disabled when an offcanvas and its backdrop are visible. Use the `data-bs-scroll` attribute to enable `<body>` scrolling. `<div class="offcanvas offcanvas-start" data-bs-scroll="true" data-bs-backdrop="false" tabindex="-1" id="offcanvasScrolling" aria-labelledby="offcanvasScrollingLabel">`
Responsive offcanvas classes are available across for each breakpoint.

- .offcanvas
- .offcanvas-sm
- .offcanvas-md
- .offcanvas-lg
- .offcanvas-xl
- .offcanvas-xxl

There’s no default placement for offcanvas components, so you must add one of the modifier classes below.

- .offcanvas-start places offcanvas on the left of the viewport (shown above)
- .offcanvas-end places offcanvas on the right of the viewport
- .offcanvas-top places offcanvas on the top of the viewport
- .offcanvas-bottom places offcanvas on the bottom of the viewport

### Pagination

```html
<nav aria-label="Page navigation example">
  <ul class="pagination">
    <li class="page-item"><a class="page-link" href="#">Previous</a></li>
    <li class="page-item"><a class="page-link" href="#">1</a></li>
    <li class="page-item"><a class="page-link" href="#">2</a></li>
    <li class="page-item"><a class="page-link" href="#">3</a></li>
    <li class="page-item"><a class="page-link" href="#">Next</a></li>
  </ul>
</nav>
```

will be:
![](/bootStrap5.2/images/80.PNG)

Use `.disabled` for links that appear un-clickable and `.active` to indicate the current page. Add `.pagination-lg` or `.pagination-sm` for additional sizes. Change the alignment of pagination components with `.justify-content-center`, `.justify-content-end`.

### Placeholders

Use loading placeholders for your components or pages to indicate something may still be loading.

In the example below, we take a typical card component and recreate it with placeholders applied to create a “loading card”. Size and proportions are the same between the two.

```html
<div class="card">
  <img src="..." class="card-img-top" alt="..." />

  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">
      Some quick example text to build on the card title and make up the bulk of
      the card's content.
    </p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>

<div class="card" aria-hidden="true">
  <img src="..." class="card-img-top" alt="..." />
  <div class="card-body">
    <h5 class="card-title placeholder-glow">
      <span class="placeholder col-6"></span>
    </h5>
    <p class="card-text placeholder-glow">
      <span class="placeholder col-7"></span>
      <span class="placeholder col-4"></span>
      <span class="placeholder col-4"></span>
      <span class="placeholder col-6"></span>
      <span class="placeholder col-8"></span>
    </p>
    <a
      href="#"
      tabindex="-1"
      class="btn btn-primary disabled placeholder col-6"
    ></a>
  </div>
</div>
```

will be:
![](/bootStrap5.2/images/81.PNG)

How it works
Create placeholders with the `.placeholder` class and a grid column class (e.g., `.col-6`) to set the `width`. They can replace the text inside an element or be added as a modifier class to an existing component.

We apply additional styling to `.btns` via `::before` to ensure the `height` is respected. You may extend this pattern for other situations as needed, or add a `&nbsp;` within the element to reflect the height when actual text is rendered in its place.

### Popovers

```html
<button
  type="button"
  class="btn btn-lg btn-danger"
  data-bs-toggle="popover"
  data-bs-title="Popover title"
  data-bs-content="And here's some amazing content. It's very engaging. Right?"
>
  Click to toggle popover
</button>
```

will be:
![](/bootStrap5.2/images/82.PNG)

`data-bs-content="Top popover">` can be top right bottom left. `data-bs-title="Dismissible popover"`
will make it Dismissible.

### Progress bar

```html
<div class="progress">
  <div
    class="progress-bar"
    role="progressbar"
    aria-label="Basic example"
    style="width: 25%"
    aria-valuenow="25"
    aria-valuemin="0"
    aria-valuemax="100"
  ></div>
</div>
```

will be:
![](/bootStrap5.2/images/83.PNG)

Add labels to your progress bars by placing text within the `.progress-bar`. set a height value on the `.progress`, so if you change that value the inner `.progress-bar` will automatically resize accordingly. Add `.progress-bar-striped` to any `.progress-bar` to apply a stripe via CSS gradient over the progress bar’s background color. The striped gradient can also be animated. Add `.progress-bar-animated` to `.progress-bar `to animate the stripes right to left via CSS3 animations.

### Scrollspy

Automatically update Bootstrap navigation or list group components based on scroll position to indicate which link is currently active in the viewport. Scrollspy toggles the `.active` class on anchor (`<a>`) elements when the element with the id referenced by the anchor’s href is scrolled into view. Scrollspy is best used in conjunction with a Bootstrap `nav component` or `list group`, but it will also work with any anchor elements in the current page.

```html
<div class="row">
  <div class="col-4">
    <nav
      id="navbar-example3"
      class="h-100 flex-column align-items-stretch pe-4 border-end"
    >
      <nav class="nav nav-pills flex-column">
        <a class="nav-link" href="#item-1">Item 1</a>
        <nav class="nav nav-pills flex-column">
          <a class="nav-link ms-3 my-1" href="#item-1-1">Item 1-1</a>
          <a class="nav-link ms-3 my-1" href="#item-1-2">Item 1-2</a>
        </nav>
        <a class="nav-link" href="#item-2">Item 2</a>
        <a class="nav-link" href="#item-3">Item 3</a>
        <nav class="nav nav-pills flex-column">
          <a class="nav-link ms-3 my-1" href="#item-3-1">Item 3-1</a>
          <a class="nav-link ms-3 my-1" href="#item-3-2">Item 3-2</a>
        </nav>
      </nav>
    </nav>
  </div>

  <div class="col-8">
    <div
      data-bs-spy="scroll"
      data-bs-target="#navbar-example3"
      data-bs-smooth-scroll="true"
      class="scrollspy-example-2"
      tabindex="0"
    >
      <div id="item-1">
        <h4>Item 1</h4>
        <p>...</p>
      </div>
      <div id="item-1-1">
        <h5>Item 1-1</h5>
        <p>...</p>
      </div>
      <div id="item-1-2">
        <h5>Item 1-2</h5>
        <p>...</p>
      </div>
      <div id="item-2">
        <h4>Item 2</h4>
        <p>...</p>
      </div>
      <div id="item-3">
        <h4>Item 3</h4>
        <p>...</p>
      </div>
      <div id="item-3-1">
        <h5>Item 3-1</h5>
        <p>...</p>
      </div>
      <div id="item-3-2">
        <h5>Item 3-2</h5>
        <p>...</p>
      </div>
    </div>
  </div>
</div>
```

will be:
![](/bootStrap5.2/images/84.PNG)

Scrollspy also works with nested `.nav`s. If a nested `.nav` is `.active`, its parents will also be `.active`. Scroll the area next to the navbar and watch the active class change.

### Spinners

Normal spinner

```html
<div class="spinner-border" role="status">
  <span class="visually-hidden">Loading...</span>
</div>
```

Growing spinner

```html
<div class="spinner-grow" role="status">
  <span class="visually-hidden">Loading...</span>
</div>
```

with Buttons

```html
<button class="btn btn-primary" type="button" disabled>
  <span
    class="spinner-border spinner-border-sm"
    role="status"
    aria-hidden="true"
  ></span>
  <span class="visually-hidden">Loading...</span>
</button>
<button class="btn btn-primary" type="button" disabled>
  <span
    class="spinner-border spinner-border-sm"
    role="status"
    aria-hidden="true"
  ></span>
  Loading...
</button>
```

### Toasts

```html
<button type="button" class="btn btn-primary" id="liveToastBtn">
  Show live toast
</button>

<div class="toast-container position-fixed bottom-0 end-0 p-3">
  <div
    id="liveToast"
    class="toast"
    role="alert"
    aria-live="assertive"
    aria-atomic="true"
  >
    <div class="toast-header">
      <img src="..." class="rounded me-2" alt="..." />
      <strong class="me-auto">Bootstrap</strong>
      <small>11 mins ago</small>
      <button
        type="button"
        class="btn-close"
        data-bs-dismiss="toast"
        aria-label="Close"
      ></button>
    </div>
    <div class="toast-body">Hello, world! This is a toast message.</div>
  </div>
</div>
```

will be:
![](/bootStrap5.2/images/85.PNG)

### Tooltips

Enable tooltips:

```JavaScript
const tooltipTriggerList = document.querySelectorAll('[data-bs-toggle="tooltip"]')
const tooltipList = [...tooltipTriggerList].map(tooltipTriggerEl => new bootstrap.Tooltip(tooltipTriggerEl))
```

Tooltips on links

```html
<p class="muted">
  Placeholder text to demonstrate some
  <a href="#" data-bs-toggle="tooltip" data-bs-title="Default tooltip"
    >inline links</a
  >
  with tooltips. This is now just filler, no killer. Content placed here just to
  mimic the presence of
  <a href="#" data-bs-toggle="tooltip" data-bs-title="Another tooltip"
    >real text</a
  >. And all that just to give you an idea of how tooltips would look when used
  in real-world situations. So hopefully you've now seen how
  <a href="#" data-bs-toggle="tooltip" data-bs-title="Another one here too"
    >these tooltips on links</a
  >
  can work in practice, once you use them on
  <a href="#" data-bs-toggle="tooltip" data-bs-title="The last tip!"
    >your own</a
  >
  site or project.
</p>
```

---

## Helpers

### Clearfix

Quickly and easily clear floated content within a container by adding a clearfix utility.`<div class="clearfix">...</div>`.

### Color & background

Set a background color with contrasting foreground color.

```html
<div class="card text-bg-primary mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <p class="card-text">
      Some quick example text to build on the card title and make up the bulk of
      the card's content.
    </p>
  </div>
</div>
<div class="card text-bg-info mb-3" style="max-width: 18rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <p class="card-text">
      Some quick example text to build on the card title and make up the bulk of
      the card's content.
    </p>
  </div>
</div>
```

Use them in place of combined .text-_ and .bg-_ classes, like on badges

### Colored links

Colored links with hover states. You can use the `.link-*` classes to colorize links. `<a href="#" class="link-primary">Primary link</a>`

### Position

Use these helpers for quickly configuring the position of an element.

- `.fixed-top`
  Position an element at the top of the viewport, from edge to edge.
- `.fixed-bottom`
  Position an element at the bottom of the viewport, from edge to edge.
- `.sticky-top`
  Position an element at the top of the viewport, from edge to edge.
- Responsive variations also exist for `.sticky-top` utility.
- `.sticky-bottom`
  Position an element at the bottom of the viewport, from edge to edge.

### Vertical rule

Use the custom vertical rule helper to create vertical dividers like the `<hr>` element.

```html
<div class="d-flex" style="height: 200px;">
  <div class="vr"></div>
</div>
```

### Visually hidden

Use these helpers to visually hide elements but keep them accessible to assistive technologies.

---

## Utilities

IDC :D.
