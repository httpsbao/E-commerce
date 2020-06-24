## 开启服务

##### 前端：

在项目目录下：

```
cd vue-online-shop-frontend
npm install
npm start
```

##### 后端

在项目目录下：

```
cd vue-online-shop-backend
npm install
npm start
```



##  各页面介绍

### 首页

主要有首页头部导航栏以及展示本地商品信息的列表，列表主要展示了本地商品的名称、介绍、价格、生产商以及添加购物车操作。

### 后台管理页面

主要用于对商品以及生产商的后台管理，包括查看商品（可以进行修改商品信息）、添加商品、查看生产商（可以进行修改生产商信息）以及添加生产商。



#### 查看商品页面

主要展示了后台商品的名称、价格、制造商以及修改和删除操作。

#### 添加/修改商品页面

展示一个表单页面，主要用于添加一个新商品或者对指定商品信息进行修改。

#### 查看制造商页面

主要展示了后台制造商的名称以及修改和删除操作。

#### 购物车页面

主要用于展示添加到本地购物车的商品信息列表，列表主要展示了购物车商品的名称、介绍、价格、生产商以及移出购物车操作。



## 页面展示

### 用 `element-ui` 组件库重构之前页面

首页

![admin 页面](https://github.com/httpsbao/E-commerce/blob/master/vue-online-shop-frontend/src/assets/adminPage.png)



商品列表

![Home 页面](https://github.com/httpsbao/E-commerce/blob/master/vue-online-shop-frontend/src/assets/homePage.png)

购物车

![执行加入购物车操作](https://github.com/httpsbao/E-commerce/blob/master/vue-online-shop-frontend/src/assets/cartPage.png)

移出购物车

![移除购物车](https://github.com/httpsbao/E-commerce/blob/master/vue-online-shop-frontend/src/assets/outCartPage.png)

### 用 `element-ui` 组件库重构之后页面

首页

![首页](https://github.com/httpsbao/E-commerce/blob/master/vue-online-shop-frontend/src/assets/home1.png)



管理页面

![管理页面](https://github.com/httpsbao/E-commerce/blob/master/vue-online-shop-frontend/src/assets/admin1.png)



## MongoDB 实践记录

注意：在使用 mongoimport 模块的时候必须要退出 mongo 环境！！！
mongoimport 导入 json 文件：

```
语法：
    mongoimport <options> <file>
 
介绍：
MongoDB的mongoimport模块是用来导入数据的模块。在开发中经常会用到。
mongoimport中有几个参数先展示一下：

-h,–host ：代表远程连接的数据库地址，默认连接本地Mongo数据库；
–port：代表远程连接的数据库的端口，默认连接的远程端口27017；
-u,–username：代表连接远程数据库的账号，如果设置数据库的认证，需要指定用户账号；
-p,–password：代表连接数据库的账号对应的密码；
-d,–db：代表连接的数据库；
-c,–collection：代表连接数据库中的集合；
-f, –fields：代表集合中的字段，可以根据设置选择导出的字段；
–type：代表导出输出的文件类型，包括csv和json文件；
-o, –out：代表导出的文件名；
-q, –query：代表查询条件；
–skip：跳过指定数量的数据；
–limit：读取指定数量的数据记录；
–sort：对数据进行排序，可以通过参数指定排序的字段，并使用 1 和 -1 来指定排序的方式，其中 1 为升序排列，而-1是用于降序排列,如sort({KEY:1})
其中三个加粗的部分是不可省略的参数。即：-d、-c、-f。

在winCMD中，键入以下命令：

mongoimport -d 使用的库的名称 -c 使用的集合的名称 -f 要导入的文件地址 
```

技巧：当不想输入–file后面的路径时，可以打开要导入的文件所在的文件夹，直接拖拽进 cmd 窗口即可。
