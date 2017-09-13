# evil-escape
[![MELPA](http://melpa.org/packages/evil-escape-badge.svg)](http://melpa.org/#/evil-escape)
[![MELPA Stable](http://stable.melpa.org/packages/evil-escape-badge.svg)](http://stable.melpa.org/#/evil-escape)

<!-- markdown-toc start - Don't edit this section. Run M-x markdown-toc-generate-toc again -->
**Table of Contents**

- [evil-escape](#evil-escape)
    - [Install](#install)
    - [Usage](#usage)
    - [Customization](#customization)
        - [Key sequence](#key-sequence)
        - [Delay between keys](#delay-between-keys)
        - [Unordered key sequence](#unordered-key-sequence)
        - [Excluding a major mode](#excluding-a-major-mode)
        - [Enable only for a list of major modes](#enable-only-for-a-list-of-major-modes)
        - [Inhibit evil-escape](#inhibit-evil-escape)
        - [Assign a key binding directly](#assign-a-key-binding-directly)

<!-- markdown-toc end -->

Customizable key sequence to escape from insert state and everything else in
Emacs.

Version 3.0 is a rewrite of `evil-escape` and removes the previous limitations:
- escape sequence can now be used in macros
- there is no limitation on the choice of key for the first key of the sequence.

Press quickly `fd` (or the 2-keys sequence of your choice) to:

- escape from all stock evil states to normal state
- escape from evil-lisp-state to normal state
- escape from evil-iedit-state to normal state
- abort evil ex command
- quit minibuffer
- abort isearch
- quit ibuffer
- quit image buffer
- quit compilation buffers
- quit magit buffers
- quit help buffers
- quit apropos buffers
- quit ert buffers
- quit undo-tree buffer
- quit paradox
- quit gist-list menu
- quit helm-ag-edit
- hide neotree buffer
- quit evil-multiedit

And more to come !

Contributions to support more buffers are _very welcome_:
**Escape Everything !**

## Install

The package is available in [MELPA][].

If you have MELPA in `package-archives`, use

    M-x package-install RET evil-escape RET

If you don't, open `evil-escape.el` in Emacs and call
`package-install-from-buffer`.

## Usage

To toggle the `evil-escape` mode globally:

    M-x evil-escape-mode

## Customization

### Key sequence

The key sequence can be customized with the variable `evil-escape-key-sequence`.
For instance to change it for `jk`:

```elisp
(setq-default evil-escape-key-sequence "jk")
```

### Delay between keys

The delay between the two key presses can be customized with the variable
`evil-escape-delay`. The default value is `0.1`. If your key sequence is
composed with the two same characters it is recommended to set the delay to
`0.2`.

```elisp
(setq-default evil-escape-delay 0.2)
```

### Unordered key sequence

The key sequence can be entered in any order by setting
the variable `evil-escape-unordered-key-sequence` to non nil.

### Excluding a major mode

A major mode can be excluded by adding it to the list
`evil-escape-excluded-major-modes`.

### Enable only for a list of major modes

An inclusive list of major modes can defined with the variable
`evil-escape-enable-only-for-major-modes`. When this list is non-nil
then evil-escape is enabled only for the major-modes in the list.

### Inhibit evil-escape

A list of zero arity functions can be defined with variable
`evil-escape-inhibit-functions`, if any of these functions return
non nil then evil-escape is inhibited.
It is also possible to inhibit evil-escape in a let binding by
setting the `evil-escape-inhibit` variable to non nil.

### Assign a key binding directly

It is possible to bind `evil-escape' function directly`, for
instance to execute evil-escape with <kbd>C-c C-g</kbd>:

```elisp
(global-set-key (kbd "C-c C-g") 'evil-escape)
```

[MELPA]: http://melpa.org/
