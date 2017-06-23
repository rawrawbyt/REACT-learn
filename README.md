# REACT-learn

初始环境：已安装 Node.js 和 npm

## class01 
### 生成package.json
    
    ```
    $ npm init --yes
    ```

### 安装webpack
    
```
//$ npm install webpack webpack-dev-server --save-dev
$ npm install webpack@1.13.1 webpack-dev-server@1.14.1 --save-dev
```    

### 安装Babel：支持ES6语法，支持REACT的一些特性
    ```
    //$ npm install babel-cli --save-dev
    ```
####  安装Babel loader
> babel-core:核心模块
  babel-loader：文件特定格式转换
  
```
$ npm install babel-core babel-loader --save-dev
```
#### 安装ES6 和 REACT 支持
>babel-preset-es2015:ES6语法包
 babel-preset-react:React语法包
```
$ npm install babel-preset-es2015 babel-preset-react --save-dev
``` 
#### 配置.babelrc
根目录下新建.babelrc文件
```
{
    "presets":["es2015","react"]
  }
```

### ESLint：代码检查工具
#### 安装预处理
```
$ npm install eslint eslint-loader --save-dev
```
#### 安装差劲
```
//第三方格式插件(a①①y,注意啊不要打错，CV的我没话说)
$ npm install eslint-plugin-import eslint-plugin-react eslint-plugin-jsx-a11y --save-dev
$ npm install eslint-config-airbnb --save-dev
```  
#### 配置.eslintrc
根目录下新建.eslintrc文件
```
{
    "extends":"airbnb",
    "rules":{
            "comma-dangle":["error","never"]
    }
  }
```
### 5. 配置webpack插件
#### html-webpack-plugin
自动生成HTML页面，并引入正确的JavaScript文件依赖  
```
$ npm install html-webpack-plugin --save-dev
```
#### 新建webpack.config.js,具体内容见该文件
#### 配置package.json
```json
  "scripts": {
    "build":"webpack",
    "dev":"webpack-dev-server --hot"
  },
```

### 添加react库    
```
$ npm install react react-dom --save
```

### 试运行
#### 新建app/app.jsx
```
import React from 'react';
import ReactDOM from 'react-dom';
function App() {
  return (
    <div className="container">
      <h1>Hello Rawraw!</h1>
    </div>
  );
}
const app = document.createElement('div');
document.body.appendChild(app);
ReactDOM.render(<App />, app);
```
#### 运行
```
$ npm run dev
```
打开http://localhost:8080
##### 安装了webpack2的报错（先忽略）
用了1的config装了2.还是先学习1吧。跳到下一步
```
   //报错
      ①configuration.module has an unknown property 'preLoaders'.
      ②configuration.resolve has an unknown property 'root'
      ③configuration.resolve.extensions[0] should not be empty
   //解决(真是还好英语好)
    ①preloader,postloader都是webpack1的配置。webpack2中所有的load(pre~,~,posy~)要写在一个数组里
    ②resolve.root是webpack1中的配置。webpack2中root: APP_PATH改成modules: [APP_PATH, 'node_modules']
    ③webpack1需要传空值，webpack2把空值删了就可以了
    
    更多的改变[https://doc.webpack-china.org/guides/migrating/](https://doc.webpack-china.org/guides/migrating/)
    
    webpack --display-error-details
    查看具体的错误
    netstat -aon|findstr 80
    tasklist|findstr 4
    
```

### 组件热加载功能HMR
只更新修改过的组件
```
$ npm install babel-preset-react-hmre --save-dev
```
     
    
* 第二章 Webpack 的示例代码
	* part1 简单的 hello world
	* part2 使用 Loaders
	* part3 使用 webpack 配置文件
	* part4 使用 plugins 
* 第三章 
	* part3 搭建 React ＋ webpack 的开发环境
	* part4 React 组件简单例子： 制作自己的介绍页面
* 第四章
	* part1 Deskmark 应用的实现
* 第五章
	* part1 使用 Flux 架构完成一个 Todo List
	* part2 使用 Redux 和 Handlebars 完成一个简单数据状态变化的页面
* 第六章
	* part1 使用 React ＋ Redux 完成 Deskmark 的改造
	* part2 使用 React ＋ Redux ＋ redux-promise-middleware 实现 Deskmark 的异步请求
* 勘误（corrigendum）
	* 全书勘误表
