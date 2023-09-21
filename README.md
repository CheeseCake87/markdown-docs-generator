# markdown-docs-generator

The aim of this project is to make generating documentation have a small setup footprint and be easy to use.
It leverages the power of Flask to render the markdown files into HTML.

## Setup

Add the following folders and their contents to your project:

```text
docs/
docs_gen/
docs_markdown/
```

## Commands

```text
flask --app docs_gen compile
```
This command is used to do a one time compile of the markdown files into HTML.

```text
flask --app docs_gen watch
```

This command is used to watch the markdown files for changes and recompile them into HTML.

## Markdown files explained

The `__index__.md` file is used to set up the `index.html` page.

The `__menu__.md` file is used to set up the `__menu__.html`.

Each markdown file in the `docs_markdown` must contain the following at the top of the file:

```text
Menu = Category/Page 1
Title = Page 1 Title
```

See the example files for more details.

The Menu value is used to insert the page into the menu and must match the structure of the `__menu__.md`

For example:

```text
- Category
    - Page 1
```

Would be:

```text
Menu = Category/Page 1
```

You can set a page to work with the top level. For example, to link to the `Category` menu entry you would do:

```text
Menu = Category
```

The Title value is used to set the title of the HTML page.

## Styling

This gives you a lot of control to set the styling by yourself in regular HTML/CSS or even JS if you'd want to build that in.

You can edit anything in the `docs_gen/templates` folder to set whatever styles you'd like.

CSS and images can be found in the `docs/static` folder.