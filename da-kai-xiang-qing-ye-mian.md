### 打开详情页面

> 从列表页面跳转到详情目前用过该方法，如果使用vue-router提供的$router.push方法无法打开tab页签

神盾系统里面很多页面都有使用这个方法，比如打开详情页面，详情页面保存之后要跳转回列表页面，新增一个标签不跳转

```js
import {
    mapMutations
} from 'vuex'

//name:页签的名字
//router:vue的路由对象
//projectId:每个打开的页面都有一个id，删除等其他操作都需要根据id来判断
//url:路由里面配置的url
//params:需要带过去的参数

//如果要跳转到列表页面的话在参数里面加一个isOpenPage为true就会跳转到
this.openSubPage({
    name: '新增活动',
    router: this.$router,
    projectId: 'huodong_xinzeng', 
    url: '/main/niiwoo/operation/activitySettings', 
    params: {type:'add'}
});
```



