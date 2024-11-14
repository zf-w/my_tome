---
description: "I listed some of the software I have used for better transparency and to be more helpful."
long_title: "Software Used - Zhifeng"
---

# Software Used

## GPG(GnuPG)

I have used this software to sign my `git` `commit`s.

```bash
gpg -a --export-secret-key -o gpg.pri.key <id> # Seems multiple id formats can work here
gpg --import gpg.pri.key
gpg -K --keyid-format=long # List all the secret key ids, need to copy one key's id to git config.
```

I have met `error: gpg failed to sign the data` when trying to sign my `commit`s on my WSL Ubuntu. After viewing the `Stackoverflow` Solution, I fixed the issue by exporting an environment variable `export GPG_TTY=$(tty)`.

| Name                                        |                                                       Link                                                        | Last Accessed |
| ------------------------------------------- | :---------------------------------------------------------------------------------------------------------------: | :-----------: |
| GitHub Docs About Signing Using GPG Key     | [Link](https://docs.github.com/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key) |  y2024m11d05  |
| Stackoverflow Solution About unable to sign |              [Link](https://stackoverflow.com/questions/41052538/git-error-gpg-failed-to-sign-data)               |  y2024m11d05  |
