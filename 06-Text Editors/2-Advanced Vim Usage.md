# Advanced Vim Usage

Once you're comfortable with the basics of Vim, it's time to explore its more advanced features. These capabilities can help you maximize productivity, automate repetitive tasks, and manage large projects more efficiently.

## Custom Key Mappings

Vim allows you to create custom key mappings, which can be added to your `.vimrc` file. This helps streamline your workflow by assigning shortcuts to frequently used commands.

### Creating Key Mappings

- **Normal Mode Mapping**: Use `nnoremap` for custom mappings in Normal Mode.
  
    ```vim
    nnoremap <leader>w :w<CR>
    ```
  
    This maps `<leader>w` (commonly `\w`) to save the file.

- **Insert Mode Mapping**: Use `inoremap` for Insert Mode mappings.
  
    ```vim
    inoremap jj <Esc>
    ```
  
    This maps `jj` to exit Insert Mode, which can be quicker than reaching for the `Esc` key.

- **Visual Mode Mapping**: Use `vnoremap` for Visual Mode mappings.
  
    ```vim
    vnoremap <leader>y "+y
    ```
  
    This maps `<leader>y` to yank (copy) text to the system clipboard.

### Leader Key

The `<leader>` key is a customizable prefix key that you can set in your `.vimrc`. It's commonly used to create shortcuts.

```vim
let mapleader = ","
```
