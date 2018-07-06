<sub>/ [CSS Documentation](..) / [Terms and Definitions](.) / Specificity</sub>

# Specificity

Specificity is a formal measure of a [selector's][selectors] priority when determining which [rules][rules] to apply to a given element.

The detailed rules for calculating specificity can be found in the [selectors specification][slectors-spec].

## Quick Reference

A simple heuristic approach to calculating a selector's specificity is to break the selector into its composite parts and add up their values:

 * IDs have a value of 100
 * Classes, attributes, and pseudo-classes\* have a value of 10
 * Elements and pseudo-elements have a value of 1
 * The universal selector and `:not` have a value of 0

<sub>\* With the exception of `:not`</sub>

 * For declarations with the `!important` flag, add 1000 to the value of their selector
 * Declarations within the `style` attribute are treated as though they have a specificity of 1000

The selector with the highest specificity is given priority. If multiple selectors have the same specificity, the later selectors take priority.

> :warning: **Note**
> 
> While this approach may work in most situations, be sure to reference the actual specification when debugging issues like "Why isn't my selector being applied?" as there are a variety of nuanced details that are not covered by this naive approach.

[rules]: rules
[selectors]: selectors
[selectors-spec]: https://www.w3.org/TR/selectors-3/#specificity