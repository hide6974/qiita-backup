Heroku mac M1で設定中に

```mac:terminal
heroku config:set RAILS_MASTER_KEY=<master key>

zsh: parse error near `\n'

```

↓解決 api/config/のmaster.keyをXXXXXXXX貼り付けること

```mac:terminal
heroku config:set RAILS_MASTER_KEY=XXXXXXXX

```
以上
