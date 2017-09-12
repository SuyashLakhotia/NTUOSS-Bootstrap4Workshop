# NTUOSS Bootstrap 4 Workshop

*by Suyash Lakhotia for NTU Open Source Society*

This workshop is based on Bootstrap v4.0.0-beta and assumes basic knowledge of HTML & CSS (short recap can be found below).

***Disclaimer*** *-* *This document is only meant to serve as a reference for the attendees of the workshop. It does not cover all the concepts or implementation details discussed during the actual workshop.*

<hr>

### Workshop Details:

**When?**: Friday, 15 Sept 2017. 6:30 PM - 8:30 PM.<br>
**Where?**: Theatre@TheNest, Innovation Centre, Nanyang Technological University<br>
**Who?**: NTU Open Source Society

### Questions?

Raise your hand at any time during the workshop or shoot me an [e-mail](mailto:hello@suyashlakhotia.com) later.

### Errors?

If you find any mistake (typo or anything else), please make a pull request or [post an issue](https://github.com/SuyashLakhotia/NTUOSS-Bootstrap4Workshop/issues/new)! Thanks!

<hr>

## Task 0 - Initial Setup

1. Download a text editor if you don't already have one. I would recommend either:
    1. [Atom](https://atom.io/)
    2. [Sublime Text 2](http://www.sublimetext.com/2)
    3. [Brackets](http://brackets.io/)
2. Download [this project](https://github.com/SuyashLakhotia/NTUOSS-Bootstrap4Workshop/archive/master.zip) and unzip the file to get started.

## Revisiting HTML & CSS

Before we dive into creating websites using Bootstrap 4, let's do quick recap of HTML & CSS. HTML is the markup language that you surround content with and is made up of different angle-bracketed tags while CSS is the language used to define the styles to apply to the web page. In a nutshell, if you want to display content on a web page, you surround it with the appropriate HTML tags and then apply CSS styles to make it look *prettier*.

### HTML

An HTML file is divided into two parts, the head and the body:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        ...
    </head>
    <body>
        ...
    </body>
</html>
```

The head contains the metadata for the web page and is not displayed directly. It contains the title of the web page, any meta tags and is usually also where you define which CSS stylesheets you want to import for the page (and sometimes which JavaScript files too).

The body contains the actual content to be displayed. The content to be displayed is wrapped in different tags according to the structure of the data, for example:

```html
<h1 id="some-id">Title</h1>
...
<h6>Smallest Subtitle<h6>

<p>Some paragraph content. You can <strong>bold</strong> or <em>italicize</em> text easily.</p>

<div class="some-class">
    Defines a division of the content.
</div>

<img src="path/to/some/image.png">
```

HTML tags usually have a matching opening (e.g. `<p>`) and closing (e.g. `</p>`) tag. They may or may not have additional attributes (e.g. `src=""`) defined. The different HTML tags and examples of their usage can be found [here](https://www.w3schools.com/tags/).

### CSS

A CSS file looks something like this:

```css
h1 {
    color: blue;
}

.some-class {
    background-color: #fff;
    border: 1px bottom #000;
}

#some-id {
    padding: 10px;
    text-align: justify;
}
```

Each style rule consists of a selector (e.g. `h1` or `.some-class`) followed by the declarations that apply to all elements that are matched by the selector. You can find out more about CSS [here](https://www.w3schools.com/css/default.asp).

## Task 1 - Setting Up Bootstrap

![task 1 screenshot](screenshots/task_0.png?raw=true)

1. Open up `index.html` (inside `BootstrapWorkshop/`) in your preferred text editor.
2. Open up `index.html` in your browser as well and remember to hit refresh whenever you make changes to the files. You can also use *Live Preview* if you're using Brackets and *atom-live-server* if you're using Atom so you don't have to keep refreshing every time.
3. Replace the contents of `index.html` with the following:

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta/css/bootstrap.min.css" integrity="sha384-/Y6pD6FV/Vv2HJnA6t+vslU6fwYXjCFtcEpHbNJ0lyAFsXTsjBbfaDjzALeQsN6M" crossorigin="anonymous">

    <link rel="stylesheet" href="css/custom.css">

    <title>Personal Website</title>
</head>

<body>
    <h1>Hello, world!</h1>

    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.11.0/umd/popper.min.js" integrity="sha384-b/U6ypiBEHpOf/4+1nzFpr53nxSS+GLCkfwBdFNTxtclqqenISfwAzpKaMNFNmj4" crossorigin="anonymous"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta/js/bootstrap.min.js" integrity="sha384-h0AbiXch4ZDo7tp9hKZ4TsHbi047NrKGLO3SEJAg45jXxnGIfYzk4Si90RDIqNm1" crossorigin="anonymous"></script>
</body>

</html>
```

The above code loads your custom stylesheet `custom.css`, Bootstrap's CSS & JavaScript as well as Bootstrap's JavaScript dependencies (jQuery & Popper.js) into `index.html`.

**Note:** It is important to link your own CSS stylesheet *after* Bootstrap's if you wish to override any of the default classes.

## Task 2 - The Grid System

If you've ever built your own website before, you know how much of a pain it can be to make sure things are aligned correctly. Thankfully, Bootstrap has a simple solution to that problem called the [grid](https://getbootstrap.com/docs/4.0/layout/grid/).

Bootstrap's grid system is made up of responsive rows & columns where each row has 12 columns. This allows you to layout any HTML element fairly easily. Let's try doing that for three paragraphs of text as an example.

In `index.html`, insert the following inside the `<body>` tag just before the `<script>` tags:

```html
<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>

<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>

<p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
```

![task 2a screenshot](screenshots/task_2a.png?raw=true)

### Containers

![task 2b screenshot](screenshots/task_2b.png?raw=true)

The first thing we're going to do is wrap all the paragraphs in containers. Containers are the most basic layout element in Bootstrap and are required when using the default grid system. You may choose one of the two containers:

`.container`  - responsive fixed size container

```html
<div class="container">
    ...
</div>
```

`.container-fluid` - full-width container that spans the entire width of the viewport (i.e. visible area of the browser)

```html
<div class="container-fluid">
    ...
</div>
```

For this example, we'll be wrapping our paragraphs with a `<div>` of the `.container` class to add a modest margin to the sides:

```html
<div class="container">
    <p>Lorem ipsum dolor...</p>
    <p>Lorem ipsum dolor...</p>
    <p>Lorem ipsum dolor...</p>
</div>
```

### Rows & Columns

The next step is to wrap our paragraphs with a `.row` inside `.container`:

```html
<div class="container">
    <div class="row">
        <p>Lorem ipsum dolor...</p>
        <p>Lorem ipsum dolor...</p>
        <p>Lorem ipsum dolor...</p>
    </div>
</div>
```

One thing to remember is that only `.col` tags should be immediate children of `.row` tags and content should be placed within these columns. So, let's create three `.col` tags of equal width for our paragraphs:

```html
<div class="container">
    <div class="row">
        <div class="col-lg-4">
            <p>Lorem ipsum dolor...</p>
        </div>
        <div class="col-lg-4">
            <p>Lorem ipsum dolor...</p>
        </div>
        <div class="col-lg-4">
            <p>Lorem ipsum dolor...</p>
        </div>
    </div>
</div>
```

What we have just done is assign 1/3 of large viewports to each paragraph by putting each paragraph in 4 columns out of a total of 12 columns. Try playing around with these numbers and see what happens but remember that the total number of columns in a row must not exceed 12.

![task 2c screenshot](screenshots/task_2c.png?raw=true)

A shortcut for equal width columns is to simply leave the number blank i.e.:
**Note:** `col-lg-*` will only take effect for large screens (i.e. `>= 992px` in width) so the same website on mobile will render the paragraphs in separate rows (which is fine since they would be really close together and impossible to read otherwise). In order to specify different column widths for different screen sizes, Bootstrap provides (in increasing order of screen width) `col-*`, `col-sm-*`, `col-md-*`, `col-lg-*` & `col-xl-*` classes. You can find out more [here](https://getbootstrap.com/docs/4.0/layout/grid/#grid-options).


```html
<div class="row">
    <div class="col-lg">
        <p>Lorem ipsum dolor...</p>
    </div>
    <div class="col-lg">
        <p>Lorem ipsum dolor...</p>
    </div>
    <div class="col-lg">
        <p>Lorem ipsum dolor...</p>
    </div>
</div>
```

### Alignment Classes

Bootstrap's grid system also comes with a variety of classes to better align columns vertically & horizontally within rows.

Vertical alignment can be achieved using a `align-items-*` class on the row or `align-self-*` classes on each column. Copy the following pieces of code into `index.html` just right after your previous `.container` tag, before the `<script>` tags, and see how it renders on the browser.

Note that the `style` attribute has only been defined to create a distinction between the different divs.

![task 2d screenshot](screenshots/task_2d.png?raw=true)

```html
<div class="container">
    <div class="row align-items-start" style="height: 200px; background-color: rgba(255,0,0,.1); border: 1px solid #000;">
        <div class="col">
            Column Content
        </div>
        <div class="col">
            Column Content
        </div>
        <div class="col">
            Column Content
        </div>
    </div>
    <div class="row align-items-center" style="height: 200px; background-color: rgba(255,0,0,.1); border: 1px solid #000;">
        <div class="col">
            Column Content
        </div>
        <div class="col">
            Column Content
        </div>
        <div class="col">
            Column Content
        </div>
    </div>
    <div class="row align-items-end" style="height: 200px; background-color: rgba(255,0,0,.1); border: 1px solid #000;">
        <div class="col">
            Column Content
        </div>
        <div class="col">
            Column Content
        </div>
        <div class="col">
            Column Content
        </div>
    </div>
</div>
```

![task 2e screenshot](screenshots/task_2e.png?raw=true)

```html
<div class="container">
    <div class="row" style="height: 200px; background-color: rgba(255,0,0,.1);">
        <div class="col align-self-start" style="background-color: rgba(86,61,124,.15); border: 1px solid 1px solid rgba(86,61,124,.2);">
            Column Content
        </div>
        <div class="col align-self-center" style="background-color: rgba(86,61,124,.15); border: 1px solid 1px solid rgba(86,61,124,.2);">
            Column Content
        </div>
        <div class="col align-self-end" style="background-color: rgba(86,61,124,.15); border: 1px solid 1px solid rgba(86,61,124,.2);">
            Column Content
        </div>
    </div>
</div>
```

Horizontal alignment can be achieved using one of the `.justify-content-*` classes on the row. Copy the following piece of code into `index.html` and see how it renders on the browser. Note again that the `style` attribute has only been defined to create a distinction between the different divs.

![task 2f screenshot](screenshots/task_2f.png?raw=true)

```html
<div class="container">
    <div class="row justify-content-start">
        <div class="col-4" style="background-color: #eee; border: 1px solid #000;">
            Column Content
        </div>
        <div class="col-4" style="background-color: #eee; border: 1px solid #000;">
            Column Content
        </div>
    </div>
    <div class="row justify-content-center">
        <div class="col-4" style="background-color: #eee; border: 1px solid #000;">
            Column Content
        </div>
        <div class="col-4" style="background-color: #eee; border: 1px solid #000;">
            Column Content
        </div>
    </div>
    <div class="row justify-content-end">
        <div class="col-4" style="background-color: #eee; border: 1px solid #000;">
            Column Content
        </div>
        <div class="col-4" style="background-color: #eee; border: 1px solid #000;">
            Column Content
        </div>
    </div>
    <div class="row justify-content-around">
        <div class="col-4" style="background-color: #eee; border: 1px solid #000;">
            Column Content
        </div>
        <div class="col-4" style="background-color: #eee; border: 1px solid #000;">
            Column Content
        </div>
    </div>
    <div class="row justify-content-between">
        <div class="col-4" style="background-color: #eee; border: 1px solid #000;">
            Column Content
        </div>
        <div class="col-4" style="background-color: #eee; border: 1px solid #000;">
            Column Content
        </div>
    </div>
</div>
```

## Task 3 - Creating a Jumbotron

Alright, now that we know how the grid system works, let's actually start building our personal website. The first thing we're going to do is add a nice-looking title for our personal website! Delete everything inside `<body>` except for the `<script>` tags and insert the following code:

```html
<h1>YOUR NAME</h1>
<h3>Welcome to my personal website!</h3>
```

This looks pretty simple. Let's add some style to it by converting it into something Bootstrap calls a [jumbotron](https://getbootstrap.com/docs/4.0/components/jumbotron/).

Wrap the code inside a `<div>`. Most Bootstrap layout classes are applied to content-wrapping divs.

```html
<div>
    <h1>YOUR NAME</h1>
    <h3>Welcome to my personal website!</h3>
</div>
```

Let's assign the `.jumbotron` & `.jumbotron-fluid` class to the div. Just like that, Bootstrap allows you to make a pretty appealing title for your page.

```html
<div class="jumbotron jumbotron-fluid">
    ...
</div>
```

Now, let's add some typography classes and change the tags to make our title look better. Bootstrap comes with a lot of [typography utilities](https://getbootstrap.com/docs/4.0/content/typography/) that can help you make your website look good without too much effort.

```html
<div class="jumbotron jumbotron-fluid text-center">
    <h1 class="display-3">YOUR NAME</h1>
    <p class="lead">Welcome to my personal website!</p>
</div>
```

## Task 4 - Images

Let's go ahead and add a photo of ourself to the website. The first thing to do is to actually copy the image file and place it under a new directory `img/` and rename the file to `avatar.jpg`. If your image is a different format or in another directory, make sure to change the `src` attribute accordingly.

Once we've copied the image, we can place it in a row right after the jumbotron:

```html
<div class="container">
    <div class="row justify-content-center">
        <div class="col-6 col-lg-3">
            <img src="img/avatar.jpg" class="img-fluid">
        </div>
    </div>
</div>
```

If your image is bigger than the column width, it might overflow off its expected position. Let's fix that. Add the `.img-fluid` class to the `<img>` tag and let the magic happen. Just like that, Bootstrap automatically fits the images to the width assigned to it. This also helps when viewing the website through a mobile browser. Try resizing your browser. The image should shrink automatically.

In addition to the `.img-fluid` class, Bootstrap also offers the following classes for images:

1. `.img-thumbnail`: Adds a thumbnail-esque border to the image.
2. `.rounded`: Adds rounded corners to the image.
3. `.rounded-circle`: Crops the image into a circle.

## Task 5 - Spacing Classes

Now that we have our photo on the website, let's add a quick description right below the image in another row:

```html
<div class="container">
    <div class="row justify-content-center">
        ...
    </div>
    <div class="row justify-content-center">
        <div class="col-lg-8 text-justify">
            <p>This is a paragraph that should describe who you are, what you do and why you do it. But for now, I'm just going to keep typing random things until I write enough words to make it look like a decently-sized paragraph. I'm realizing that this may have not been the best idea. I should have just stuck to the Lorem Ipsum text from before. Oh well, now I'm too far in to give up. This is kind of like a metaphor for life, isn't it?</p>
        </div>
    </div>
</div>
```

Looks like the image and text may be too close together, let's fix that by adding a `margin-bottom` to the image row. Bootstrap provides a plethora of built-in classes to define margin & padding values for elements. Let's add `.mb-4` to our row, which will add a bottom margin of 1.5rems.

```html
<div class="container">
    <div class="row justify-content-center mb-4">
        ...
    </div>
    <div class="row justify-content-center">
        ...
    </div>
</div>
```

You can find out more about the available spacing classes [here](https://getbootstrap.com/docs/4.0/utilities/spacing/).

## Task 6 - Cards

The next thing we're going to do is add a few cards to showcase projects we've done. Cards are flexible content containers and an extremely popular modern web design tool.

Let's add a deck of three cards right after our paragraph of text:

```html
<div class="container my-4">
    <div class="card-deck">
        <div class="card">
            <div class="card-header">Header Content</div>
            <div class="card-body">
                <h4 class="card-title">Project 1</h4>
                <p class="card-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
            </div>
        </div>
        <div class="card">
            <div class="card-body">
                <h4 class="card-title">Project 2</h4>
                <p class="card-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
            </div>
        </div>
        <div class="card">
            <div class="card-body">
                <h4 class="card-title">Project 3</h4>
                <p class="card-text">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
            </div>
            <div class="card-footer">Footer Content</div>
        </div>
    </div>
</div>
```

As you can see, cards usually have `.card-title` & `.card-text` in their `.card-body` and may also have a header (i.e. `card-header`) or footer (i.e. `.card-footer`). We can also add a splash of color to our cards by adding any of the following classes to the `.card` div:

- `bg-primary`
- `bg-secondary`
- `bg-success`
- `bg-danger`
- `bg-warning`
- `bg-info`
- `bg-light`
- `bg-dark`

It is important to add the `.text-white` class if you're choosing a darker color as the background.

Cards are extremely flexible and have many more features that aren't covered here. To find out more, check out the documentation [here](https://getbootstrap.com/docs/4.0/components/card/).

## Task 7 - Buttons

Bootstrap comes with various button styles that can be implemented extremely easily. Let's add a button to one of our cards:

```html
<div class="card bg-light">
    <div class="card-body">
        ...
        <a href="#"><button type="button" class="btn btn-primary">Project Link</button></a>
    </div>
</div>
```

Again, Bootstrap comes with default classes that can be used to add a splash of color. Feel free to play around with them:

- `btn-primary`
- `btn-secondary`
- `btn-success`
- `btn-danger`
- `btn-warning`
- `btn-info`
- `btn-light`
- `btn-dark`
- `btn-link`

You can find out more about Bootstrap buttons [here](https://getbootstrap.com/docs/4.0/components/buttons/).

## Task 8 - Navbar

A navbar is a great way to navigate around websites or even a single web page. Bootstrap offers a fairly simple way to implement a navbar. Copy the following lines into `index.html` right above the jumbotron:

```html
<nav class="navbar sticky-top navbar-expand-lg navbar-dark bg-dark">
    <a class="navbar-brand" href="#">YOUR NAME</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
        <div class="navbar-nav">
            <a class="nav-item nav-link active" href="#">Home <span class="sr-only">(current)</span></a>
            <a class="nav-item nav-link" href="#">Projects</a>
            <a class="nav-item nav-link" href="#">Blog</a>
        </div>
    </div>
</nav>
```

Look at the navbar on your browser and try to compare the different parts to the code. For our current website, we don't really need a navbar since it's a fairly short single page website but as you grow the website to multiple pages or a really long single page, navbars allow users to easily navigate as well as place themselves.

The Bootstrap navbar is responsive & mobile-friendly by default. Try resizing your browser's width and see how your navbar changes.

Read more about Bootstrap's navbar [here](https://getbootstrap.com/docs/4.0/components/navbar/).

## Task ∞ - This Is Not The End

We have just covered a few features of the many, many features that has made Bootstrap a primary tool for many front-end developers. You can find out more about the different components & useful CSS classes Bootstrap offers in their [documentation](https://getbootstrap.com/docs/4.0/). Alternatively, play around with Bootstrap on your own and head to [StackOverflow](http://stackoverflow.com/) or [w3schools](http://www.w3schools.com/) whenever you hit a wall. Do note that Bootstrap 4 is relatively new and most online help may be referring to Bootstrap 3.

Additionally, you can jumpstart your website by using a template or theme from [here](https://themes.getbootstrap.com/).
