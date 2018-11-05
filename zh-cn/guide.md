
# 开发规范

## 结构化规范

```
swad-webUi
│  .babelrc                     babel之配置文件.babelrc
│  .eslintignore                      配置忽略哪些文件的配置
│  .eslintrc.js                      eslint检测配置文件
│  .gitignore                      git忽略配置文件
│  favicon.ico                      浏览器页签图标
│  index.html                      入口页面
│  package.js                      前端项目依赖配置文件
│
├─node_modules                      前端项目依赖模块包
├─build                      构建脚本目录
│      build.js                      生产环境构建（编译打包）脚本
│      check-versions.js                      版本验证工具
│      dev-client.js
│      dev-server.js
│      utils.js
│      vue-loader.conf.js                      根据当前的开发环境对webpack中的vue-loader进行配置
│      webpack.base.conf.js                      配置webpack基础编译入口和输出等
│      webpack.dev.conf.js                       用于本地调试时的配置文件
│      webpack.prod.conf.js                      用于打包部署的配置文件
├─config                      项目配置
│      dev.env.js                      开发环境变量
│      index.js                      项目配置文件
│      prod.env.js                      生产环境变量
│      proden.env.js                      英文生产环境变量
│      rap.env.js
│      sit.env.js
├─dist                       打包后项目
├─disten                      英文版打包后项目
├─src                      项目源码目录
│  │  App.vue                       根组件
│  │  main.js                       入口js文件
│  ├─api                      接口目录
│  ├─assets                       资源目录，资源会被wabpack构建
│  │  ├─custom-theme                       换肤相关
│  │  ├─font                       字体图标资源文件
│  │  ├─iconfont                       字体图标脚本
│  │  └─img                       图片相关
│  ├─cache                       接口缓存相关
│  ├─components                       公共组件目录
│  ├─directive                       自定义指令相关
│  ├─filters                       过滤器
│  ├─i18n                       国际化
│  ├─mixins                      混入对象定义
│  ├─mock                      假数据
│  ├─router                      路由相关
│  ├─store                       vuex状态管理相关
│  ├─styles                      样式相关
│  ├─utils                      工具方法类
│  ├─vendor                      一些第三方库相关
│  └─views                       前端页面文件
│      ├─alarms
│      ├─assets
│      ├─dashboard
│      ├─error
│      ├─layout
│      ├─login
│      ├─order
│      ├─relation
│      ├─report
│      ├─risk
│      ├─situation
│      ├─system
│      ├─theme
│      └─traffic
└─static                      一些静态资源

```

## 组件命名规范
Vue官方文档给予以下说明：
> 当注册组件 (或者 prop) 时，可以使用 kebab-case (短横线分隔命名)、camelCase (驼峰式命名) 或 PascalCase (单词首字母大写命名)。
 PascalCase 是最通用的声明约定而 kebab-case 是最通用的使用约定。

 命名可遵循以下规则：

`
1、有意义的名词、简短、具有可读性
 2、以小写开头，采用短横线分割命名
 3、公共组件命名以公司名称简拼为命名空间(app-xx.vue)
 4、文件夹命名主要以功能模块代表命名
同时还需要注意：必须符合自定义元素规范: 使用连字符分隔单词，切勿使用保留字。app- 前缀作为命名空间: 如果非常通用的话可使用一个单词来命名，这样可以方便于其它项目里复用。
`

## 文件结构规范

``` Vue
<template>
          <div>
            <!--必须在div中编写页面-->
          </div>
</template>
<script>
          export default {
            components : {
            },
            data () {
              return {
              }
            },
            methods: {
            },
            mounted() {
            }
         }
</script>
<!--声明语言，并且添加scoped-->
<style lang="less" scoped>
</style>
```

- vue文件方法声明顺序

```script
    - components
    - props
    - data
    - created
    - mounted
    - activited
    - update
    - beforeRouteUpdate
    - metods
    - filter
    - computed
    - watch
```


## 注释规范

代码注释在一个项目的后期维护中显的尤为重要，所以我们要为每一个被复用的组件编写组件使用说明，为组件中每一个方法编写方法说明。
以下情况，务必添加注释

`
1.公共组件使用说明
 2.各组件中重要函数或者类说明
 3.复杂的业务逻辑处理说明
 4.特殊情况代码处理说明,对于代码中特殊用途的变量、存在临界值、函数中使用的hack、使用了某种算法或思路等需要进行注释描述
 5.注释块必须以/**（至少两个星号）开头**/；
 6.单行注释使用//；
`

## 编码规范

优秀的项目源码，即使是多人开发，看代码也如出一人之手。统一的编码规范，可使代码更易于阅读，易于理解，易于维护。尽量按照ESLint格式要求编写代码

`
    1.使用ES6风格编码源码
        定义变量使用let ,定义常量使用const
        使用export ，import 模块化
 2.组件 props 原子化
        提供默认值
        使用 type 属性校验类型
        使用 props 之前先检查该 prop 是否存在
 3.避免 this.$parent
 4.谨慎使用 this.$refs
 5.无需将 this 赋值给 component 变量
 6.调试信息console.log() debugger 使用完及时删除
`

- 更多详细编码风格参考官方给出的文档
[Vue官方风格指南](https://cn.vuejs.org/v2/style-guide/#%E8%A7%84%E5%88%99%E5%BD%92%E7%B1%BB)

