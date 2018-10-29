# 从零配置react项目
* 1.建立一个文件夹作为根目录，例如：jnode_test03,用命令"npm init"初始化项目，初始化后会生成一个"package.json"文件。
* 2.在根目录下建立两个文件夹build和client，在build文件夹下建立webpack的配置文件"webpack.config.js"，在client文件夹下建立入口文件"app.js"和"App.js"。然后安装依赖包和开发依赖包，
>"npm i react"安装react依赖包
>"npm i react-dom"安装react-dom依赖包
>"npm i babel-core@6.\*"安装6.x版本的babel-core
>"npm i babel-loader@7.\*"安装7.x版本的babel-loader。
>
>>为了方便启动项目，在package.json文件夹下的"script"下加入' "build": "webpack --config build/webpack.config.js" '
* 3.在根目录下建立.babelrc文件配置babel文件
> 
~~~
{
  "presets": [
    ["es2015", {"loose": true}],
    "react"
  ]
}
~~~
* 4.安装开发依赖包
> "npm i babel-preset-es2015@6.\*"安装babel-preset-es2015开发依赖包
>"babel-preset-es2015-loose@8.\*"安装babel-preset-es2015-loose开发依赖包
>"babel-preset-react@6.\*"安装babel-preset-react开发依赖包  

<font color=red>**特别注意：**</font>安装时一定要安装指定版本，否则会出现不兼容的情况
* 5.安装"html-webpack-plugin"开发依赖包=>"npm i html-webpack-plugin@2.*",引入HTMLPlugin在module下的rules下配置HTML插件=>
~~~
plugins: [
    new HTMLPlugin()
]
~~~
在webpack.config.js下引入js文件加载的方式
~~~
{
        test: /.js$/,
        loader: 'babel-loader',
        exclude: [path.join(__dirname, '../node_modules')]
      }
~~~