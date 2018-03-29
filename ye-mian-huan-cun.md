### 页面缓存

页面打开后再次点击tab或者是导航栏，实现不刷新功能，实现思路是用keep-alive把router-view包裹住，利用key属性来区分缓存页面

```
//页面代码实现
<keep-alive :include="list.join(',')">
    <router-view v-if="isRouteKey"></router-view>
    <router-view :key="key" v-else></router-view>
</keep-alive>

//key的实现
key(){
    return this.$route.fullPath;
}
```



