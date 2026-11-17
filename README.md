# FlatUI Dark Modus Theme

An **experimental** dark theme for Emacs, using the [FlatUI colors](https://flatuicolors.com/).

It is a reimplementation of [`flatui-dark-theme`](https://github.com/theasp/flatui-dark-theme)
built on the [modus-themes](https://github.com/protesilaos/modus-themes) engine
(`modus-themes-theme`) instead of the raw `deftheme` / `custom-theme-set-faces` API.
Rather than defining ~550 faces by hand, it declares a complete FlatUI **palette** and
lets the modus-themes engine generate its full face set from it.

> **Status: experimental.** This is a proof-of-concept for building the theme on the
> modus-themes engine. It is expected to be folded back into
> [`flatui-dark-theme`](https://github.com/theasp/flatui-dark-theme) in the future, so
> it is not currently published on MELPA.
>
> Because it is palette-driven, the niche per-mode faces that the original defines
> (web-mode, gnus, erc, helm, magit, org, etc.) are **not** ported; the engine's own
> face set is used and colored by the palette.

## Requirements

- Emacs 29.1+
- [`modus-themes`](https://github.com/protesilaos/modus-themes) **5.0.0+** (the version
  that provides the theme-building API `modus-themes-theme`).

  ```elisp
  (package-install 'modus-themes)
  ```

## Installation

This is not on MELPA. Clone it and add it to your theme load path:

```elisp
(add-to-list 'custom-theme-load-path
             (expand-file-name "flatui-dark-modus-theme/"
                               (expand-file-name "~/.emacs.d/")))
```

(e.g. `git clone git@github.com:theasp/flatui-dark-modus-theme.git
~/.emacs.d/flatui-dark-modus-theme`)

## Usage

```elisp
(load-theme 'flatui-dark-modus t)
```

The theme is registered as a modus-themes derivative, so it also appears in
`modus-themes-registered-items`.

```elisp
;; extend the palette with extra named colors
(setq flatui-dark-modus-palette-user '((my-accent "#2ecc71")))

;; override existing palette entries
(setq flatui-dark-modus-palette-overrides '((keyword "#2ecc71")))
```

## License

GPL-2.0-or-later — see [LICENSE](LICENSE).
