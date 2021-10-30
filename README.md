# Vim Diagon

![screencast](https://i.imgur.com/0zo22qu.gif)

[Diagon][diagon-repo] is a useful tool to generate simple yet useful diagrams.
This plugin is a wrapper of it to simplify your workflow of drawing. If you,
like me, sometimes have situations when simple diagrams are needed to illustrate
something (especially in a post or other markdown files), then it is for you.

## Table of Contents

<!-- TOC START GFM -->

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
  - [Commands](#commands)
  - [Options](#options)
- [Mappings](#mappings)
- [Credits](#credits)

<!-- TOC END -->

## Prerequisites

This plugin requires Diagon's command line interface to work. You should follow
the instructions on its [GitHub repo][diagon-repo] to install it.

## Installation

Take [`vim-plug`][plug-repo] for example. Put the following line in your
`.vimrc` or `init.vim`.

```vim
Plug 'willchao612/vim-diagon'
```

## Usage

> You can always use `:h vim-diagon.txt` or other entries to refer to the docs.

First you can type some text in a code block like this. I will use the example
given by [Diagon's online demo][diagon-online] to illustrate. You can find other
accepted text formats and types of diagrams there, too.

```
Linux
  Android
  Debian
    Ubuntu
      Lubuntu
      Kubuntu
      Xubuntu
      Xubuntu
    Mint
  Centos
  Fedora
```

Then visually select the text within that code block and call `Diagon Tree`.

It turns into this. Simple as that.

```
Linux
 ├──├──Android
 ├──├──Debian
 ├──│   ├──Ubuntu
 ├──│   │   ├──Lubuntu
 ├──│   │   ├──Kubuntu
 ├──│   │   ├──Xubuntu
 ├──│   │   └──Xubuntu
 ├──│   └──Mint
 ├──├──Centos
 └──└──Fedora
```

### Commands

Command `:Diagon` can accept a range, if not given then default to current line.
A type must be given, a complete type list can be invoked by typing `Tab`. To
find all accepted types by Diagon API, refer to its [GitHub repo][diagon-repo].

### Options

Diagon API provides several additional style and options as well. If you want to
apply different styles or just to try out all the options, you can refer to
Diagon's [online demo][diagon-online] (it was first aimed to be an online tool).

With options, you can then call `:Diagon` like
`Diagon Math --style=ASCII --transform_math_letters=false`.

You only need to specify the options on call of `:Diagon`. No globle variables
are needed. If you use some styles or options so frequently, just add a mapping
for them.

## Mappings

There are no pre-defined mappings. You can add mappings like the one below.

```vim
noremap <Leader>D :Diagon<Space>

noremap <Leader>dm :Diagon Math<CR>
noremap <Leader>ds :Diagon Sequence<CR>
noremap <Leader>dt :Diagon Tree<CR>
```

Then press `Tab` to invoke complete list.

## Credits

Many thanks to [@ArthurSonzogni](https://github.com/ArthurSonzogni) for his work
on [Diagon][diagon-repo] project. This plugin wouldn't have existed without it.

[diagon-repo]: https://github.com/ArthurSonzogni/Diagon
[diagon-online]: https://arthursonzogni.com/Diagon/
[plug-repo]: https://github.com/junegunn/vim-plug
