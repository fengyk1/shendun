### 删除tab

* 点击tab上面的x按钮会关闭当前tab页

菜单数据都是存放在state里面、神盾系统所有涉及到菜单增删改查的操作都放在store文件夹里面

### 使用案例

```js
//先从vuex里面引入mapMutations

import {
    mapMutations
} from 'vuex'

//然后在methods里面注入方法
...mapMutations(['removeTabItem'])
```

```js
this.removeTabItem({data:item,router:this.$router});
```



