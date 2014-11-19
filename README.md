# evil-escape
[![MELPA](http://melpa.org/packages/evil-escape-badge.svg)](http://melpa.org/#/evil-escape)
[![MELPA Stable](http://stable.melpa.org/packages/evil-escape-badge.svg)](http://stable.melpa.org/#/evil-escape)

Customizable key sequence to escape from insert state and everything else in
Emacs.

Press `fd` quickly to:

- escape from all evil states to normal state
- escape from evil-lisp-state to normal state
- abort evil ex command
- quit minibuffer
- abort isearch
- quit magit buffers
- quit help buffers
- hide neotree buffer

And more to come !

Contributions to support more buffers are _very welcome_:
**Escape Everything !**

## Install

The package _will be available soon_ in [MELPA][].

If you have MELPA in `package-archives`, use

    M-x package-install RET evil-escape RET

If you don't, open `evil-escape.el` in Emacs and call
`package-install-from-buffer`.

## Usage

To toggle the `evil-escape` mode globally:

    M-x evil-escape-mode

## Customization

The key sequence can be customized with the variable `evil-escape-key-sequence`.

**Note:** The variable `evil-escape-key-sequence` must be set before requiring
`evil-escape`.

## Known Bugs

- `key-chord` with `evil` corrupts the display of the prefix argument in the
echo area For instance entering `11` will display `1 1 1 -` instead of `1 1 -`.
Only the display is affected, the prefix argument is not altered, more info:
[bug entry][].

[MELPA]: http://melpa.org/
[bug entry]: https://bitbucket.org/lyro/evil/issue/365/key-chord-confuse-evils-minibuffer-echo
