# 仿掘金 - CMS

## 登录

## api

### base: https://api.skyseek.top

### 地址： https://api.skyseek.top/admin

### 首页获取所有文章： https://api.skyseek.top/api/acticles?fields=id,title,description&populate=*

```json
{
      "id": 3,
      "title": "前端概念与HTML ｜ 青训营笔记",
      "description": "首先他是现在Web2.0的环境下，解决GUI人机交互的最主流的方案。其次前端开发者应该具备跨终端的能力，使用web技术栈，解决多端图形界面交互问题。",
      "user_info": {
        "id": 2,
        "introduce": "努力耕耘的大学生",
        "createdAt": "2023-02-11T14:57:35.836Z",
        "updatedAt": "2023-02-11T14:57:59.623Z",
        "publishedAt": "2023-02-11T14:57:59.621Z",
        "user_name": "杨鹏"
      },
      "acticle_tag": {
        "id": 8,
        "tagName": "青训营",
        "createdAt": "2023-02-11T15:29:13.695Z",
        "updatedAt": "2023-02-11T15:29:14.314Z",
        "publishedAt": "2023-02-11T15:29:14.313Z"
      }
```

### 获取单个详情文章：https://api.skyseek.top/api/acticles?filters[id][$eqi]=${id}&populate=*

    - ${id}为传入的id

```json
{
  "id": 3,
  "title": "前端概念与HTML ｜ 青训营笔记",
  "description": "首先他是现在Web2.0的环境下，解决GUI人机交互的最主流的方案。其次前端开发者应该具备跨终端的能力，使用web技术栈，解决多端图形界面交互问题。",
  "content": "**这是我参与「第五届青训营 」笔记创作活动的第一天**\n# 前端概念\n### 什么是前端\n首先他是现在Web2.0的环境下，解决GUI人机交互的最主流的方案。其次前端开发者应该具备跨终端的能力，使用web技术栈，解决多端图形界面交互问题。\n### 前端技术栈\n前端技术栈主要分为三层，HTML+CSS+JavaScript 分别对应着 内容+样式+行为，这是构建前端的基础，可以使用HTTP网络协议对服务器发送网络请求进行交互传递数据。\n### 前端需要关注的问题\n- 功能：满足用户功能需求\n- 美观：页面样式是否满足用户审美\n- 无障碍：网站是否对所有人可用\n- 安全：保障用户数据安全\n- 性能：用户是否使用流畅\n- 兼容：是否可以在多种web平台使用\n- 体验：用户直观感受\n### 前端的边界\n前端除了开发页面，在如今也可以做更多的事情\n- node.js：开发服务器端应用\n- electron：开发客户端应用\n- webRTC：P2P在线传输\n- WebGL：开发3D应用\n- WebASSEMBLY：将c++等语言在web端上运行\n# HTML概念\n### HTML是什么\n> HyperText Markup Language \n\n- HyperText：超文本\n- Markup Language：标签语法\n### HTMl概念\n#### DOM树\n他是由层层嵌套的HTML标签形成的树结构，里面的每个节点称之为DOM节点，这不禁让我们想到Vue底层的虚拟DOM树也是通过HTML类似的结构对页面进行渲染\n#### 语义化是什么\nhtml元素、属性、属性值都拥有对应的含义，这个就叫做语义。语义化是指开发者开开发的时候需要遵循语义来进行开发，比如开发的时候不应该贪图方便都是div和span，而应该用已存在的html标签对文章内容进行合理的编写\n#### 为什么需要语义化\n- 开发者：在开发的时候，可以通过语义化标签快速判断数据的作用\n- 搜索引擎：可以提取关键字、排序等\n- 屏幕阅读器：给特殊人群带来便利\n# 总结\n学习完这节课后对HTML有更深刻的理解了，比如HTML他存在是为了表达，而不是样式，所以在HTML上通过style添加样式是很不提倡的行为，因为样式我们已经有了CSS可以进行表达。然后就是语义化的重要性，这对开发者来说，规范的语义化习惯带给我们的好处是长远的，也为互联网的和谐生态可以贡献出自己微薄的一份力。",
  "createdAt": "2023-02-11T15:31:35.753Z",
  "updatedAt": "2023-02-11T15:33:06.126Z",
  "publishedAt": "2023-02-11T15:31:36.651Z",
  "time": "2023-02-02",
  "acticle_tag": {
    "id": 8,
    "tagName": "青训营",
    "createdAt": "2023-02-11T15:29:13.695Z",
    "updatedAt": "2023-02-11T15:29:14.314Z",
    "publishedAt": "2023-02-11T15:29:14.313Z"
  },
  "user_info": {
    "id": 2,
    "introduce": "努力耕耘的大学生",
    "createdAt": "2023-02-11T14:57:35.836Z",
    "updatedAt": "2023-02-11T14:57:59.623Z",
    "publishedAt": "2023-02-11T14:57:59.621Z",
    "user_name": "杨鹏"
  },
  "cover": null
}
```

### 获取当前文章的相关文章：https://api.skyseek.top/api/acticle-tags?filters[tagName][$eqi]=${tagName}&populate=*&pagination[pageSize]=5

- ${tagName}为传进来的 tagName
- 最后的数字代表只拿 5 个

````json
{
  "id": 8,
  "tagName": "青训营",
  "createdAt": "2023-02-11T15:29:13.695Z",
  "updatedAt": "2023-02-11T15:29:14.314Z",
  "publishedAt": "2023-02-11T15:29:14.313Z",
  "acticles": [
    {
      "id": 4,
      "title": "CSS：前端的必修课 ｜ 青训营笔记",
      "description": "层叠样式表：用来定义页面元素的样式\n名称CSS中的“层叠（cascading）”表示样式单规则应用于HTML文档元素的方式。具体地说，CSS样式单中的样式形成一个层次结构，更具体的样式覆盖通用样式。",
      "content": "**这是我参与「第五届青训营 」笔记创作活动的第2天**\n# CSS是什么\n\n> Cascading Style Sheets\n\n层叠样式表：用来定义页面元素的样式\n名称CSS中的“层叠（cascading）”表示样式单规则应用于HTML文档元素的方式。具体地说，CSS样式单中的样式形成一个层次结构，更具体的样式覆盖通用样式。样式规则的优先级由CSS根据这个层次结构决定，从而实现级联效果。\n\n## css的基本组成\n- 选择器 Selector：选择HTML元素，对其进行样式的修改\n- 选择器 Property：选择CSS中内置属性，他代表某些含义\n- 属性值 Value：选择想要的样式\n- 声明 Declaration：Property和Value结合中间用‘:’分割，结尾用‘;’代表他是一个声明\n- 规则：选择器加大括号加上声明，他属于一条规则\n\n```js \nh1{\n    //下面代表一个声明\n    color:white;\n    //上面代表的就是一个声明\n}\n```\n## 页面中使用css的方式\n- 外链：通过link标签引入\n- 嵌入：通过在html中添加style标签，在其标签内写css代码\n- 内联：在需要修改样式的元素处，添加style属性修改当前元素的样式\n\n一般来说推荐第一种，可以更符合语义化，html就是内容，css就是样式，通过文件分开。\n## CSS的工作流程\n\n<img src=\"https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/ca51c6d301474f61b20a7782e0859c71~tplv-k3u1fbpfcp-watermark.image?\" alt=\"Snipaste_2023-01-16_10-51-08.png\" width=\"70%\" />\n\n可见，我们的CSS与HTMl有相应单独解析的过程，最后在创建DOM树的时候，将其合并后展示\n\n# CSS使用介绍\n## 选择器\n- 通配选择器：可以选择全部元素\n- 标签选择器：选择标签元素\n- id选择器：读取标签中的id属性值，选择对应的元素，**id应该应该是唯一的**\n- 类选择器：读取标签中的class属性值，选择对应的元素\n- 伪类选择器：选择标签不同的状态下的样式，存在状态伪类和结构伪类\n- 属性选择器：通过'[]'进行框选，可以选择拥有这个属性的标签，也可以选择当属性拥有特定的值时选择\n\n```js\n    input[type=\"password\"]{\n        xxx\n    }\n```\n以上代码为当input拥有type=\"password\"时生效的xxx样式。\n\n也可以通过 **\"^=\"** 和 **\"$=\"** 来选择以什么开头和什么结尾的属性，这跟正则的代表含义一样。\n\n\n### 组合\n\n<img src=\"https://p3-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/eac3945406ad40d5a5b2e65cd5e598b1~tplv-k3u1fbpfcp-watermark.image?\" alt=\"Snipaste_2023-01-16_11-11-44.png\" width=\"70%\" />\n\n### 特异度Specificity（权重）\n!important > 行间样式 > ID 选择器 >class 选择器｜伪类选择器｜属性选择器 >元素选择器｜伪元素选择器 > 通配符选择器｜子选择器选择器｜相邻兄弟选择器\n\n## 继承\n- 如果一个`属性具备继承性`, 那么`在该元素上设置后`, 它的`后代元素都可以继承这个属性`;\n- 当然, 如果`后代元素自己有设置该属性`, 那么`优先使用后代元素自己的属性`(不管继承过来的属性权重多高);\n\n*关于盒模型部分的属性通常不可继承性*\n\n显式继承`box-sizing: inherit;`可以使原本不可继承的变成可继承。\n\n## 初始值\ncss中，每个属性都有一个初始值，可以使用initial关键字显式重置为初始值\n\n比如`background-color: initial`,将背景颜色重置为初始值透明。\n\n## 盒模型\n### contentbox\n可以把标签看成一个个的盒子，他由content，padding，boder，margin组成，设置的宽高是content的宽高。\n### boder-box\n在`box-sizing: boder-box`下，设置的宽高包括content，padding，boder，这样更符合开发直觉。\n\n## 行级和块级\n### 行级排版上下文 Inline Formatting Context（IFC）\n只包含行级盒子的容器会创建一个IFC，在其中的排版规则如下\n- 盒子在一行内水平摆放\n- 一行放不下会换行显示\n- text-align决定一行内盒子的水平对齐\n- vertical-align决定一个盒子在行内的垂直对齐\n- 会避开浮动元素\n### 块级排版上下文 Block Formatting Context （BFC）\n会创建一个BFC的容器有：根元素、浮动、绝对定位、inline-block、Flex子项和Grid子项、overflow不是visible的块盒、display：flow-root。其中排版规则如下\n- 盒子从上到下摆放\n- 垂直margin合并\n- BFC内盒子的margin不会与外面的合并\n- BFC不会和浮动元素重叠\n\n## Flex Box\n他属于一种新的排版上下文，可以控制子级盒子",
      "createdAt": "2023-02-11T15:52:38.210Z",
      "updatedAt": "2023-02-11T16:00:04.241Z",
      "publishedAt": "2023-02-11T15:52:39.714Z",
      "time": "2023-02-01"
    },
    {
      "id": 3,
      "title": "前端概念与HTML ｜ 青训营笔记",
      "description": "首先他是现在Web2.0的环境下，解决GUI人机交互的最主流的方案。其次前端开发者应该具备跨终端的能力，使用web技术栈，解决多端图形界面交互问题。",
      "content": "**这是我参与「第五届青训营 」笔记创作活动的第一天**\n# 前端概念\n### 什么是前端\n首先他是现在Web2.0的环境下，解决GUI人机交互的最主流的方案。其次前端开发者应该具备跨终端的能力，使用web技术栈，解决多端图形界面交互问题。\n### 前端技术栈\n前端技术栈主要分为三层，HTML+CSS+JavaScript 分别对应着 内容+样式+行为，这是构建前端的基础，可以使用HTTP网络协议对服务器发送网络请求进行交互传递数据。\n### 前端需要关注的问题\n- 功能：满足用户功能需求\n- 美观：页面样式是否满足用户审美\n- 无障碍：网站是否对所有人可用\n- 安全：保障用户数据安全\n- 性能：用户是否使用流畅\n- 兼容：是否可以在多种web平台使用\n- 体验：用户直观感受\n### 前端的边界\n前端除了开发页面，在如今也可以做更多的事情\n- node.js：开发服务器端应用\n- electron：开发客户端应用\n- webRTC：P2P在线传输\n- WebGL：开发3D应用\n- WebASSEMBLY：将c++等语言在web端上运行\n# HTML概念\n### HTML是什么\n> HyperText Markup Language \n\n- HyperText：超文本\n- Markup Language：标签语法\n### HTMl概念\n#### DOM树\n他是由层层嵌套的HTML标签形成的树结构，里面的每个节点称之为DOM节点，这不禁让我们想到Vue底层的虚拟DOM树也是通过HTML类似的结构对页面进行渲染\n#### 语义化是什么\nhtml元素、属性、属性值都拥有对应的含义，这个就叫做语义。语义化是指开发者开开发的时候需要遵循语义来进行开发，比如开发的时候不应该贪图方便都是div和span，而应该用已存在的html标签对文章内容进行合理的编写\n#### 为什么需要语义化\n- 开发者：在开发的时候，可以通过语义化标签快速判断数据的作用\n- 搜索引擎：可以提取关键字、排序等\n- 屏幕阅读器：给特殊人群带来便利\n# 总结\n学习完这节课后对HTML有更深刻的理解了，比如HTML他存在是为了表达，而不是样式，所以在HTML上通过style添加样式是很不提倡的行为，因为样式我们已经有了CSS可以进行表达。然后就是语义化的重要性，这对开发者来说，规范的语义化习惯带给我们的好处是长远的，也为互联网的和谐生态可以贡献出自己微薄的一份力。",
      "createdAt": "2023-02-11T15:31:35.753Z",
      "updatedAt": "2023-02-11T16:00:09.103Z",
      "publishedAt": "2023-02-11T15:31:36.651Z",
      "time": "2023-02-02"
    }
  ]
}
````

### 获取所有标签： https://api.skyseek.top/api/tags

### 获取作者榜：https://api.skyseek.top/api/user-names

### 文章 tag 栏：https://api.skyseek.top/api/acticle-tags

```json
{
      "id": 2,
      "tagName": "综合",
      "createdAt": "2023-02-11T15:28:29.031Z",
      "updatedAt": "2023-02-11T15:28:29.532Z",
      "publishedAt": "2023-02-11T15:28:29.531Z"
    },
```

### 标签切换栏：https://api.skyseek.top/api/tags

- isActive 为 true 时代表这个 tag 有角标

```json
{
      "id": 4,
      "tag_name": "课程",
      "isActive": false,
      "activeContent": null,
      "createdAt": "2023-02-11T15:24:35.348Z",
      "updatedAt": "2023-02-11T15:24:35.923Z",
      "publishedAt": "2023-02-11T15:24:35.920Z"
    },
    {
      "id": 8,
      "tag_name": "竞赛",
      "isActive": true,
      "activeContent": "马上报名",
      "createdAt": "2023-02-11T15:25:44.404Z",
      "updatedAt": "2023-02-11T15:25:44.858Z",
      "publishedAt": "2023-02-11T15:25:44.857Z"
    },
```

### 广告图片位：https://api.skyseek.top/api/ads?populate=*

    - 媒体文件第一个分辨率较低，第二个分辨率高

```json
{
  "id": 1,
  "createdAt": "2023-02-11T15:14:10.284Z",
  "updatedAt": "2023-02-11T15:22:20.072Z",
  "publishedAt": "2023-02-11T15:22:20.070Z",
  "AD": [
    {
      "id": 11,
      "name": "9e74d078b35f4c1da88965f08adfa146_tplv-k3u1fbpfcp-no-mark_480_400_0_0.webp",
      "alternativeText": "9e74d078b35f4c1da88965f08adfa146_tplv-k3u1fbpfcp-no-mark_480_400_0_0.webp",
      "caption": "9e74d078b35f4c1da88965f08adfa146_tplv-k3u1fbpfcp-no-mark_480_400_0_0.webp",
      "width": 480,
      "height": 400,
      "formats": {
        "thumbnail": {
          "name": "thumbnail_9e74d078b35f4c1da88965f08adfa146_tplv-k3u1fbpfcp-no-mark_480_400_0_0.webp",
          "hash": "thumbnail_9e74d078b35f4c1da88965f08adfa146_tplv_k3u1fbpfcp_no_mark_480_400_0_0_2701a40dd6",
          "ext": ".webp",
          "mime": "image/webp",
          "path": null,
          "width": 187,
          "height": 156,
          "size": 3.52,
          "url": "/uploads/thumbnail_9e74d078b35f4c1da88965f08adfa146_tplv_k3u1fbpfcp_no_mark_480_400_0_0_2701a40dd6.webp"
        }
      },
      "hash": "9e74d078b35f4c1da88965f08adfa146_tplv_k3u1fbpfcp_no_mark_480_400_0_0_2701a40dd6",
      "ext": ".webp",
      "mime": "image/webp",
      "size": 11.02,
      "url": "/uploads/9e74d078b35f4c1da88965f08adfa146_tplv_k3u1fbpfcp_no_mark_480_400_0_0_2701a40dd6.webp",
      "previewUrl": null,
      "provider": "local",
      "provider_metadata": null,
      "createdAt": "2023-02-11T15:14:00.396Z",
      "updatedAt": "2023-02-11T15:14:00.396Z"
    }
  ]
}
```

### 二维码图片：https://api.skyseek.top/api/qrs?populate=*

    - 媒体文件第一个分辨率较低，第二个分辨率高

```json
      "QR_code_url": [
        {
          "id": 12,
          "name": "home.59780ae.png",
          "alternativeText": "home.59780ae.png",
          "caption": "home.59780ae.png",
          "width": 500,
          "height": 500,
          "formats": {
            "thumbnail": {
              "name": "thumbnail_home.59780ae.png",
              "hash": "thumbnail_home_59780ae_b9b96c18aa",
              "ext": ".png",
              "mime": "image/png",
              "path": null,
              "width": 156,
              "height": 156,
              "size": 10.65,
              "url": "/uploads/thumbnail_home_59780ae_b9b96c18aa.png"
            }
          },
          "hash": "home_59780ae_b9b96c18aa",
          "ext": ".png",
          "mime": "image/png",
          "size": 44.78,
          "url": "/uploads/home_59780ae_b9b96c18aa.png",
          "previewUrl": null,
          "provider": "local",
          "provider_metadata": null,
          "createdAt": "2023-02-11T15:15:27.972Z",
          "updatedAt": "2023-02-11T15:15:27.972Z"
        }
      ]
```

### 账户-密码

用户名：test
test@qq.com
Test123456

## 项目启动

```

npm run dev

# or

yarn dev

```

node 版本 >= 16

```

npm install
npm run develop

```

### 无法运行

运行

```

npm run strapi install i18n

```
## 部署

## 执行一下的步骤
1. 安装 nginx
2. 安装node.js
3. 安装pm2

### 首先 
```
git clone https://github.com/ganbadui/juejin-cms
```

### 安装
```
yarn i
```
### 在当前目录下创建 `server.js`
```
const strapi = require('@strapi/strapi');
strapi().start();

```

### 使用pm2 运行

```
pm2 start ./server.js
```
### pm2常用命令
```
pm2 start
pm2 log
pm2 list

```

### centos7 部署错误解决方法
```sh
yum install -y centos-release-scl-rh 
yum install -y centos-release-scl 

安装gcc7 
yum install devtoolset-7-gcc.x86_64 && yum install devtoolset-7-gcc-c++.x86_64


---	启用
scl enable devtoolset-7 bash


--查看
g++ --version
```
