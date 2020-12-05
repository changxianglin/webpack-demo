## 1. 创建项目并按照依赖

```
mkdir webpack-demo && webpack-demo
npm init --yes
npm install webpack webpack-cli --save-dev
```

## 2. 创建目录及文件

```
mkdir src && cd src
touch index.js
cd ..
mkdir dist && cd dist
touch index.html
```

## 3. 创建 index.js 内容

```
function component() {
  var element = document.createElement('div');

  element.innerHTML = 'Hello Webpack!'

  return element;
}

document.body.appendChild(component());
```

## 4. 创建 index.html 内容

```
<!doctype html>
<html>
  <head>
    <title>Webpack</title>
  </head>
  <body>
    <script src="bundle.js"></script>
  </body>
</html>
```

## 5. 确定 package.json 内容

```
{
  "name": "webpack-demo",
  "version": "1.0.0",
  "description": "",
  "private": true,
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "webpack"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "webpack": "^5.10.0",
    "webpack-cli": "^4.2.0"
  }
}
```

## 6. 创建配置文件 webpack.config.js

```
touch webpack.config.js
```

## 7. 配置 webpack.config.js

```
const path = require('path');

module.exports = {
  entry: './src/index.js',
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist')
  }
};
```

## 8. 运行 npm start 创建 bundle.js

```
npm run start
```

> 在 dist 中会产生一个 bundle.js 文件，在浏览器中打开 index.html 可得结果。

- [github 源码地址](https://github.com/changxianglin/webpack-demo)
