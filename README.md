# Aqademia

**A XeTeX template for printable academic documents.**

This is a custom XeTeX template designed for note taking and posterior printing (hence the serif font).
It's a redesign of [advy99](https://github.com/advy99)'s template, which is a heavy redesign of one [Dunspa](https://github.com/Dunspa) provided us with.
We regretably can't find the primary source anywhere, sorry about that.
The listings style was inspired by [Wandmalfarbe](https://github.com/Wandmalfarbe)'s Eisvogel.

The placeholder image `src/titlepage.png` is *Troiana Iris* by Albrecht Dürer.

A demo is avaliable at the [releases](https://github.com/Groctel/aqademia/releases) page.

![Preview](preview.png)

## Dependencies

The font used in listings is `Liberation Mono`.
The document is designed to be build with `XeTeX`.

## Using and building

A full `LaTeX` distribution is assumed.

The template must be included manually in the file, be it by adding it to your `~/texmf` or by symlinking it to the template (the same way I do in the `src` directory).
Until the template is considered feature complete, you will need to manually include it yourself, which you can do with a submodule:

```sh
git submodule add https://github.com/Groctel/aqademia
```

Build it the project with `xelatex` in the same directory where the main file is:

```sh
cd src
xelatex aqademia.tex
```

## Document properties

### Physical properties

This document is designed to be printed in European A4 paper and to fit as much text as possible in a single page without becoming too crowded (check the margins in `marginsrb`).
It uses `fancy` style headers and footers and coloured hyperlinks.

### Custom commands

- **`\aqchap{text}`:** Matches the chapter indicator text to `text`.
- **`\aqsec{text}`:** Matches the section indicator text to `text`.
- **`\aqssec{text}`:** Matches the subsection indicator text to `text`.
- **`\aqsssec{text}`:** Matches the subsubsection indicator text to `text`.
- **`\aqapp{text}`:** Starts the appendices with their chapter indicator text set to `text`.
- **`\aqtitlepage[nolicense][author]{org}{subtitle}{link}`:** Generates a title page with the following options:
  - **`nolicense`:** Optionally remove the license from the title page
  - **`author`:** Show an author different to `\theauthor`, which is shown in `rhead`
  - **`org`:** Show the organisation over the title
  - **`subtitle`:** Show a subtitle next to the document's title
  - **`link`:** Show a url to the document's repository
- **`\code{text}`:** Renders the `text` in monospaced font a bit scaled down to fit the paragraph's line height

If you were previously using `texttt` for titles you can migrate it to `code` by running this command at the root of your tex project:

```sh
find -name "*.tex" -exec sed -i 's/texttt/code/' {} +
```

### Arguments

This template provides some arguments to customize your document:

| Argument    | Type   | Default     | Description                                   |
| :---------- | :----- | :---------- | :-------------------------------------------- |
| `ltitle`    | String | `CC`        | Title argument of `doclicense`.               |
| `lmodifier` | String | `by-nc-sap` | Modifier argumento for `doclicense`.          |
| `lversion`  | String | `4.0`       | Version argument for `doclicense`.            |
| `title`     | String |             | Title of the document to be printed in lhead. |
| `tab`       | String | `3`         | Size of tabs in listings.                     |


# TO-DO

- Upgrade the template to a `.cls` file
- Stylise default tables
