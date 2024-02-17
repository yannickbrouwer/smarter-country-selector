# Smarter Country Selector
Many websites let users select a country from a large dropdown, [which is bad for UX](https://baymard.com/blog/drop-down-usability). Recently I encountered several issues while usability testing an autocomplete country selector. I created this prototype to address most of the issues I encountered.

It builds upon the work that [Jamie Holst](https://www.smashingmagazine.com/2011/11/redesigning-the-country-selector/) and [Adam Silver](https://adamsilver.io/blog/building-an-accessible-autocomplete-control/) have done.
 
The country data is based on the ISO 3166 list and was last updated in January 2024.

## Demo
A demo can be found at: [https://www.yannickbrouwer.nl/countries](https://www.yannickbrouwer.nl/countries)

## Features

### Input Validation

1. **Multilingual Support**: Accepts Dutch and English inputs for country names, catering to users who might use English spellings in Dutch applications. Both `Germany` and `Duitsland` will lead to the same country, with suggestions shown in the currently selected language. You could for example also create a version where users can input the name of a country in it's native language.
2. **Diacritic Insensitivity**: Accepts inputs with or without diacritic marks. For example, both `Réunion` and `Reunion` are recognized as valid.
3. **Flexible Formatting**: Supports inputs with dashes, spaces, or no spaces at all, leading to the correct country. For instance in Dutch, `Nieuw-Zeeland` is correct but `Nieuw Zeeland` and `nieuwzeeland` all correctly identify as New Zealand.
4. **Alternative Names**: Recognizes well-known alternative names for countries, e.g., `United Kingdom`, `England`, `Great Britain` and  `Northern Ireland` all resolve to the United Kingdom.

### Sorting

Results are grouped and sorted within three categories based on the input:

1. **Two-Letter Codes**: Inputs matching a two-letter country code have top priority. For example, `FI` will prioritize Finland over Fiji.
2. **Name Start Match**: Inputs matching the start of a country's name in English or Dutch are next. Typing `New` will bring New Zealand and New Caledonia to the top.
3. **Alternative Names**: Inputs matching alternative names are considered last. For instance, `Nor` will prioritize Norway and North Macedonia, with Northern Ireland (as an alternative for the United Kingdom) ranking lower.
4. **Weight-Based Sorting**: Within these groups, countries are sorted by "weight" to reflect common usage patterns. For example, `United` in my context is more likely to refer to the United States or United Kingdom than to the United Arab Emirates.

## Accessibility

The autocomplete functionality is fully accessible via keyboard:

- **Navigation**: Use the up and down cursor keys to change the highlighted option.
- **Selection**: Press Enter or Tab to confirm the highlighted option.
- **Exit**: Press Escape to exit the form without making a selection.

By default, the top option is highlighted upon typing. If the form is exited by clicking away, tabbing or pressing Enter, the highlighted option is automatically selected.

## Implementation

The prototype is built using HTML, CSS and Javascript. I'm a designer by trade so my code is a bit messy. If you have suggestions for improvements feel free to submit an issue or pull request on GitHub.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
