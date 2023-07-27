# Set Resources on Files with rcedit

## Description
This GitHub Action uses rcedit to set resources on exe or dll files.

## Usage

### Inputs

| Input | Description | Required | Default |
|-------|-------------|----------|---------|
| `directory-path` | Path to the directory containing the files. | true | - |
| `file-types` | Types of the files to be processed (comma-separated, without dots). | true | 'exe,dll' |
| `comment` | Comment to set on the files. | false | - |
| `set-icon` | Whether to set the icon of a specific file. | false | 'false' |
| `exe-file-name` | Name of the file whose icon should be set. | false | - |
| `ico-file-path` | Path to the icon file. | false | - |
| `company-name` | Company name to set on the files. | false | - |
| `file-description` | File description to set on the files. | false | - |
| `file-version` | File version to set on the files. | false | - |
| `legal-copyright` | Legal copyright to set on the files. | false | - |
| `legal-trademarks` | Legal trademarks to set on the files. | false | - |
| `product-name` | Product name to set on the files. | false | - |
| `product-version` | Product version to set on the files. | false | - |

### Example

This GitHub Action can be used as follows in your workflows:

```yaml
jobs:
  build:
    runs-on: windows-latest
    steps:
      - uses: actions/checkout@v2
      
      - name: Set resources on files with rcedit
        uses: ./ # Uses an action in the root directory
        with:
          directory-path: './dist'
          file-types: 'exe,dll'
          comment: 'My custom comment'
          set-icon: 'true'
          exe-file-name: 'myExecutable.exe'
          ico-file-path: './icon.ico'
          company-name: 'My Company'
          file-description: 'My file description'
          file-version: '1.0.0'
          legal-copyright: 'Copyright 2023'
          legal-trademarks: 'My Trademark'
          product-name: 'My Product'
          product-version: '1.0.0'
```

## Author
This Action was created by [Bioblaze Payne(Randolph William Aarseth II)](https://github.com/Bioblaze).
