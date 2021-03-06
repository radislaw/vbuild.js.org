# Static files like favicon

You may need to copy favicon.ico or `CNAME` file if you're deploying to github pages, you can achieve this by creating a `./static` and put these files in it, and you're all set:

```bash
./static/favicon.ico ===> ./dist/favicon.ico
./static/CNAME ===> ./dist/CNAME
```

All the files inside `./static` will be copied to the root directory of `./dist` or a custom dist path if use `--dist` option too.

You can also change the folder name you want for `static` folder, as well as the destination directory of files for `static` folder.

```js
export default {
  static: {
    // `from` is relative to `./`
    from: 'public',
    // `to` is relative to `./dist`
    to: './'
  }
}
```

Now everything inside `./public` will be copied to './dist'.

You can also use an array as `static` option to totally override the default one and copy more directories.


```js
export default {
  static: [
    {from: './src/assets', to: './assets'},
    {from: './static', to: './'}
  ]
}
```

You can find the option definitions at [copy-webpack-plugin](https://github.com/kevlened/copy-webpack-plugin#pattern-properties).
