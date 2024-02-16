# Smarter Country Selector

The Smarter Country Selector is designed to enhance usability in applications where users need to select countries from a dropdown menu. This project addresses common issues found in standard autocomplete country selectors by implementing advanced features and accommodating various input methods. Our prototype, developed as a side project, leverages official ISO country data updated in January 2024, including Dutch translations and alternative names. The prototype and its functionalities can be explored at [https://yannickbrouwer.nl/countries/](https://yannickbrouwer.nl/countries/), where the source code and JSON data are available for inspection.

## Features

### Input Validation

1. **Diacritic Insensitivity**: Accepts inputs with or without diacritic marks. For example, both `Réunion` and `Reunion` are recognized as valid.
2. **Flexible Formatting**: Supports inputs with dashes, spaces, or no spaces at all, leading to the correct country. For instance, `Nieuw Zeeland`, `Nieuw-Zeeland`, and `nieuwzeeland` all correctly identify as New Zealand.
3. **Multilingual Support**: Accepts Dutch and English inputs for country names, catering to users who might use English spellings in Dutch applications. Both `Germany` and `Duitsland` will lead to the same country, with suggestions shown in the currently selected language.
4. **Alternative Names**: Recognizes well-known alternative names for countries, e.g., `United Kingdom`, `England`, and `Great-Britain` all resolve to the United Kingdom.

### Sorting

Results are grouped and sorted within three categories based on the input:

1. **Two-Letter Codes**: Inputs matching a two-letter country code have top priority. For example, `FI` will prioritize Finland over Fiji.
2. **Name Start Match**: Inputs matching the start of a country's name in English or Dutch are next. Typing `Nieuw` will bring New Zealand and New Caledonia to the top.
3. **Alternative Names**: Inputs matching alternative names are considered last. For instance, `Noor` will prioritize Norway and North Macedonia, with Northern Ireland (as an alternative for the United Kingdom) ranking lower.
4. **Weight-Based Sorting**: Within these groups, countries are sorted by "weight" to reflect common usage patterns. For example, `United` is more likely to refer to the United States or United Kingdom than to the United Arab Emirates.

## Accessibility

The autocomplete functionality is fully accessible via keyboard:

- **Navigation**: Use the up and down cursor keys to change the highlighted option.
- **Selection**: Press Enter to confirm the highlighted option.
- **Exit**: Press Escape to exit the form without making a selection.

By default, the top option is highlighted upon typing. If the form is exited by clicking away or tabbing (or pressing Enter), the highlighted option is automatically selected.

## Implementation

The prototype is built using modern web technologies and can be integrated into various web projects. Detailed implementation instructions, including how to load the JSON data and incorporate the autocomplete script into your website, are available in the project's GitHub repository.

## Contributions

Contributions to the Smarter Country Selector are welcome! If you have suggestions for improvements, additional features, or language support, please feel free to submit an issue or pull request on GitHub.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
