# Hugo, Go, DartSASS

## Summary

Dev Container for building Hugo sites with the added Go and DartSASS dependencies.

|          Metadata           |                    Value                         |
| --------------------------- | ------------------------------------------------ |
| *Contributors*              | [Michael A Williamson](https://github.com/mawcs) |
| *Categories*                | Frameworks                                       |
| *Definition type*           | Dockerfile                                       |
| *Works in Codespaces*       | Untested                                         |
| *Container host OS support* | Windows, not tested in Linux or macOS            |
| *Container OS*              | Debian                                           |
| *Languages, platforms*      | Hugo, Go, DartSASS                               |

Includes Hugo, Go, and DartSASS. Also includes the "Go", "Even Better TOML", and "markdownlint" VS Code extensions.

The arguments include VARIANT, but switching to plain "hugo" will break the DartSASS integration.

The VERSION argument changes which version of Hugo to use with "latest" as the default.
