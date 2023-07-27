# Set Resources on Files with rcedit

This GitHub Action uses rcedit to set resources on executable files.

## Inputs

### `directory-path`

**Required** The path to the directory containing the executable files.

### `comment`

The comment to set on the executable files. If not provided, no comment will be set.

### `set-icon`

Flag indicating whether to set the icon of a specific executable file. Defaults to `false`.

### `exe-file-name`

The name of the executable file whose icon should be set. This input is used only if `set-icon` is `true`.

### `ico-file-path`

The path to the icon file. This input is used only if `set-icon` is `true`.

### `company-name`

The company name to set on the executable files. If not provided, no company name will be set.

### `file-description`

The file description to set on the executable files. If not provided, no file description will be set.

### `file-version`

The file version to set on the executable files. If not provided, no file version will be set.

### `legal-copyright`

The legal copyright to set on the executable files. If not provided, no legal copyright will be set.

### `legal-trademarks`

The legal trademarks to set on the executable files. If not provided, no legal trademarks will be set.

### `product-name`

The product name to set on the executable files. If not provided, no product name will be set.

### `product-version`

The product version to set on the executable files. If not provided, no product version will be set.

## Usage

Here's an example of how you might use this action in your workflow:

```yaml
name: Set Resources

on:
  push:
    branches: [ main ]

jobs:
  set-resources:
    runs-on: windows-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Set resources with rcedit
        uses: Bioblaze/rcedit-action@v1a
        with:
          directory-path: './path/to/exe/files'
          comment: 'This is a comment'
          set-icon: 'true'
          exe-file-name: 'my-executable.exe'
          ico-file-path: './path/to/icon.ico'
          company-name: 'My Company'
          file-description: 'This is a file description'
          file-version: '1.0.0'
          legal-copyright: '2023 My Company'
          legal-trademarks: 'My Company Trademark'
          product-name: 'My Product'
          product-version: '1.0.0'
```

## Author

Bioblaze Payne
Randolph William Aarseth II