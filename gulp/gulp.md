# gulp（ローカル）

- https://www.npmjs.com/package/gulp-sass/

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