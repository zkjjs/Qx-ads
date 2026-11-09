# Qx-ads

Quantumult X 重写规则与独立的 Loon 脚本。按客户端选择对应文件。

| 客户端 | 文件 | 用途 |
| --- | --- | --- |
| Quantumult X | [Vipads](Vipads) | 重写规则集合，包含请求拦截和第三方响应脚本。 |
| Loon | [WeTalk_Loon.js](WeTalk_Loon.js) | WeTalk 签到与视频奖励脚本，文件开头附有 Loon 配置示例。 |

## Quantumult X

`Vipads` 是重写资源。把下面一行加到现有配置的 `[rewrite_remote]` 段，更新资源后查看重写规则是否加载。

```ini
https://raw.githubusercontent.com/zkjjs/Qx-ads/main/Vipads, tag=Vipads, enabled=true
```

此资源声明了较多 MitM 域名并引用第三方脚本。使用前可在 [原始规则](https://raw.githubusercontent.com/zkjjs/Qx-ads/main/Vipads)中查看匹配范围和脚本来源。配置格式见 [Quantumult X 官方示例](https://github.com/crossutility/Quantumult-X/blob/master/sample.conf)。

## Loon

打开 [WeTalk_Loon.js](WeTalk_Loon.js)，按文件开头的示例把 `[Script]` 条目和对应的 `[MITM]` 主机合并进现有 Loon 配置。请求规则和定时任务使用同一个脚本地址。

## GitHub Actions

[SideInstaller 构建工作流](.github/workflows/build-sideinstaller-gsa503-fix.yml) 检出上游 SideInstaller v0.9.0 并应用补丁。该工作流独立于客户端规则订阅。
