# GitHub を使って開発を進めることができる

## 1. リモートリポジトリ

GitHub 上に新規リポジトリを作成してください。

## 2. プッシュ

ローカルの PC 上に GitHub 上で作成したリポジトリの同じ名前のディレクトリを作成し、そのディレクトリ内に README.md　ファイルを作成してください。

```shell
$ mkdir git_practice
$ cd git_practice
$ touch README.md
```

次に、ローカルリポジトリを新規作成し、変更をステージに追加、コミットしてください。
```shell
$ git init
$ git add README.md
git commit -m "first commit"
```

リモートリポジトリを登録してください。そして GitHub に変更をプッシュしてください。
```shell
$ git remote add origin https://github.com/makoto00000/git_practice.git
```

## 3. 追加の変更をプッシュ

README.md に変更を追加してください。そしてその変更を GitHub にプッシュしてください。
```shell
$ git push origin main
```

## 4. クローン

GitHub 上にある他者が作成したリポジトリを自分の PC 上にクローンしてください。クローン対象は何でも良いです。
```shell
$ git clone [リポジトリパス]
（-bオプションで特定のブランチをクローンできる）
```