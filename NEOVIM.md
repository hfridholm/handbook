# Neovim

# Install
[neovim](https://github.com/neovim/neovim/wiki/Building-Neovim)

**Step 1:** Install build prerequisites
```bash
sudo apt-get update
```
```bash
sudo apt-get install ninja-build gettext cmake unzip curl
```

**Step 2:** Move to home directory and clone repo
```bash
cd ~ && git clone https://github.com/neovim/neovim
```

** Step 3:** Move into repo and checkout the stabe version of neovim
```bash
cd neovim && git checkout stable
```

** Step 4:** build neovim
```bash
make CMAKE_BUILD_TYPE=RelWithDebInfo
```

** Step 5:** install neovim from build
```bash
cd build && cpack -G DEB && sudo dpkg -i nvim-linux64.deb
```

## Plugins

#### Nvim Tree
[nvim-tree.lua](https://github.com/nvim-tree/nvim-tree.lua)

#### Lualine
[lualine.nvim](https://github.com/nvim-lualine/lualine.nvim)

#### Treesitter
[nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter)

#### Telescope
[telescope.nvim](https://github.com/nvim-telescope/telescope.nvim)

Install ripgrep to search in files

[ripgrep](https://github.com/BurntSushi/ripgrep)

```bash
sudo apt-get update && sudo apt-get install ripgrep
```