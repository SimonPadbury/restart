## CHANGELOG

## 2 Nov 2024 -- v.1.2

* The stylesheet now has `html { color-scheme: light dark; }`. So you don’t need the meta-tag in the HTML `<meta name="color-scheme" content="light dark">`.
* Simplified the focus ring (using `outline` again), because all evergreen browsers now do a better job, rounding around rounded inputs and buttons.
* Default font sizes changed to EMs equivalent of 18px, 20px, 24px, 30px, 36px, 48px.
* Setting margin bottom on typographic block elements to 1rem (not using a variable).
* Colors for butttons, inputs, and line details are now controlled by the new CSS function, `light-dark()`.
* `font-family: inherit` on form elements.

## 22 May 2024 -- v.1.1

* Changed line height `--lh` thoughout to `calc(1em + 0.5rem)`.
* Using this `--lh` for margin-bottom of typographic block elements.
* Removed margin-bottom of nested (child) lists.  

## 15 May 2024 -- v.1.0

* Initial launch.