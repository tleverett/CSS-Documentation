<sub>/ [CSS Documentation](..) / [Terms and Definitions](.) / Values</sub>

# Values

For purposes of this documentation, a "Value" is the text between the colon (`:`) and semicolon (`;`) in a [declaration][declarations], ignoring any `!important` declarations, as well as leading or trailing whitespace.

## Example

The following code example includes two values.

```text
.lorem .ipsum,
.dolor .sit {
  amet: consectetur;
        ^^^^^^^^^^^
  adipiscing: elit !important;
              ^^^^
}
```

[declarations]: declarations