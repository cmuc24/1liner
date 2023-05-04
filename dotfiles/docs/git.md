Kurzbeschreibung
-------

- new local / remote?
- syncing dotfiles?
- new SSH-Keys, GPG-Keys needed? (Auth & signing commits)

```shell script
#!/bin/bash

# Set username and email for next commands
# Configure Git
email="github@nextcos.de"
username="cmuc24"
git config --global user.email "${email}"
git config --global user.name "${username}"

# Extended config
gpgkeyid=""
git config --global user.signingkey "${gpgkeyid}"
git config --global commit.gpgsign true
git config --global core.pager /usr/bin/less
git config --global core.excludesfile ~/.gitignore

```
setup new local/remote? 
-------
### Windows
Prereq: Git-Bash or OpenSSH

- using Git-Bash [Git-Dokumentation](https://docs.github.com/de/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
- using OpenSSH [MS-Dokumentation](https://learn.microsoft.com/de-de/windows-server/administration/openssh/openssh_keymanagement)

```shell script
# - generate new SSH key
# - start ssh-agent (linux only)
# - add the key to it
# - Display the public key 
# - copy & paste to GitHub (see directlink)

ssh-keygen -t rsa -b 4096 -C "${email}"
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub
```

- add ssh key to your github profile (directlink):  
[https://github.com/settings/ssh/new](https://github.com/settings/ssh/new)

Setup Git
---------

### Installieren, welche Version?

 `git git-full gh git-scm`

### Konfiguration via Shell/CLI or Editor

- `git config`
- `git config --global`
- `~/.gitconfig`

### GitHub Docs

- [Einen neuen GPG-Schlüssel erzeugen](https://docs.github.com/de/authentication/managing-commit-signature-verification/generating-a-new-gpg-key)
- [Einen neuen SSH-Schlüssel zum GitHub-Konto hinzufügen](https://docs.github.com/de/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

### Restore

- On old system, create a backup of a GPG key
  - `gpg --list-secret-keys`
  - `gpg --export-secret-keys {{KEY_ID}} > /tmp/private.key`
- On new system, import the key:
  - `gpg --import /tmp/private.key`
- Delete the `/tmp/private.key` on both side

### Create

- `gpg --full-generate-key`

[Read GitHub documentation about generating a new GPG key for more details](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-gpg-key).
[Read GitHub documentation DE](https://docs.github.com/de/github/authenticating-to-github/generating-a-new-gpg-key).
