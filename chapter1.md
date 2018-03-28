### 级联菜单

> 主要实现切换tab页的时候选中上级菜单

* 主要实现

监听route改变的时候去根据路径和参数做匹配，匹配到对应的菜单设置选中（这个方法不需要手动调用，在APP.vue文件里面）

```js
watch :{
    '$route' () {
        this.changeRouter({
            path:this.$route.path,
            params:this.$route.query
        });
    }
}
```



