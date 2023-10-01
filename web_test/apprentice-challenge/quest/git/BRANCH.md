# ブランチを利用して開発を進めることができる

Git で管理されているディレクトリに移動してください。

## 1. ブランチの新規作成

feature という名前のブランチを新規作成してください。

```shell
$ git branch feature
```

## 2. ブランチの切り替え

ローカルリポジトリのブランチを feature ブランチに切り替えてください。
```shell
$ git checkout feature
（-bオプションを付けるとブランチの作成とチェックアウトをまとめて行うことができる。）
```
git 2.23.0以降はgit switch
```shell
$ git switch feature
（-cオプションでブランチの作成と切り替えを同時に）
```
ブランチの一覧を確認する場合
```shell
$ git branch
* feature
  main
（*は現在のブランチを示す）
（-aオプションでリモートリポジトリも確認できる）
```

## 3. マージ

feature ブランチでファイルの変更を行い、コミットしてください。そしてローカルリポジトリのブランチを main ブランチに切り替えてください。
```shell
$ git commit -am "change README.md"
$ git checkout main
（-aオプションでaddとcommitを同時にできる）
```

次に、feature ブランチの変更を main ブランチに取り込んでください。なお、他のブランチの変更を取り込むことをマージと言います。
```shell
$ git merge feature
```

## 4. ブランチの名前の変更

feature ブランチの名前を rename という名前に変更してください。
```shell
$ git branch -m feature rename
```

## 5. ブランチの削除

rename ブランチを削除してください。
```shell
$ git branch -d rename
```
