# 可可影视 TVBox Jar 爬虫

## 文件说明

- `kekedy_spider.jar` — TVBox 爬虫 jar 包（主文件，必须）
- `tvbox_config_local.json` — 本地 jar 模式配置示例
- `tvbox_config_online_template.json` — 在线 jar 模式配置模板（上传 GitHub 用）

## 使用方法

### 方法一：本地 jar 模式（推荐，最稳）

1. 把 `kekedy_spider.jar` 传到手机里，放到 `/storage/emulated/0/TVBox/` 目录下
   （没有 TVBox 文件夹就自己建一个）

2. 打开 TVBox → 设置 → 配置地址，填入下面这个配置文件的地址
   （配置文件也可以放手机里，或者上传 GitHub）

3. 配置文件里 jar 路径写法：
```
jar:file:///storage/emulated/0/TVBox/kekedy_spider.jar;com.kekedy.spider.Spider
```

### 方法二：在线 jar 模式（不用传文件到手机）

1. 把 `kekedy_spider.jar` 上传到你的 GitHub 仓库

2. 点击 jar 文件，点 "Raw" 按钮，复制浏览器地址栏的链接

3. 修改 `tvbox_config_online_template.json` 里的 api 地址：
   把 `https://raw.githubusercontent.com/你的GitHub用户名/你的仓库名/main/kekedy_spider.jar`
   换成你刚才复制的 raw 链接

4. 把修改后的 json 配置文件也上传到 GitHub

5. TVBox 里填配置文件的 raw 链接就行

## TVBox 配置格式说明

```json
{
  "sites": [
    {
      "key": "kekedy_jar",
      "name": "可可影视",
      "type": 3,
      "api": "jar:jar包地址;爬虫类名",
      "searchable": 1,
      "quickSearch": 1,
      "filterable": 1,
      "ext": ""
    }
  ]
}
```

- `type: 3` — 表示这是 jar 爬虫源
- `api` 格式：`jar:jar包路径;完整类名`
  - 本地：`jar:file:///手机路径/kekedy_spider.jar;com.kekedy.spider.Spider`
  - 在线：`jar:https://xxx/kekedy_spider.jar;com.kekedy.spider.Spider`

## 爬虫功能

- 首页推荐
- 分类浏览（电影、连续剧、动漫、综艺、纪录、短剧）
- 视频详情
- 多播放源自动提取
- 搜索功能
- 自动域名轮询（主站挂了自动切备用）
- cdndefend 挑战自动破解

## 常见问题

**Q: TVBox 加载不出来？**
A: 检查 jar 路径对不对，TVBox 有没有存储权限，手机里的路径别写错。

**Q: 播放不了？**
A: 源站可能挂了，等会儿再试，jar 包会自动切备用域名。

**Q: 怎么添加更多源？**
A: 在配置 json 的 sites 数组里继续加就行。
