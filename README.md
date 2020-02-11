# Aqademia

**A XeTeX template for printable academic documents.**

This is a custom XeTeX template designed for note taking and posterior printing (hence the serif font).
It's a redesign of [advy99](https://github.com/advy99)'s template, which is a heavy redesign of one [Dunspa](https://github.com/Dunspa) provided us with.
We regretably can't find the primary source anywhere, sorry about that.
The listings style was inspired by [Wandmalfarbe](https://github.com/Wandmalfarbe)'s Eisvogel.

The placeholder image `src/titlepage.png` is *Troiana Iris* by Albrecht Dürer.

A demo is avaliable at the [releases](https://github.com/Groctel/aqademia/releases) page.

![Preview](preview.png)

## Document properties

### Physical properties

This document is designed to be printed in European A4 paper and to fit as much text as possible in a single page without becoming too crowded (check the margins in `marginsrb`).
It uses `fancy` style headers and footers and coloured hyperlinks.

### Argumentos

This template provides some arguments to customize your document:

| Argument       | Type   | Default     | Description                                                   |
| :------------- | :----- | :---------- | :------------------------------------------------------------ |
| `license`      | Bool   | `false`     | Whether to display the licence at the title page.             |
| `subtitle`     | Bool   | `false`     | Whether to display the subtitle at the title page.            |
| `toc`          | Bool   | `false`     | Whether to display the table of contents after the titlepage. |
| `author`       | String |             | Author of the document.                                       |
| `date`         | String | `\today`    | Date of the last version of the document.                     |
| `graphics`     | String | `img/`      | Graphics directory.                                           |
| `language`     | String | `english`   | Language provided to `babel`                                  |
| `lmodifier`    | String | `by-nc-sap` | Modifier argumento for `doclicense`.                          |
| `ltitle`       | String | `CC`        | Title argument of `doclicense`.                               |
| `lversion`     | String | `4.0`       | Version argument for `doclicense`.                            |
| `organization` | String |             | Organisation or other supertitle.                             |
| `tab`          | String | `3`         | Size of tabs in listings.                                     |
| `title`        | String |             | Title of the document.                                        |
| `repository`   | String |             | Link to the document's repository.                            |
| `subtitle`     | String |             | Subtitle of the document (titlepage only).                    |

## Dependencies

The font used in listings is `Libertine Mono` (It is scaled down in inline code sections).
The document is designed to be build with `XeTeX`.

## Building

```bash
cd src
xelatex aqademia.tex
```

## About appendices

### Differences over sessions

While the chapter is declared outside the `input` files in the sessions, it is declared as the appendices header.
The `section` command is substituted by the `subsection` command previously used, so that the style is conserved without losing a sectioning level.

#### Subsections

The `subsection` level is also substituted by `subsubsection`.

### Numbering

Appendices are referred to as a letter, starting from letter `A`.


