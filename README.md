# ding-editor-parse

#### 项目介绍
将富文本字符串转译为ding dom

#### 基本使用方法
（1）复制文件夹：

> 复制文件夹dingParse至项目中

(2)引入必要文件:

> 在需要使用的页面中引入dingParse组件

    <import src="../../component/dingParse/aParse.axml"/>

> 在使用的acss中引入aParse.acss,也可以在app.acss中全局引入

    @import "../../component/dingParse/aParse.acss";

(3)数据绑定

> index.js

    var AParse = require('../../component/dingParse/aParse.js');
    
    Page({
      onLoad(query) {
    
      let article = `
          <h3>
          <span style="color:red">钉钉小程序</span>
          <span style="color:green">富文本解析</span>
          <span style="color:blue">解决方案</span>
          </h3>
      `
        /**
         * 使用说明：
        * dingParse.AParse(bindName , type, data, target,imagePadding)
        * 1.bindName绑定的数据名(必填)
        * 2.type可以为html或者md(必填)
        * 3.data为传入的具体数据(必填)
        * 4.target为Page对象,一般为this(必填)
        * 5.imagePadding为当图片自适应是左右的单一padding(默认为0,可选)
        */
    
        let that = this;
        dingParse.aParse('article', 'html', article, that, 5);
      }
    });



（4）模板引用：

> 在相应的axml中引入模板，这里的article为bindName

    <import src="../../component/dingParse/aParse.axml"/>
    
    <template is="aParse" data="{{aParseData:article.nodes}}"/>


