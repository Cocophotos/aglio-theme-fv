# Aglio FV Theme


This is *FV*, the theme engine for [Aglio](https://github.com/danielgtaylor/aglio). It takes an [API Blueprint](http://apiblueprint.org/) AST and renders it into static HTML. Example use:

```bash
$ sudo npm install -g aglio-theme-fv
$ aglio -i blueprint.apib -o MyAPI.html
```

Theme engines for Aglio are described in more detail in the [Aglio documentation](https://github.com/danielgtaylor/aglio#customizing-output).

## Design Philosophy
FV is based on Oglio (the default theme) and is designed from the ground up to be both **fast** and **extensible** while maintaining backward compatibility with most of the original Aglio theme. It uses the following technologies:

* [Less](http://lesscss.org/) to produce CSS
* [Markdown-it](https://github.com/markdown-it/markdown-it#readme) to render Markdown
* [Jade](http://jade-lang.com/) to produce HTML
* [Highlight.js](https://highlightjs.org/) to highlight code snippets

For backward compatibility, Jade templates can continue to use inline Stylus and CoffeeScript.

Contrary to Oglio, the API blueprint JSON schema is rendered like the parameters (easier to read).

## Theme Options

Olio comes with a handful of configurable theme options. These are set via the `--theme-XXX` parameter, where `XXX` is one of the following:

Name           | Description
-------------- | ------------------
`condense-nav` | Whether to condense nagivation for resources with only a single action (default is `true`).
`full-width`   | Whether to use the full page width or a responsive layout (default is responsive).
`style`        | LESS or CSS to control the layout and style of the document using the variables from below. Can be a path to your own file or one of the following presets: `default`. May be an array of paths and/or presets.
`template`     | Jade template to render HTML. Can be a path to your own file or one of the following presets: `default`.
`variables`    | LESS variables that control theme colors, fonts, and spacing. Can be a path to your own file or one of the following presets: `default`, `flatly`, `slate`, `cyborg`. May be an array of paths and/or presets.

**Note**: When using this theme programmatically, these options are cased like you would expect in Javascript: `--theme-full-width` becomes `options.themeFullWidth`.

License
=======
Copyright &copy; 2016 Daniel G. Taylor and 2016 Corentin Ribeyre

http://dgt.mit-license.org/
