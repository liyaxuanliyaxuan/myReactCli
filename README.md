
### 功能实现
- [x] Es6/7
- [x] react/react-router/dva
- [x] less
- [x] dev-server
- [x] 模块热替换（HMR）
- [x] sourcemap
- [x] CSS代码分割
- [x] 代码分割(SplitChunksPlugin)
- [x] 浏览器缓存
- [x] tree shaking
- [x] DellPlugin
- [x] PWA
- [x] eslint
- [x] stylelint

### 快速开始
```javascript
git clone git@github.com:LuoShengMen/React-Whole-barrels.git
npm install  // 依赖包安装
npm run dll   // dllplugin进行打包
npm run start // 开发模式启动项目
npm run build // 生产环境项目打包
npm run dev-build // 开发环境打包
```

### 其他配置
```javascript
git checkout TS-React // 切换到ts配置
git checkout Multiplt-Page        // 切换到多页面配置
```

### 原仓库地址
https://github.com/Rashomon511/React-Whole-barrels.git
### details
- PWA的实现使用了workbox-webpack-plugin插件，该插件在生产模式下运行，不能进行用户自定义sw.js文件，必须通过更改插件的相关配置实现；另一种方案是开启https服务，使用serviceworker-webpack-plugin，该插件可以自定义sw.js（配置该文件的路径即可），使用service work服务都需要在脚本中进行注册。
- 提取css文件的两种方式：一种是使用extract-text-webpack-plugin，一种是使用mini-css-extract-plugin
- 生成html模板实现资源自动引入的方式：web-webpack-plugin；html-webpack-plugin，可以零配置，也可以指定进行配置。两类插件都会获取css的提取文件，在默认情况下放置在link中。
- 使用cdn加速设置publicPath时，由于插件的使用不同，在配置css的publicPath会有所不同，比如web-webpack-plugin可以配置路径，mini-css-extract-plugin可以配置路径，；html-webpack-plugin不能配置路径。