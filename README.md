##项目实现##

### 本节目标###

本节实验中我们将分别按照如下步骤：

抓取淘宝MM 的姓名，封面图片，年龄、所在城市等信息
抓取每一个MM个人主页内的写真图片
把每一个MM的写真图片按照文件夹保存到本地

### 可行性分析###

淘女郎首页上的源码信息是公开的，本次实验仅仅是用来技术实践，并不带盈利性目的，也不将图片用于其他商业环境，并不会产生商业上的产权纠纷，所以这个项目是可行的。

### 程序结构 ###

遍历淘女郎主页上所有 MM
抓取各个 MM 的姓名，封面图片，年龄、所在城市等信息
遍历MM 个人主页内的所有写真图片
把每 MM 的写真图片按照文件夹保存到本地

### 流程说明 ###

通过 Selenium Webdriver 获得目标页面源码，之后通过 BeautifulSoup 解析概源码，通过正则表达式提取出模特名字、所在城市、身高、体重，个人主页、封面图片地址等信息，根据模特名字和城市建立文件夹。
再次通过 Selenium Webdriver 获得模特个人主页的页面源码，之后通过 BeautifulSoup 解析源码，通过正则获得页面艺术照的URL地址信息。
最后通过 urllib 内置库，打开图片地址，通过二进制读写的方式获得模特艺术照，并将艺术照存在相应文件夹里面。