# ローカルへの gulp インストールと gulpfile.js の作成

- https://www.npmjs.com/package/gulp/

## インストール

gulp をインストールします（ローカル）
```
$ npm install gulp --save-dev
```

package.json を確認します
```
{
  "name": "lesson",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "gulp-sass": "^2.0.4" ← この行が追加されました
  }
}
```

## gulp を制御する gulpfile.js を作成

package.json と同じ階層に gulpfile.js を作成します（Windows）
```
> type nul > gulpfile.js
```

package.json と同じ階層に gulpfile.js を作成します（macOS）
```
$ touch gulpfile.js
```

現在のディレクトリ構成は以下のようになりました
```
lesson
   │ 
   ├ dev
   │    │
   │    └ sass
   │
   ├ gulpfile.js
   │ 
   ├ html
   │ 
   └ package.json
```
