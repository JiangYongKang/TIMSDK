# IMSDK小程序demo运行

##  一分钟跑通demo

1. 安装微信小程序 [开发者工具](https://mp.weixin.qq.com/debug/wxadoc/dev/devtools/download.html)。

2. 使用微信开发者工具打开`/dist/wx`目录

   ![](_doc/1.png)

3. 配置 `SDKAPPID` 和 `SECRETKEY`，获取方式参考：[密钥获取方法](https://cloud.tencent.com/document/product/269/36838#.E6.AD.A5.E9.AA.A41.EF.BC.9A.E5.88.9B.E5.BB.BA.E5.BA.94.E7.94.A8)
   1. 打开 `/dist/wx/static/debug/GeneraterUserSig.js` 文件
   2. 按图示填写相应配置后，保存文件
   
   ![](_doc/2.png)

4. 点击编译即可运行

   ![](_doc/4.png)
   
    > **常见问题：**
    >
    > 1. 合法域名
    >
    >    进入微信公众平台，在小程序开发的服务器域名配置相关域名信息
    >
    >    ![](_doc/5.png)
    >
    > 2. 基础库
    >
    >    如果打开项目后，编译报错，请您升级小程序开发工具为最新版本，基础库版本 > 2.1.1,
    >
    > 3. 本地设置
    >
    >    如上图所示


##  开发运行

### 项目目录

```xml
├───sdk/               - demo 中未使用，仅供自行集成 
├  └───wx/ 
├───build/   
├───config/
├───dist/
│   └───wx/            - MpVue 项目编译后文件目录，使用小程序开发工具导入此文件夹
├───src/
│   ├───components/    - 组件
│   ├───pages/         - 页面
│   ├───store/         - Vuex 目录
│   ├───stylus/        - 全局主题色样式，可以修改全局颜色
│   ├───utils/         - 方法
│   ├───app.json
│   ├───App.vue
│   └───main.js
├───static/            - 静态依赖资源
│   ├───debug/         - 包含 userSig 验证登录方法
│   ├───images/        - 图片
│   └───iview/         - 使用的 iview 组件
├───_doc/
├───.babelrc
├───.editorconfig
├───.eslintignore
├───.eslintrc.js
├───.postcssrc.js
├───index.html
├───package-lock.json
├───package.json
├───project.config.json
└───README.md

```

### 启动流程

1. 克隆本仓库到本地
      
     ```shell
     # 命令行执行
     git clone https://github.com/tencentyun/TIMSDK.git
     
     # 进入 Web Demo 项目
     cd TIMSDK/WXMini
    ```

2. 将`project.config.json`文件中的`appid`修改为自己微信小程序的`appid`

   ![](_doc\3.png)

3. 配置 `SDKAPPID` 和 `SECRETKEY`，获取方式参考：[密钥获取方法](https://cloud.tencent.com/document/product/269/36838#.E6.AD.A5.E9.AA.A41.EF.BC.9A.E5.88.9B.E5.BB.BA.E5.BA.94.E7.94.A8)
    1. 打开 `/dist/wx/static/debug/GeneraterUserSig.js` 文件
    2. 按图示填写相应配置后，保存文件
    
     ![](_doc/8.png)
     
4. 项目使用了 [MpVue](http://mpvue.com/mpvue/) 需要[nodejs](https://nodejs.org/zh-cn/) ( Version > 8 ) 环境

   安装依赖并启动

   ```shell
   # 安装demo构建和运行所需依赖
   npm install
   
   # 构建并生成最终可在小程序开发工具内使用的代码
   npm run start
   ```

   > **注意事项：**
   >
   > 1. node version > 8
   >
   > 2. 使用 npm install 命令，如果有些依赖包无法成功安装，你可以试着切换 npm 源，然后再执行npm install命令

6. 使用微信开发者工具导入项目，目录为`/dist/wx`

    ![](_doc/1.png)

7. 点击开发工具的编译即可预览该项目

   ![](_doc/4.png)

   > **注意事项：**
   >
   > 1. 合法域名
   >
   >    进入微信公众平台，在小程序开发的服务器域名配置相关域名信息
   >
   >    ![](_doc/5.png)
   >
   > 2. 基础库
   >
   >    如果打开项目后，编译报错，请您升级小程序开发工具，基础库使用>2.1.1,
   >

## 项目截图

   ![](_doc/6.png)

## 备注

### 页面结构

目录 /src/pages

| 页面  | 简介                                                        |
| :------- | ----------------------------------------------------------- |
| login/   | 登录页                                                       |
| index/   | 首页，对话列表                                                |
| chat/    | 聊天对话页 & 群信息/用户信息                                 |
| contact/ | 通讯录                                                       |
| own/     | 个人信息                                                     |
| create/  | 创建群聊                                                     |
| members/ | 群成员                                                       |
| profile/ | 修改个人信息                                                  |
| groups/ | 群列表                                      |
| groupDetail/ | 群详细页 |
| system/  | 系统通知页                                                   |
| blacklist/  | 黑名单页                                                  |
| detail/  | 个人信息&群信息                                               |
| friend/  | 发起会话                                                     |
| mention/ | @选择页 |