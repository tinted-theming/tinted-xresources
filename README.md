# Tinted Xresources

Tinted themes for [Xresources]. Have a look at the [gallery] page for
examples of what the theme colors look like.

Formerly [base16-xresources], however since the repository now supports
the [base16] and [base24] scheme systems, the repo has been renamed.

## Installation

### Manual

Add the colors to your **.Xresources** dotfile

```sh
curl https://raw.githubusercontent.com/tinted-theming/tinted-xresources/main/xresources/base16-default-dark.Xresources >> ~/.Xresources
xrdb -load ~/.Xresources
```

### Tinty

If you use [Tinty] to set your themes, complete the following steps to 
update your theme when running `tinty apply base16-default-dark` (where
`base16-default-dark` is a placeholder scheme name):

1. Create a `theme` file for Xresources to `include` at `~/theme`
1. Add the following include directive to your `~/.Xresources` dotfile:
`#include "Xresources.d/theme"`
2. Add the following `toml` settings to your Tinty
   `~/.config/tinted-theming/tinty/config.toml` file:

   ```toml
   [[items]]
   path = "https://github.com/tinted-theming/tinted-xresources"
   name = "tinted-xresources"
   themes-dir = "xresources"
   hook = "cp -f %f ~/theme && xrdb -load ~/.Xresources"
   supported-systems = ["base16", "base24"]
   ```

## Contributing

See [CONTRIBUTING.md], which contains building and contributing
instructions.

[base16-xresources]: https://github.com/tinted-theming/base16-xresources
[Xresources]: https://wiki.gentoo.org/wiki/X_resources
[gallery]: https://tinted-theming.github.io/base16-gallery
[CONTRIBUTING.md]: CONTRIBUTING.md
