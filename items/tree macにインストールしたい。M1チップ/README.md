tree mac エラー　homebrewからインストールしたいがエラーとなる
以下で解決した。



```mac:terminal
tree mac

zsh: command not found: tree
hide@hidenoMacBook-Air demoapp_v1 % brew install tree
Updating Homebrew...
error: Not a valid ref: refs/remotes/origin/master
fatal: ambiguous argument 'refs/remotes/origin/master': unknown revision or path not in the working tree.
Use '--' to separate paths from revisions, like this:
'git <command> [<revision>...] -- [<file>...]'

```

not install

```mac:terminal
tree mac

hide@hidenoMacBook-Air ~ % brew install tree  
Updating Homebrew...
fatal: Could not resolve HEAD to a revision
==> Searching for similarly named formulae...
Error: No similarly named formulae found.
Error: No available formula or cask with the name "tree".
==> Searching for a previously deleted formula (in the last month)...
Error: No previously deleted formula found.
==> Searching taps on GitHub...
Error: No formulae found in taps.
hide@hidenoMacBook-Air ~ % brew doctor
```

解決はロゼッタモードのterminalでのインストールでOKだった





