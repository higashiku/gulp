# [Node.js] Windows にインストール

- Node.js のバージョンも管理したい
  - すでに Node.js がインストールされている ... 2 → 3
  - Node.js はインストールされていない ... 3

- Node.js の単一バージョンをインストールできればよい（バージョン管理は不要）
  - すでに nodist がインストールされている ... 4 → 1
  - nodist はインストールされていない ... 1

## 1. 通常のインストール

公式サイトより任意のバージョンをダウンロードしてインストール

- https://nodejs.org/ja/

## 2. アンインストール

アンインストーラを使い、アンインストール

- スタート > すべてのプログラム > Node.js > Uninstall Node.js

## 3. nodist で Node.js を導入しバージョン管理する

nodistのページからインストーラーをダウンロードして、nodistをインストール

- https://github.com/marcelklehr/nodist
- https://github.com/marcelklehr/nodist/releases （ダウンロードページ）

nodist が正常にインストールされているか確認（バージョンを表示してみる）
```
> nodist -v
```

Node.js もインストールされているか確認（バージョンを表示してみる）
```
> node -v
```

インストール済みの Node.js 一覧
```
> nodist ls
> 7.2.1 (global: v7.2.1)
```

nodist のアップデート
```
> nodist update
```

利用可能な Node.js 一覧
```
> nodist dist
nodev0.1.14
nodev0.1.15
nodev0.1.16
...（たくさん表示される）
```

任意のバージョンの Node.js をインストール
```
> nodist add v6.3.0
> nodist ls
> 6.3.0 (global: v6.3.0)
  7.2.1
```

利用する Node.js のバージョンを変更
```
> nodist use v6.3.0
> node -v
v6.3.0
```

不要なバージョンの Node.js を削除
```
> nodist rm v7.2.1
```

## 4. nodist をアンインストール

アンインストーラを使い、アンインストール

- C:\Program Files (x86)\Nodist\uninstall.exe

