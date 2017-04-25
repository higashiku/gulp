# [Node.js] macOS にインストール

- Node.js のバージョンも管理したい
  - すでに Node.js がインストールされている ... 2 → 3
  - Node.js はインストールされていない ... 3

- 取り急ぎ Node.js をインストールできればよい（バージョン管理は不要）
  - すでに nodebrew がインストールされている ... 4 → 1
  - nodebrew はインストールされていない ... 1

## 1. 通常のインストール

公式サイトより任意のバージョンをダウンロードしてインストール

- https://nodejs.org/ja/

## 2. アンインストール

### npm のアンインストール

```
$ sudo npm uninstall npm -g
```

### Node.js をアンインストール

node_modules がどこにあるか確認
```
$ npm root -g
/usr/local/lib/node_modules
```

org.nodejs.node.pkg.bom に記載されているファイルをすべて削除（パスに注意）
```
$ lsbom -f -l -s -pf /var/db/receipts/org.nodejs.node.pkg.bom | while read i; do sudo rm /usr/local/${i}; done
```

### その他関連ファイルを削除
```
$ sudo rm -rf /usr/local/lib/node /usr/local/lib/node_modules /var/db/receipts/org.nodejs.*
$ sudo rm -rf ~/.npm
```

### アンインストールできたか確認
```
$ node -v
$ npm -v
```

## 3. nodebrew で Node.js を導入しバージョン管理する

nodebrew のインストール

- https://github.com/hokaccha/nodebrew

nodebrew をインストールする
```
$ curl -L git.io/nodebrew | perl - setup
```

nodebrew のパスを通し、.bash_profile を再読み込みする
```
$ echo 'export PATH=$HOME/.nodebrew/current/bin:$PATH' >> ~/.bash_profile
$ source ~/.bash_profile
```

nodebrew が正常にインストールされたか確認（バージョンを
表示
表示）


```
$ nodebrew -v
$ node -v // -bash: node: command not found
$ nodebrew install-binary v6.3.0 // nodebrew install v6.3.0 だと遅い
$ nodebrew use v6.3.0
$ node -v // v6.3.0
```

インストール済みの Node.js 一覧
```
$ nodebrew ls
```

利用可能な Node.js 一覧
```
$ nodebrew ls-remote
```

任意のバージョンの Node.js をインストール
```
$ nodebrew install v6.3.0
$ nodebrew ls
```

利用する Node.js のバージョンを変更
```
$ nodebrew use v6.3.0
$ node -v
```

不要なバージョンの Node.js を削除
```
$ nodebrew uninstall v6.3.0
```

## 4. nodebrew をアンインストール
```
$ rm -rf ~/.nodebrew
$ nodebrew -v
```
