# Autocompletion

Since the main `docker` formula in Homebrew now automatically installs the correct shell completions when you install or upgrade Docker, you can safely remove the old, deprecated package.

Run the following command in your terminal:

```bash
brew uninstall docker-completion
```

### Will I lose my tab auto-complete?

**No.** As long as you have the main `docker` package installed via Homebrew (or Docker Desktop), your auto-completions will continue to work. The native completions are now automatically placed in Homebrew's standard completion directories (like `$(brew --prefix)/share/zsh/site-functions` for Zsh) whenever Docker is updated.

If you uninstall it and find your completions stop working in a new terminal window, you can manually generate them using Docker's built-in command:

* **For Zsh:** `docker completion zsh > $(brew --prefix)/share/zsh/site-functions/_docker`
* **For Bash:** `docker completion bash > $(brew --prefix)/etc/bash_completion.d/docker`

*(Note: You usually do not need to run these manual commands, as Homebrew handles this during the standard `brew install docker` or `brew upgrade docker` process).*

### Autocompletion still not working
This usually means one of two things: either Zsh isn't configured to look in Homebrew's custom directory for completion files, or your Zsh completion cache is stale and needs to be reset.

Here is how to get it working.

### 1. Ensure Zsh is reading Homebrew's folder

For Zsh to know about the `_docker` file you just created, Homebrew's `site-functions` directory must be added to Zsh's `$fpath` **before** the completion system is initialized.

Open your `~/.zshrc` file in a text editor (like `nano ~/.zshrc`) and look for the line that says `autoload -Uz compinit`. Make sure the Homebrew path is added *above* it.

Add this block to your `~/.zshrc` if it isn't there already:

```zsh
# Add Homebrew's site-functions to the Zsh fpath
if type brew &>/dev/null; then
  FPATH="$(brew --prefix)/share/zsh/site-functions:${FPATH}"
fi

# Initialize the completion system
autoload -Uz compinit
compinit

```

Save the file and exit.

### 2. Clear your Zsh completion cache

Zsh heavily caches its auto-completions to load faster. When you manually add a new file like `_docker`, Zsh often ignores it until the cache is destroyed and rebuilt.

Run these commands in your terminal:

```bash
# Delete the hidden zcompdump cache files
rm -f ~/.zcompdump*

# Reload your shell to rebuild the cache
exec zsh

```

Try typing `docker r` and hitting **Tab** again. It should now successfully suggest commands like `rm`, `rmi`, `run`, etc.

---

> **Note for Oh My Zsh users:** If you are using the Oh My Zsh framework, it manages completions slightly differently. You can bypass the manual file generation entirely by simply opening your `~/.zshrc`, finding the `plugins=(...)` line, and adding `docker` to the list of plugins (e.g., `plugins=(git docker)`). Then, run `source ~/.zshrc`.