# CS2工具盒子线上数据仓库

这个仓库用于维护软件的线上公开数据：

- `sponsors.json`：赞助名单，只填写确认展示的昵称和可选留言。
- `notices.json`：更新提示，软件启动后会读取，未看过的提示会弹出一次。

## 上传方式

1. 在 GitHub 新建公开仓库：`cs2-toolbox-data`
2. 把本文件夹里的 `README.md`、`sponsors.json`、`notices.json` 上传到仓库根目录
3. 确认 Raw 地址类似：

```text
https://raw.githubusercontent.com/Infatuation-Studio/cs2-toolbox-data/main/sponsors.json
https://raw.githubusercontent.com/Infatuation-Studio/cs2-toolbox-data/main/notices.json
```

如果 GitHub 账号或组织不是 `Infatuation-Studio`，需要把软件里的线上数据地址改成你的 Raw 根地址。

## 更新赞助名单

只改 `sponsors.json`：

```json
{
  "sponsors": [
    {
      "name": "赞助昵称",
      "message": "留言或备注"
    }
  ]
}
```

没有留言时可以省略 `message`。

## 发布更新提示

只改 `notices.json`，每条提示的 `id` 必须唯一。用户看过一次后，同一个 `id` 不会再弹。

```json
{
  "notices": [
    {
      "id": "v1.0.1",
      "type": "success",
      "title": "新版本提示",
      "message": "CS2工具盒子已经更新到 1.0.1。",
      "detail": "修复若干稳定性问题，优化悬浮窗体验。",
      "popup": true,
      "enabled": true
    }
  ]
}
```

`type` 可选：`info`、`success`、`warning`、`error`。
