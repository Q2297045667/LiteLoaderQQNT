# LiteLoaderQQNT

LiteLoaderQQNT 是一个 QQNT 的插件加载器。
它可以让你自由地为 QQNT 添加各种插件。
比如：美化主题，增加功能，做任何事情 等...

Telegram 闲聊群：https://t.me/LiteLoaderQQNT


## 注意事项

- 目前仍在开发当中，可能会存在一些问题和不足。
- 仅为个人兴趣而制作，开发目的在于学习和探索。
- 能力有限，随缘更新。不过也欢迎各位来提交PR。
- 由于项目特殊性，必要时会停止开发或删除仓库。


## 安装方法

请先去官网安装QQNT最新版：https://im.qq.com/，
支持 Windows, Linux, MacOS 的 32 位与 64 位 QQNT。

> Windows QQNT 9.9.1 版本，需根据 Release 的说明来使用 LiteLoaderQQNT。

安装位置：
- Windows: `QQNT的根目录/resources/app`
- Linux: `QQNT的根目录/resources/app`
- MacOS: `/Applications/QQ.app/Contents/Resources/app`

### 使用 Release 安装（推荐）

1. 下载 `Release` 中最新的 `LiteLoaderQQNT.zip`，解压出 `LiteLoader` 文件夹并放到 `安装位置`。
2. 编辑 `安装位置/package.json` 文件，将 `main` 键值改为 `LiteLoader`（如果使用Launcher请跳过）。
3. 重新启动 QQNT，享受 LiteLoaderQQNT 带来的乐趣吧！

### 使用 Clone 安装（不推荐）

1. 克隆 `Repo` 并拉取 `submodule`，将文件夹放到 `安装位置`，重命名文件夹为 `LiteLoader`。
2. 编辑 `安装位置/package.json` 文件，将 `main` 键值改为 `LiteLoader`（如果使用Launcher请跳过）。
3. 重新启动 QQNT，享受 LiteLoaderQQNT 带来的乐趣吧！

应与 package.json 文件同级：
```
├─app_launcher
├─LiteLoader    <--在这
│  ├─builtins
│  ├─src
│  ├─package.json
│  └─...
├─package.json
└─...

```

QQNT 的 package.json 文件示例：
```
{
    ...
    "homepage": "https://im.qq.com",
    "sideEffects": true,
    "main": "LiteLoader",   <- 修改这里（只需要指向文件夹即可）
    ...
}
```


## 插件开发

如需上架插件市场，要使用最新的 manifest 格式（建议参考已上架插件，文件来源可使用仓库源码，也可用 Release 指定文件），并在 Github 开源。
需要打包的插件请在仓库发布 Release，文件尽量使用 Github Actions 打包。
插件模板：[LiteLoaderQQNT-Plugin-Template](https://github.com/mo-jinran/LiteLoaderQQNT-Plugin-Template)  
插件仓库：[LiteLoaderQQNT-Plugin-List](https://github.com/mo-jinran/LiteLoaderQQNT-Plugin-List)

> Windows QQNT 9.8.5 版本及以上暂时无法打开自身的 DevTools，请安装 Chii Devtools 插件（推荐）或 QQNT vConsole 插件进行调试。


## 数据目录

LiteLoaderQQNT 的默认数据文件夹在 `用户目录/Documents/LiteLoaderQQNT`，修改环境变量 `LITELOADERQQNT_PROFILE` 可指定目录位置。

数据目录结构：
```
LiteLoaderQQNT
    ├─plugins           // 插件本体目录
    │   ├─my-plugin         // 插件本体
    │   └─...
    ├─plugins_cache     // 插件缓存目录
    │   ├─my-plugin
    │   └─...
    ├─plugins_data      // 插件数据目录
    │   ├─my-plugin
    │   └─...
    └─config.json       // LiteLoader配置文件
```


## 开源协议

[MIT License](./LICENSE)  
Copyright (c) 2023 沫烬染
