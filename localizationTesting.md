# Localization: Implementation and Testing... Locally

by Isabela Moreira

## What's localization?

Adapting a product to meet language and cultural requirements

- Numeric, date, time formats
- Currency, measurements
- Keyboard usage
- ...basically everything your user sees

## Localization vs. internationalization

Internationalization makes it easy to provide a localized product by removing barriers to localization.

- No hardcoded strings!
- Support for RTL and LTR

## Why is localization important?

Expanding your user base!

- 25.2% of Internet users worldwide speak English
- 76.3% of users across 10 languages

## Localization Goals

- Single source of truth
- Handle an arbitrary number of languages
- Require minimal to no dev effort to add new languages
- Decoupled implementation
- Automated as much as possible

## Localizing a React and vanilla JS app

`react-intl-universal` is better than `react-intl` — uses a JSON file an doesn't require wrapping components in an HOC.

ICU MessageFormat: Message written and translated as a single unit

## Testing localization

**Pseudo-localization**: strategy for using a local file to force a bunch of latin characters to be used, useful for seeing strings that haven't been localized.

```
npm install pseudo-localization
```

Use `intl.get('MY_STRING')` in your automated testing to make sure you're not looking for hard-coded strings!

## Wrap Up

- Hard-coded strings are bad!
- Translate messages as a single unit (minimize string variables and don't concatenate strings)
- Use `react-intl-universal` and `pseudo-localization`
- Don't DIY localization
