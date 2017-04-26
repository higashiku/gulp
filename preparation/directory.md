# ディレクトリ構成

## はじめに

今回は参考として以下のようなディレクトリ構成で進めます。
  ディレクトリ構成はプロジェクトに合わせて検討してください。

```
lesson
   │ ＜開発用ディレクトリ＞
   ├ dev
   │    │ ＜.sass ディレクトリ＞
   │    └ sass
   │       └ style.sass
   │
   │ ＜納品ファイル用ディレクトリ＞
   ├ html
   │    │ ＜.css ディレクトリ(自動生成されるもの)＞
   │    ├ css
   │    │  └ style.css
   │    │
   │    └ index.html
   │
   └ 上記以外でgulpが必要とするファイル
```

## ディレクトリの作成（Windows）

デスクトップに移動（Windows）
```
> cd Desktop
```

デスクトップ上に練習用のディレクトリを作成し、移動します
```
$ cd lesson
$ mkdir lesson
```

作業に使うディレクトリを作成します
```
$ mkdir lesson\dev
$ mkdir lesson\dev\sass
$ mkdir lesson\html
```


## ディレクトリの作成（macOS）

デスクトップに移動
```
$ cd ~/Desktop
```

デスクトップ上に練習用のディレクトリを作成し、移動します
```
$ mkdir lesson
$ cd lesson
```

作業に使うディレクトリを作成します
```
$ mkdir lesson/dev
$ mkdir lesson/dev/sass
$ mkdir lesson/html
```







