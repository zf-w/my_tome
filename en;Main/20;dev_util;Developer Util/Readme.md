---
description: "Tools I have used, and documentations about how to set up them."
long_title: "Developer Configs - Zhifeng"
---

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
