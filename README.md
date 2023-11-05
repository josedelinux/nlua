# nlua

Lua script that let's you use Neovim as a Lua interpreter.

Neovim embeds a Lua interpreter, but it doesn't expose the same command line interface as plain `lua`.

The plain interface looks like this:

```
usage: lua [options] [script [args]]
Available options are:
  -e stat   execute string 'stat'
  -i        enter interactive mode after executing 'script'
  -l mod    require library 'mod' into global 'mod'
  -l g=mod  require library 'mod' into global 'g'
  -v        show version information
  -E        ignore environment variables
  -W        turn warnings on
  --        stop handling options
  -         stop handling options and execute stdin
```


`nlua` is a script which emulates that interface, Using Neovim's `-l` option under the hood.

Currently supported:

- `-e`
- `-v`
- `--`
- `[script [args]]`
- stdin handling


## Motivation

- It let's you use Neovim as Lua interpreter for [luarocks]. This in turn allows you to run tools like [busted] to test Neovim plugins.

- It allows tools like [local-lua-debugger-vscode] to use the Neovim Lua. Enabling debugging of busted test cases for Neovim plugins.

See:

- [Using Neovim as Lua interpreter with Luarocks](https://zignar.net/2023/01/21/using-luarocks-as-lua-interpreter-with-luarocks/)
- [Debugging Lua in Neovim](https://zignar.net/2023/06/10/debugging-lua-in-neovim/)


## Requirements

- `env` executable supporting the `-S` option. Run `env --help` in a shell to verify.
- Neovim 0.9+ with LuaJIT

## Installation

For [luarocks] support, copy or symlink `nlua` to `/usr/bin/`
If you don't need [luarocks] support, copy it into any folder in your `$PATH`.


## Luarocks setup

TODO

[luarocks]: https://luarocks.org/
[busted]: https://lunarmodules.github.io/busted/
[local-lua-debugger-vscode]: https://github.com/tomblind/local-lua-debugger-vscode