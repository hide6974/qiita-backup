MacOS M1 Github構築で、
ちょこちょこ詰まったとこを中心にメモります。

## 実現すること
- Mac　Visualstudioでレポジトリ作成しソースコミットできること。


## 動作環境について

- macOS Big Sur 
- Visualstudio for Mac

１．先人のちからで、実施する。
　初心者がGithubをはじめてみる【Mac】 (´･ω･`)
　https://qiita.com/Shobon/items/8c6cda5a2bcbf2525c6e
２．エラーが出たためメールと、usernameを入力。
３．お終い。


```terminal:terminal
git push origin master
↓エラーメッセージ
error: src refspec master does not match any
error: failed to push some refs to 'https://github.com/hide6974/new.git'
```

原因は途中コマンドで聞かれたメールとusernameを登録していないため

```terminal:terminal
git commit -m "first" 

*** Please tell me who you are.

Run

  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"

to set your account's default identity.
Omit --global to set the identity only in this repository.
```
解消。

### 以上（執筆15分）
