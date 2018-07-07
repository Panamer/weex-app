## Commands

### npm start


### npm run dev

Open the code compilation task in watch mode.

### npm run ios

(Mac only, requires Xcode)
Starts the development server and loads your app in an iOS simulator.

### npm run android

### npm run pack:ios

只能在Xcode上

### npm run pack:android

### npm run pack:web

Packaging html5 project into `web/build` folder.

### npm run test

Starts the test runner.
=======
# weex-app
用weex-toolkit结合vue-router开发weex单页app、

在build的时候css样式问题：

1、justify 不支持 text-align (支持: `left`|`center`|`right`)

2、color 不要写单词

3、不必写的样式(默认样式)
 flex-direction: column
 flex-wrap: nowrap
 position: relative
 
4、位置圆角等不可用百分比

5、样式名称要全写，比如，background要写成background-color

6、display可能不支持

官方提供的访问静态资源方法是可以的

分享朋友圈只能原生支持
