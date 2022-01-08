## 向多合一订阅添加新的 Airport

1. 在`profile/aio-profile.ini`中加入新 Airport 的订阅链接
    - 标注tag。
    - 多个链接间用`|`分隔。

2. 修改 `custom/aio/aio-rename.toml`。
    - 参照注释，新建 为该 Airport 所有节点加入前缀的主命名规则。
    - 按需添加其他命名规则。

3. 参考 `custom/aio/groups/example-airport-groups.toml` ，定义 Airport 节点分类组
    - 参照注释修改相关名字。
    - 参照注释新建 Airport 总选择组。
    - 参照已有代码定义节点地区分类组
        - 注释掉不需要的地区。
        - 按需修改各地区匹配规则/添加额外节点组。

4. 修改 `custom/aio/aio-config.toml`，参考注释引入刚才新建的Airport 节点分类组文件`xxx-groups.toml`。

5. 基于前面定义 Airport 节点分类组,修改 `custom/aio/groups/aio-main-groups`：
    - 向`手动选择`组中加入定义的 Airport 总选择组。
    - 向各地区接入组中加入对于 Airport 各地区的分类组。