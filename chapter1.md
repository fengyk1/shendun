* 从tab页切换会选中相应的菜单

菜单数据是从接口获取的，代码在store下面的action里面

```
[GetMenu]({ commit, state }, callBack) {
        if (!state.fetchMenu.isFetched) {
            http.post('shield-manage/users/queryMenuTree', {}).then(res => {
                if (res.respCode == '0000') {
                    let list = res.data.list.map((item, index) => {
                        if (index === 0) {
                            item.isActive = true
                        }
                        return item
                    })
                    commit(GetMenu, {
                        isFetched: true,
                        data: list
                    })
                    callBack()
                    if (list[0].children && list[0].children.length) {
                        commit(changeSubMenu, list[0].children[0]);
                    }
                }
            })
        }
    }
```



