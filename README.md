# My Dotfiles

This repository contains my personal dotfiles managed with [chezmoi](https://www.chezmoi.io/).

## Files Included

- **Shell Configuration**: `.zshrc`, `.zprofile`, `.p10k.zsh`
- **Git Configuration**: `.gitconfig`
- **FZF Configuration**: `.fzf.zsh`
- **System Tools**: `.config/htop/htoprc`

## Installation

### Prerequisites

1. Install chezmoi:
   ```bash
   # On macOS
   brew install chezmoi
   
   # On Linux
   sh -c "$(curl -fsLS get.chezmoi.io)"
   ```

### Setup on a new machine

1. Initialize chezmoi with this repository:
   ```bash
   chezmoi init https://github.com/justinwallis/dotfiles.git
   ```

2. Preview what changes will be made:
   ```bash
   chezmoi diff
   ```

3. Apply the dotfiles:
   ```bash
   chezmoi apply
   ```

## Updating

### Adding new files

```bash
# Add a new dotfile to chezmoi
chezmoi add ~/.newconfig

# Commit and push changes
chezmoi cd
git add .
git commit -m "Add new config file"
git push
```

### Syncing changes

```bash
# Pull and apply changes from the repository
chezmoi update

# Or manually:
chezmoi cd
git pull
chezmoi apply
```

### Updating existing files

```bash
# After modifying a file that's already managed by chezmoi
chezmoi re-add ~/.zshrc  # for example

# Commit and push
chezmoi cd
git add .
git commit -m "Update zsh configuration"
git push
```

## Useful Commands

- `chezmoi managed` - List all files managed by chezmoi
- `chezmoi status` - Show the status of files
- `chezmoi diff` - Preview changes before applying
- `chezmoi edit ~/.zshrc` - Edit a managed file
- `chezmoi cd` - Go to the chezmoi source directory

For more information, see the [chezmoi documentation](https://www.chezmoi.io/docs/).

