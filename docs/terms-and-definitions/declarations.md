<sub>/ [CSS Documentation](..) / [Terms and Definitions](.) / Declarations</sub>

# Declarations

> :warning: **Note**
>
> This definition intentionally diverges from the definitions used in some W3C specifications.

For purposes of this documentation, a "Declaration" is an individual [property][properties], followed by a colon (`:`), followed by a [value][values], optionally followed by an `!important` declaration.

Multiple declarations for the same [selection][selectors] may organized into semicolon (`;`) separated groups. These groups may be called "Declarations" or "Declaration Blocks" when including the wrapping braces.

## Example

The following code example includes two declarations in a declaration block.

```text
.lorem .ipsum,
.dolor .sit {
  amet: consectetur;
  ^^^^^^^^^^^^^^^^^
  adipiscing: elit !important;
  ^^^^^^^^^^^^^^^^^^^^^^^^^^^
}
```

[properties]: properties
[selectors]: selectors
[values]: values