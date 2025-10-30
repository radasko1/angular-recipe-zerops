# Prettier Configuration Guide

> **Official Documentation:** https://prettier.io/docs/en/  
> **Configuration Options:** https://prettier.io/docs/en/options.html  
> **CLI Reference:** https://prettier.io/docs/en/cli.html

## Core Formatting Options

**printWidth: 100**  
Maximum line length before wrapping. Set to 100 characters for better readability on modern screens.

**tabWidth: 2**  
Number of spaces per indentation level. Industry standard for JavaScript/TypeScript projects.

**useTabs: false**  
Use spaces instead of tabs for indentation. Ensures consistent formatting across all editors.

## Quote Settings

**semi: true**  
Add semicolons at the end of statements. Reduces ASI (Automatic Semicolon Insertion) issues.

**singleQuote: true**  
Use single quotes instead of double quotes for strings. Common convention in JavaScript.

**quoteProps: "as-needed"**  
Only add quotes around object properties when required. Keeps code cleaner.

**jsxSingleQuote: false**  
Use double quotes in JSX attributes. Follows HTML/XML conventions.

## Structure & Spacing

**trailingComma: "es5"**  
Add trailing commas where valid in ES5 (objects, arrays). Makes git diffs cleaner.

**bracketSpacing: true**  
Add spaces inside object literal braces: `{ foo: bar }` instead of `{foo: bar}`.

**bracketSameLine: false**  
Put closing bracket on new line in HTML/JSX. Improves readability for nested elements.

**arrowParens: "always"**  
Always include parentheses around arrow function parameters: `(x) => x` instead of `x => x`.

## Whitespace & Line Endings

**proseWrap: "preserve"**  
Maintain original line wrapping in markdown/prose. Useful for documentation files.

**htmlWhitespaceSensitivity: "css"**  
Respect CSS display property for HTML whitespace. Balances formatting with layout integrity.

**endOfLine: "lf"**  
Use Unix-style line endings (LF). Prevents cross-platform git issues.

## Advanced Options

**embeddedLanguageFormatting: "auto"**  
Format embedded code (CSS in JS, SQL in templates) automatically when identifiable.

**singleAttributePerLine: false**  
Allow multiple HTML/JSX attributes on same line. More compact for simple elements.

---

## Installation

> **Install Guide:** https://prettier.io/docs/en/install.html

```bash
npm install --save-dev prettier
# or
yarn add --dev prettier
```

## Command Line Usage

**Format a single file:**

```bash
npx prettier --write src/index.js
```

**Format all files in a directory:**

```bash
npx prettier --write "src/**/*.{js,jsx,ts,tsx,json,css,md}"
```

**Check formatting without modifying files:**

```bash
npx prettier --check "src/**/*.{js,jsx,ts,tsx}"
```

**Format all files in project:**

```bash
npx prettier --write .
```

**Common flags:**

- `--write` - Edit files in place
- `--check` - Check if files are formatted (useful for CI)
- `--list-different` - List files that differ from Prettier formatting
- `--ignore-path` - Specify path to ignore file (default: .prettierignore)

## Package.json Scripts Setup

Add these scripts to your `package.json`:

```json
{
  "scripts": {
    "format": "prettier --write .",
    "format:check": "prettier --check .",
    "format:staged": "prettier --write"
  },
  "devDependencies": {
    "prettier": "^3.0.0"
  }
}
```

**Usage:**

- `npm run format` - Format all files in the project
- `npm run format:check` - Check if all files are formatted (CI/CD)
- `npm run format:staged` - Use with lint-staged for pre-commit hooks

## Pre-commit Hook Setup (Optional)

> **Pre-commit Hook Guide:** https://prettier.io/docs/en/precommit.html  
> **Git Hooks Integration:** https://prettier.io/docs/en/install.html#git-hooks

Install husky and lint-staged:

```bash
npm install --save-dev husky lint-staged
npx husky init
```

Add to `package.json`:

```json
{
  "lint-staged": {
    "*.{js,jsx,ts,tsx,json,css,md}": "prettier --write"
  }
}
```

Create `.husky/pre-commit`:

```bash
npx lint-staged
```

---

## Additional Resources

- **Ignoring Code:** https://prettier.io/docs/en/ignore.html
- **Editor Integration:** https://prettier.io/docs/en/editors.html
- **Configuration File:** https://prettier.io/docs/en/configuration.html
- **API Reference:** https://prettier.io/docs/en/api.html
- **Comparison with Linters:** https://prettier.io/docs/en/comparison.html
