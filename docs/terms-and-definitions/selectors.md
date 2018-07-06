<sub>/ [CSS Documentation](..) / [Terms and Definitions](.) / Selectors</sub>

# Selectors

> :warning: **Note**
>
> This definition intentionally diverges from the definitions used in some W3C specifications.

For purposes of this documentation, a "Selector" is a sequence of one or more "simple selectors" (types, attributes, classes, IDs, pseudo-classes, or pseudo-elements) which may be separated by "combinators" (whitespace, `>`, `+`, or `~`).

Groups of selectors may be organized into comma (`,`) separated groups. These groups may be called "Selectors" or "Selections".

## Example

The following code example includes two selectors in a selection.

```text
.lorem .ipsum,
^^^^^^^^^^^^^
.dolor .sit {
^^^^^^^^^^^
  amet: consectetur;
  adipiscing: elit !important;
}
```