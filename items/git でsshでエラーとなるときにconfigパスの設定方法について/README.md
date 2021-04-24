```mac:terminal
ssh -T git@github.com

git@github.com: Permission denied (publickey).
```

ssh-add していないとのこと。

```mac:terminal
ssh -T git@github.com

git@github.com: Permission denied (publickey).
```

鍵しても、ssh-addを忘れていると上記エラーが出ることがあります。
まずは「ssh-add -l」して状態を確認。
読み込んでほしい秘密鍵のパスがちゃんと出てこればOKです。
出てこなければ、ssh-addする。

eval `ssh-agent`
ssh-add ~/.ssh/id_rsa


それでもだめなら

```mac:terminal
cat config
```

以下追加

```mac:terminal
cat config
Host github
  HostName github.com
  IdentityFile ~/.ssh/id_rsa_github #→ここの宛先を変更する
  User git
```

以上
