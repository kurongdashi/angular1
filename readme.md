# angular 

## 模块 module 层
* module层下面，包括service,controller,filter



# angular-animate 动画
[](http://cdn.static.runoob.com/libs/angular.js/1.4.6/angular-animate.min.js)

1. 引入ngAnimate 模块
``` 
 var app=angular.module('app',['ngAnimate']);
```
2. 作用监听dom变化添加一些css 类

例如：ng-hide ，基于此我们自己定义动画

```
.mk{
        width: 100px;
        height: 50px;
        margin-bottom: 20px;
        background-color:pink;
        transition:all .5s ;
    }
    .mk.ng-hide{
        height: 0;
        width: 0;
    }

```

# angular-route
[angular-route](https://cdn.bootcss.com/angular.js/1.7.0/angular-route.min.js)
 引入ngRoute 模块
``` 
 var app=angular.module('app',['ngRoute']);
```

1.  标签连接 a标签的 #! +标记实现
``` 
 <a href="#!/">首页</a>
    <a href="#!/html1">加载html页面1</a>
    <a href="#!/html2">加载html页面2</a>
    <br>
    <a href="#!/page1">加载templateUrl页面1</a>
    <a href="#!/page2">加载templateUrl页面2</a>

```
2. 路由容器 ng-view 指令指定div 为容器
``` 
<div ng-view ></div>

```

3. 创建模块时引入ngRoute 
``` 
 var app=angular.module('app',['ngRoute']);
```

4. 通过注入$routeProvider 作为路由对象，有when(),otherwise()方法

``` 

    app.config(['$routeProvider',function ($routeProvider) {

        $routeProvider
        // 第二个参数是对象，包括template ,redirectTo
            .when('/',{redirectTo:'/page1'})
            .when('/html1',{template:'这里是插入普通html 内容1...'})
            .when('/html2',{template:'普通html 内容2...'})
            // templateUrl此方法是会发生请求去服务器获取模板
            .when('/page1',{templateUrl:'page1.html'})
            .when('/page2',{templateUrl:'page2.html'})

    }]);

```


