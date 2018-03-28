* 获取菜单数据

```js
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



