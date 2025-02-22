---
title: "SpaceVim lang#markdown layer"
description: "Edit markdown within vim, autopreview markdown in the default browser, with this layer you can also format markdown files."
---

# [Available Layers](../../) >> lang#markdown

<!-- vim-markdown-toc GFM -->

- [Description](#description)
- [Install](#install)
- [Formatting](#formatting)
  - [options](#options)
- [Tagbar](#tagbar)
- [Key bindings](#key-bindings)

<!-- vim-markdown-toc -->

## Description

This layer is for editing markdown file.

## Install

To use this configuration layer, update your custom configuration file with:

```toml
[[layers]]
  name = "lang#markdown"
```

The tagbar support is provided via lvht/tagbar-markdown which requires php to be installed. You can also use [mdctags](https://github.com/wsdjeg/mdctags.rs)
which is written in rust.

## Formatting

SpaceVim uses remark to format Markdown file by default.
You can install remark via [npm](https://www.npmjs.com/get-npm), the commands are shown below.

```sh
npm -g install remark
npm -g install remark-cli
npm -g install remark-stringify
npm -g install remark-frontmatter
npm -g install wcwidth
```

To use [Prettier](https://github.com/prettier/prettier),
you need to change the layer option: `enabled_formatters`.

You can install [Prettier](https://github.com/prettier/prettier) via [yarn](https://yarnpkg.com/lang/zh-hans/docs/install/#windows-stable) or [npm](https://www.npmjs.com/get-npm), the commands are shown below:

1. Via `yarn`

```sh
yarn global add prettier
```

2. Via `npm`

```sh
npm install --global prettier
```

### options

**listItemIndent**

How to indent the content from list items (`tab`, `mixed` or 1 , default: 1).

- `'tab'`: use tab stops (4 spaces)
- `'1'`: use one space
- `'mixed'`: use `1` for tight and `tab` for loose list items

**enableWcwidth**

Enable/Disable wcwidth for detecting the length of a table cell, default is 0. To enable this option, you need to install [wcwidth](https://www.npmjs.com/package/wcwidth)

**listItemChar**

Bullet marker to use for list items (`'-'`, `'*'`, or `'+'`, default: `'-'`).

**enabled_formatters**

Specify the enabled formater for markdown file, default is `['remark']`. You can also append multiple formatters to this list. e.g. `["remark", "prettier"]`.

## Tagbar

To have a table of the headings in the tagbar (toggled by [F2]), make sure php is in your `$PATH` (you can test this in SpaceVim : `:!php --version` should print something about php).

If you don't want to install php, you can use [mdctags](https://github.com/wsdjeg/mdctags.rs) as an alternative.

## Key bindings

| Key bindings | mode          | Descriptions                                           |
| ------------ | ------------- | ------------------------------------------------------ |
| `SPC b f`    | Normal        | Format current buffer                                  |
| `SPC l c`    | Normal/Visual | Create content at cursor                               |
| `SPC l C`    | Normal/Visual | Remove content                                         |
| `SPC l k`    | Normal/Visual | Add URL link for word under cursor or slected word     |
| `SPC l K`    | Normal/Visual | Add picture link for word under cursor or slected word |
| `SPC l r`    | Normal/Visual | Run code block                                      |
| `SPC l f`    | Normal/Visual | Format code block                                      |
| `SPC l u`    | Normal/Visual | Update content                                         |
| `SPC l p`    | Normal        | Real-time markdown preview                             |
| `SPC l t`    | Normal        | toggle todo status                                     |
