# Markdown Loader
基于markdown-it的markdown解析插件.

Versions of dependencies:
```
    "loader-utils": "^2.0.0",
    "markdown-it": "^10.0.0",
    "schema-utils": "^2.6.5"
```

## Install
```
npm install markdown-loader-y --save
```
## Usage
const path = require('path')
const HtmlWebpackPlugin = require('html-webpack-plugin')

module.exports = {
  entry: {
    index: './src/index.js',
  },

  plugins: [
    new HtmlWebpackPlugin({
      filename: 'index.html',
      template: './src/index.html'
    }),
  ],

  module: {
    rules: [
      {
        test: /\.md$/,
        use: [
          {
            loader: 'html-loader',
            options: {
              esModule: false
            }
          },
          {
            loader:'markdown-loader-y',
            options: {
              html: true
            }
          }],
      },
    ]
  },
}