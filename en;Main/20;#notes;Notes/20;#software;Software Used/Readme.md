---
description: "I listed some of the software I have used for better transparency and to be more helpful."
long_title: "Software Used - Zhifeng"
---

# Software Used

## GPG(GnuPG)

I have used this software to sign my `git` `commit`s.

```bash
gpg -a --export-secret-key -o <gpg.pri.key> <id> # Seems multiple id formats can work here
gpg --import <gpg.pri.key>
gpg -K --keyid-format=long # List all the secret key ids, need to copy one key's id to git config.
```

I have met `error: gpg failed to sign the data` when trying to sign my `commit`s on my WSL Ubuntu. After viewing the `Stackoverflow` Solution, I fixed the issue by exporting an environment variable `export GPG_TTY=$(tty)`.

| Name                                        |                                                       Link                                                        | Last Accessed |
| ------------------------------------------- | :---------------------------------------------------------------------------------------------------------------: | :-----------: |
| GitHub Docs About Signing Using GPG Key     | [Link](https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key) |  y2024m11d05  |
| Stackoverflow Solution About unable to sign |              [Link](https://stackoverflow.com/questions/41052538/git-error-gpg-failed-to-sign-data)               |  y2024m11d05  |

# Setting Up VS Code Utilities

## Vscode Settings Config

Some quick utility codes for setting up Vscode for a project.

```json
// .vscode/settings.json
{
  "editor.formatOnSave": false,
  "explorer.autoReveal": false,
  "explorer.fileNesting.expand": false,
  "files.eol": "\n",
  "files.watcherExclude": {
    "**/.git/objects/**": true,
    "**/.git/subtree-cache/**": true,
    "**/.hg/store/**": true,
    "**/problems/**": true
  },
  "rust-analyzer.check.command": "clippy",
  "rust-analyzer.files.excludeDirs": ["./problems"],
  "[json]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true,
    "editor.tabSize": 2
  },
  "[rust]": {
    "editor.defaultFormatter": "rust-lang.rust-analyzer",
    "editor.formatOnSave": true,
    "editor.tabSize": 4
  }
}
```

```json
{
  "terminal.integrated.fontWeight": 100,
  "terminal.integrated.fontSize": 18,
  "workbench.colorCustomizations": {
    "terminal.background": "#000000",
    "terminal.foreground": "#ff96ecd2",
    "editor.selectionBackground": "#990099",
    "breadcrumb.activeSelectionForeground": "#ff0000",
    "tab.activeBackground": "#990099",
    "gitDecoration.ignoredResourceForeground": "#999999"
  }
}
```

## Vscode Extensions Config

Some quick utility codes for setting up VsCode extension recommendations for a project.

```json
// .vscode/extensions.json
{
  "recommendations": ["rust-lang.rust-analyzer"]
}
```

## Git Attributes Config

Some quick utility codes for setting up "Git Attributes" for a project.

```text
* text eol=lf
```

# Rust

| Name             | Link                                                                             | Description                         |
| :--------------- | :------------------------------------------------------------------------------- | :---------------------------------- |
| Rust Book        | [https://doc.rust-lang.org/stable/book/](https://doc.rust-lang.org/stable/book/) | About the Rust programming language |
| Rust Cargo Book  | [https://doc.rust-lang.org/cargo/](https://doc.rust-lang.org/cargo/)             | About Rust's package manager: Cargo |
| Rust Clippy Book | [https://doc.rust-lang.org/clippy/](https://doc.rust-lang.org/clippy/)           | About Rust's linter: Clippy         |

## Linter: Clippy

```toml
[lints.clippy]
# Warnings
#    Be careful with cloning smart pointers. Sometimes `.clone()` doesn't really clone.
clone_on_ref_ptr = "warn"
# Allows
#   I think sometimes `flag == true` is more readable.
bool_comparison = "allow"
#   I think sometimes `num.clone()` is more explicit.
clone_on_copy = "allow"
```
