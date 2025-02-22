# PreCSS [<img src="https://postcss.github.io/postcss/logo.svg" alt="PostCSS Logo" width="90" height="90" align="right">][postcss]

[![NPM Version][npm-img]][npm-url]

[PreCSS] lets you use Sass-like markup and staged CSS features in CSS.

```scss
$blue: #056ef0;
$column: 200px;

.menu {
  width: calc(4 * $column);
}

.menu_link {
  background: $blue;
  width: $column;
}

/* becomes */

.menu {
  width: calc(4 * 200px);
}

.menu_link {
  background: #056ef0;
  width: 200px;
}
```

PreCSS combines Sass-like syntactical sugar — like variables, conditionals, and
iterators — with emerging CSS features — like logical and custom properties,
media query ranges, and image sets.

## Usage

Add [PreCSS] to your build tool:

```bash
npm install precss --save-dev
```

#### Node

Use [PreCSS] to process your CSS:

```js
import precss from 'precss';

precss.process(YOUR_CSS);
```

#### PostCSS

Add [PostCSS] to your build tool:

```bash
npm install postcss --save-dev
```

Use [PreCSS] as a plugin:

```js
import postcss from 'postcss';
import precss from 'precss';

postcss([
  precss(/* options */)
]).process(YOUR_CSS);
```

#### Gulp

Add [Gulp PostCSS] to your build tool:

```bash
npm install gulp-postcss --save-dev
```

Use [PreCSS] in your Gulpfile:

```js
import postcss from 'gulp-postcss';
import precss from 'precss';

gulp.task('css', function () {
  return gulp.src('./src/*.css').pipe(
    postcss([
      precss(/* options */)
    ])
  ).pipe(
    gulp.dest('.')
  );
});
```

#### Grunt

Add [Grunt PostCSS] to your build tool:

```bash
npm install grunt-postcss --save-dev
```

Use [PreCSS] in your Gruntfile:

```js
import precss from 'precss';

grunt.loadNpmTasks('grunt-postcss');

grunt.initConfig({
  postcss: {
    options: {
      use: [
        precss(/* options */)
      ]
    },
    dist: {
      src: '*.css'
    }
  }
});
```

# Plugins

PreCSS is powered by the following plugins (in this order):

- [postcss-extend-rule](https://github.com/jonathantneal/postcss-extend-rule)
- [postcss-advanced-variables](https://github.com/jonathantneal/postcss-advanced-variables)
- [postcss-preset-env](https://github.com/jonathantneal/postcss-preset-env)
- [postcss-atroot](https://github.com/OEvgeny/postcss-atroot)
- [postcss-property-lookup](https://github.com/simonsmith/postcss-property-lookup)
- [postcss-nested](https://github.com/postcss/postcss-nested)

[cli-img]: https://img.shields.io/travis/jonathantneal/precss/master.svg
[cli-url]: https://travis-ci.org/jonathantneal/precss
[git-img]: https://img.shields.io/badge/chat-gitter-blue.svg
[git-url]: https://gitter.im/postcss/postcss
[npm-img]: https://img.shields.io/npm/v/precss.svg
[npm-url]: https://www.npmjs.com/package/precss-v8

[Gulp PostCSS]: https://github.com/postcss/gulp-postcss
[Grunt PostCSS]: https://github.com/nDmitry/grunt-postcss
[PostCSS]: https://github.com/postcss/postcss
[PreCSS]: https://github.com/jonathantneal/precss
