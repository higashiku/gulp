# package.json を生成

以下のコマンドで package.json を生成します
```
$ npm init
```

対話形式でプロジェクトの情報を記入します
```
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help json` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg> --save` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
name: (sample) 
```

以下の項目を設定します（Enter キーでとばしてもOK）
```
name: (sample) 
version: (1.0.0) 
description: 
entry point: (index.js) 
test command: 
git repository: 
keywords: 
author: 
license: (ISC) 
About to write to /Users/suekun/Desktop/sample/package.json:
```

この内容で package.json を生成しても良いか確認されますので、Enter キーで確定します
```
{
  "name": "sample",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC"
}

Is this ok? (yes) 
```

ファイルの一覧で package.json が生成されていることを確認します（Windows）
```
> dir
<DIR>      .
<DIR>      ..
<DIR>      dev
<DIR>      html
       256 package.json
```

ファイルの一覧で package.json が生成されていることを確認します（macOS）
```
$ ls
dev       html        package.json
```

現在のディレクトリ構成は以下のようになりました
```
lesson
   │ 
   ├ dev
   │   │
   │   └ sass
   │ 
   └ package.json
```


