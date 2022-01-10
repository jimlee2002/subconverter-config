subconverter-config
===

自用。

规则基于 [blackmatrix7/ios_rule_script](https://github.com/blackmatrix7/ios_rule_script)。

## 本地自部署

使用`docker-compose`。
- 下载仓库中的文件到特定文件夹。
- `docker-compose up -d`

## 使用

### 处理单订阅

**本地部署：**

- 默认处理单订阅，懒的话直接参考官方文档用链接传参。
- 有心思就参考`profiles/example-profile.ini`建个配置档案Profile。
    - 调用链接：`/getprofile?name=profiles/xxx-profile.ini`
    - 配置档案Profile只能本地调用，用已有的在线服务参考下面直接链接传参。
- 常用参数
    - `target=`：要生成的目标配置文件
    - `rename=`：重命名规则
    - `filename=`：生成的文件名
    - `udp=(true|false)`：是否开启upd
    - `rename=`：节点重命名规则，多条规则用 ` 分隔
    - `config=`：要用的配置文件（定义组与规则），自己看`custom/single/config`都有啥，也可以用在线的
    - `expand=(true|false)`：规则写入详细内容 or 写入 `rule-provider`
    - `list=(true|false)`：输出纯节点列表
- **注意：** 参数需要进行URLEncode，参数间用`&`分隔

**使用已有的在线服务：**`config=`用`-ol`后缀的，其他同上。

### 处理多订阅

参照 [aio 配置制作指南](custom/aio/README.MD) 编写

非通用性配置，所有aio相关的配置文件紧密捆绑。

需要往配置文件里直接编写特定参数，建议仅本地部署自用。

## 修改分流规则
- 新增分流规则：`custom/single/ruleset/rulesets.toml`
- 添加对应策略组：同步修改以下文件
    - `custom/single/groups/proxy-groups-max.toml`
    - `custom/single/groups/proxy-groups-mini.toml`
    - `custom/aio/aio-main-groups.toml`

## 常用正则小记

- `(?i:\\bSG[P]?\\b)`匹配地域代码


## 参考文档
[subconverter 中文文档](https://github.com/tindy2013/subconverter/blob/master/README-cn.md)