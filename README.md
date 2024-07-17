# IntelliJ IDEA 个人使用及配置

## 简介

主要包括以下几部分：

1. 个人配置同步问题
2. JetBrains 及插件激活
3. 常用配置整理
4. 插件推荐

## 配置同步

### GitHub 远程配置同步

使用方法： 

1. IntelliJ IDEA
2. File | Settings Repository 指定远程仓库地址 (自己在 GitHub 或者 Gitee 上新建一个空仓库即可)
3. Overwrite Local or Overwrite Remote

### JetBrains 账号配置同步

登录账号即可，无需过多解释

## 激活

### 利用 GitHub 项目免费申请 JetBrains 激活码

- 官方申请地址：[https://www.jetbrains.com/shop/eform/opensource?product=ALL](https://www.jetbrains.com/shop/eform/opensource?product=ALL)

申请条件：

1. GitHub 上有一个维护超过3个月的开源项目
2. 必须是 GitHub 开源项目的发起人或是活跃的 commiter
3. GitHub 开源项目必须指定一个 License

注意事项：

1. 提交申请前记得将 Github 个人信息中的 Email 公开
2. 收到申请成功的邮件后，如果没有注册 JetBrains 账号，记得去注册账号。注册地址：[https://account.jetbrains.com/login](https://account.jetbrains.com/login)
3. 申请成功后，可获得全家桶的使用权 1 年，如果到期了会提前给你发邮件还可以继续申请

> 或者直接参考这个地址：[https://blog.csdn.net/zlt2000/article/details/115611788](https://blog.csdn.net/zlt2000/article/details/115611788)

### 非正式激活（推荐）

- ~~2021.1.3版本（搭配试用30天到期自动续期插件永久免费食用），IDEA官方历史版本下载地址：[https://www.jetbrains.com/idea/download/other.html](https://www.jetbrains.com/idea/download/other.html)~~

- 使用始皇的：[ja-netfilter](https://gitee.com/ja-netfilter/ja-netfilter) 激活，相关文件已在 crack 文件夹下，参考如下步骤激活：

  1. 找到 crack 文件夹下的所有文件（ja-netfilter.zip、config.zip、activation_code.txt）复制到你本地文件夹中

  2. 解压并覆盖 `config` 到 `ja-netfilter` 原本的 `config`

  3. 修改 IDEA 的 `idea.vmoptions` 文件(文件在哪，Google 一下)，在末尾填上

     ```shell
     --add-opens=java.base/jdk.internal.org.objectweb.asm=ALL-UNNAMED
     --add-opens=java.base/jdk.internal.org.objectweb.asm.tree=ALL-UNNAMED
     
     -javaagent:/xxx/ja-netfilter.jar
     ```

     将其中的 `/xxx/ja-netfilter.jar` 替换为你自己的路径

  4. 打开IDEA，填入激活码（activation_code.txt 文件内容）

  5. 插件破解：需要猴油（tampermonkey）脚本, 解压 `tampermonkey.js.zip` 后，手动添加脚本到猴油中，打开 [https://plugins.jetbrains.com](https://plugins.jetbrains.com/) 搜索你想要激活的插件, 点击 `Generate Code` 按钮就能得到该插件的激活码, 粘入到插件的 `Activation Code` 中即可

- 当然，有能力的还是推荐购买正版激活

## 常用插件

- 按需关闭自带插件。插件优化：[IDEA 关闭不必要的插件减少内存占用](https://blog.csdn.net/tutian2000/article/details/80074643)
- 以下是推荐的插件：

| 序号 | 名称                                                     | 备注                                                         |
| ---- | :------------------------------------------------------- | ------------------------------------------------------------ |
| 1    | Alibaba Java Coding Guidelines                           | 阿里编程规范，可以检查自己的java命名规范编程规范以及bug，并会给出相应的解决方案 |
| 2    | Grep Console                                             | 对控制台输出的不同级别的日志进行上色，比如info级别是黑色，WARN级别是黄色，ERROR是橙色。不用找日志把眼睛找瞎了。<br/>配色方案：[利用grep-console插件使Intellij idea显示多颜色调试日志](https://blog.csdn.net/weixin_39973810/article/details/110190844) |
| 3    | Kotlin                                                   | 项目中使用到了Kotlin可以安装，现idea默认已自带               |
| 4    | Lombok                                                   | 以简单的注解形式简化POJO，现idea默认已自带                   |
| 5    | Translation                                              | 翻译                                                         |
| 6    | JRebel                                                   | 热加载插件，  代码改动之后无需重启服务，被修改的类会自动重新加载，破解请自行百度<br/>或者参考：[JRebel插件使用详解](https://blog.csdn.net/lianghecai52171314/article/details/105637251)<br/>修改完Java代码后，就可以通过快捷键 Ctrl+shift+F9 刷新项目 |
| 7    | CodeGlance Pro                                           | 类似于Sublime的右侧，整体代码滚动条，使用此插件可以查看缩略图一样，快速切换到自己需要去的地方~ |
| 8    | Rainbow Brackets                                         | 彩色括号匹配                                                 |
| 9    | Atom Material Icons                                      | 各种文件夹、文件图标                                         |
| 10   | .ignore                                                  | 生成各种模板化的git忽略文件                                  |
| 11   | MyBatis Log Free 或 Mybatis Log Plus                     | mybatis自己控制的参数编译有点反人类，选中需要转换的mybatis log日志，然后点击右键，选择Restore sql from slection<br/>这个版本免费：[地址](https://plugins.jetbrains.com/plugin/10065-mybatis-log-plugin) |
| 12   | Free Mybatis plugin 或 MybatisX 或 MyBatisCodeHelper-Pro | 生成mapper xml文件<br/>快速从代码跳转到mapper及从mapper返回代码<br/>mybatis自动补全及语法错误提示<br/>集成mybatis generator gui界面<br/>根据数据库注解，生成swagger model注解<br/>[MyBatisCodeHelper-Pro 破解版指导](https://blog.csdn.net/weixin_43811057/article/details/123759674) |
| 13   | Maven Helper                                             | 查找和排除冲突依赖项的简便方法，[IDEA Maven 镜像配置](https://blog.csdn.net/idto315/article/details/122888893) |
| 14   | Cool Request                                             | 1.根据 URL 直接跳转到对应的方法定义 ( Ctrl \ or Ctrl Alt N );<br/>2.提供了一个 Services tree 的显示窗口;<br/>3.一个简单的 http 请求工具;<br/>4.在请求方法上添加了有用功能: 复制生成 URL;,复制方法参数...<br/>5.其他功能: java 类上添加 Convert to JSON 功能，格式化 json 数据 ( Windows: Ctrl + Enter; Mac: Command + Enter )。 |
| 15   | GenerateAllSetter                                        | 当你进行对象之间赋值的时候，你会发现好麻烦呀，能不能有一个更好的办法呢~ 有，只要你选中需要生成set方法的对象，按下快捷键 alt+enter |
| 16   | CodeGeeX                                                 | 代码 AI 智能自动补全。                                       |
| 17   | IDE Eval Reset                                           | 2021.1.3版本，30天试用期无限循环（相当于破解）。<br/>1.添加第三方插件仓库`https://plugins.zhile.io`<br/>2.搜索：`IDE Eval Reset`插件进行安装<br/>3.在idea主界面help-->eval Reset点击重启idea<br/>或者参考：[idea 安装eval reset插件](https://blog.csdn.net/OracleOracolo/article/details/113886757) |
| 18   | arthas idea                                              | 基于IntelliJ IDEA开发的 Alibaba Arthas 命令生成插件，支持 Alibaba Arthas 官方常用的命令。 |
| 19   | Easy Javadoc                                             | 能帮助开发者快速生成类、方法、属性等中文javadoc/kdoc，快捷键 Ctrl+\ |
| 20   | GsonFormatPlus                                           | 基于json生成java实体类                                       |
| 21   | Key Promoter X                                           | 对你的idea操作，会提示相应的快捷键是什么                     |
| 22   | Save Action X                                            | 保存的时候进行格式化操作，去除某些文件的自动格式化<br/> `.*\.html`  `.*\.md`  `.*\.sql`  `.*\.xml`  `.*\.vue` |
| 23   | Squaretest 或 TestMe                                     | 生成单元测试                                                 |
| 24   | String Manipulation 或 ConverterX                        | 对字符串的操作，支持大小写驼峰转换，字符串加解密等           |
| 25   | Apifox Helper                                            | 在线接口文档                                                 |
| 26   | SonarLint                                                | 代码质量提示                                                 |
| 27   | Rainbow Variable                                         | 方法内彩色变量匹配                                           |

## 常用配置

看这两个就行：

1. [IDEA的常见的设置和优化（功能）](https://blog.csdn.net/zeal9s/article/details/83544074)
2. [2020年最新-IDEA最详细配置（配图文收藏版配置）](https://www.bilibili.com/read/cv5707434/)

### 主题

- 默认的 吸血鬼 主题，完美~

![image.png](https://images.gitee.com/uploads/images/2019/0118/000955_8a1a2c2a_945727.png)

### 字体

* 推荐 JetBrains Mono
* IDEA应用字体 和 代码字体 设置：

![IDEA应用字体](https://images.gitee.com/uploads/images/2019/0118/000955_06dda8fd_945727.png)
![代码字体](https://images.gitee.com/uploads/images/2019/0118/000955_dd80cfab_945727.png)


### 代码模板 

类似 sysout：

* Editor -> General -> Postfix Completion 

* Editor -> Live Templates

相关配置见：[IDEA代码模板](https://blog.csdn.net/Yinyaowei/article/details/103836510)

![image.png](https://images.gitee.com/uploads/images/2019/0118/000956_1335a7b5_945727.png)

### 文件头注释

* Editor -> File and Code Templates

```java
/**
 * 
 * @author zhangpj
 * @date ${DATE}
 */
```

![image.png](https://images.gitee.com/uploads/images/2019/0118/000957_0a1a36f9_945727.png)
