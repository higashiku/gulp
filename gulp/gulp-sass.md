# gulp-sass

- https://www.npmjs.com/package/gulp-sass/

## 導入

gulp-sass をインストール
```
$ npm install gulp-sass --save-dev
```

### タスクの追加

gulpfile.js 公式サイトのタスクをコピペします
```
'use strict';
 
var gulp = require('gulp');
var sass = require('gulp-sass');
 
gulp.task('sass', function () {
  return gulp.src('./sass/**/*.scss')
    .pipe(sass().on('error', sass.logError))
    .pipe(gulp.dest('./css'));
});
 
gulp.task('sass:watch', function () {
  gulp.watch('./sass/**/*.scss', ['sass']);
});
```

簡単な解説
```
// 厳格モードで実行され、厳格なエラーチェックが行われます
'use strict';

// node モジュールを読み込み
var gulp = require('gulp');
var sass = require('gulp-sass');

// sass タスク
// $ gulp sass コマンドで実行することができます
gulp.task('sass', function () {
  return gulp.src('./sass/**/*.scss') // Sass のディレクトリ
    .pipe(sass().on('error', sass.logError))
    .pipe(gulp.dest('./css'));        // CSS を出力するディレクトリ
});

// $ gulp sass:watch コマンドで実行する処理
// ./sass/**/*.scss ディレクトリを監視し、変更があれば sass タスクを実行します
gulp.task('sass:watch', function () {
  gulp.watch('./sass/**/*.scss', ['sass']);
});
```

ディレクトリ構成に合わせ、パスを編集します

- './sass/**/*.scss' → './dev/sass/**/*.scss'
- './css' → './html/css'


書き換える場所はこの3箇所
```
'use strict';
 
var gulp = require('gulp');
var sass = require('gulp-sass');
 
gulp.task('sass', function () {
  return gulp.src('./sass/**/*.scss')        ← 1/3
    .pipe(sass().on('error', sass.logError))
    .pipe(gulp.dest('./css'));               ← 2/3
});
 
gulp.task('sass:watch', function () {
  gulp.watch('./sass/**/*.scss', ['sass']);  ← 3/3
});
```

変更後は以下のようになります
```
'use strict';
 
var gulp = require('gulp');
var sass = require('gulp-sass');
 
gulp.task('sass', function () {
  return gulp.src('./dev/sass/**/*.scss')
    .pipe(sass().on('error', sass.logError))
    .pipe(gulp.dest('./html/css'));
});
 
gulp.task('sass:watch', function () {
  gulp.watch('./dev/sass/**/*.scss', ['sass']);
});
```

gulp sass を実行し、正常に動作することを確認します
```
$ gulp sass
[12:20:46] Using gulpfile ~/Desktop/lesson/gulpfile.js
[12:20:46] Starting 'sass'...
[12:20:46] Finished 'sass' after 20 ms
```

gulp sass:watch を実行し、正常に動作することを確認します
```
$ gulp sass:watch
[12:20:56] Using gulpfile ~/Desktop/lesson/gulpfile.js
[12:20:56] Starting 'sass:watch'...
[12:20:56] Finished 'sass:watch' after 9.85 ms
```

### Sass から CSS を生成してみる

dev/sass/style.scss
```
h1 {
  color: red;
}
```

現在のディレクトリは以下の通りです
```
lesson
   │ 
   ├ dev
   │    │
   │    └ sass
   │       │
   │       └ style.scss
   │
   ├ gulpfile.js
   │ 
   ├ html
   │ 
   └ package.json
```

gulp sass を実行し、CSSを生成してみます
```
$ gulp sass
[12:20:46] Using gulpfile ~/Desktop/lesson/gulpfile.js
[12:20:46] Starting 'sass'...
[12:20:46] Finished 'sass' after 20 ms
```

以下のように CSS ファイルが生成されていれば成功です
```
lesson
   │ 
   ├ dev
   │    │
   │    └ sass
   │       │
   │       └ style.scss
   │
   ├ gulpfile.js
   │ 
   ├ html
   │    │
   │    └ css
   │       │
   │       └ style.css
   │ 
   └ package.json
```

### watch で監視して自動更新

続いて gulp sass:watch を実行し、SCSS ファイルに変更があれば自動的に CSS を更新します
```
$ gulp sass:watch
[12:20:56] Using gulpfile ~/Desktop/lesson/gulpfile.js
[12:20:56] Starting 'sass:watch'...
[12:20:56] Finished 'sass:watch' after 9.85 ms
```

dev/sass/style.scss
```
h1 {
  color: red;
}

h2 {
  color: blue;
}
```

style.scss を保存すると、自動的に sass タスクが実行されます
```
MacBook-Pro:sample suekun$ gulp sass:watch
[12:20:56] Using gulpfile ~/Desktop/lesson/gulpfile.js
[12:20:56] Starting 'sass:watch'...
[12:20:56] Finished 'sass:watch' after 9.85 ms
[12:23:06] Starting 'sass'...
[12:23:06] Finished 'sass' after 39 ms
```






