# 插件广场 (Plugin Market)
存储插件索引、Banner、介绍等信息。

## 发布插件
> [!Note]
> 请确保在您的插件的 GitHub 仓库中至少发布了一个 Release（您只需将插件打包成 .zip 压缩包上传），否则插件将无法在 PluginMarket 中下载。
> 
> 请确保您的插件仓库的 `plugin.json` 文件中的 `version` 字段与插件市场中的 `plugin_list.json` 文件中的 `version` 字段一致，否则客户端将无法获取到最新的插件信息。
> 请确保您的插件仓库发布的 Release 中的版本号与插件市场中的 `plugin_list.json` 文件中的 `version` 字段一致，否则客户端将无法获取到最新的插件信息。
若要发布插件，请按以下步骤操作：

1. Fork 本项目。
2. 修改 `./Plugins/plugin_list.json` 文件，按照以下格式添加您的插件信息（**注意和插件仓库中的 `plugin.json` 内容是不一样的！请仔细检查格式！**），随后提交PR 等待审核即可。

插件信息格式如下：
```
{
    "其他插件...": {
        ...
    },
    // 在这里添加您的插件信息
    "您的插件仓库名称": {
        "name": "插件在 PluginMarket 显示的名称",
        "description": "插件的简介",
        "version": "插件版本号（如：1.0.0）",
        "plugin_ver": "插件最低支持的 SecRandom 版本号（可在 SecRandom 的 关于 中的 版本 部分找到该值，格式为 x.x.x.x）",
        "author": "插件作者的 PluginMarket 名称",
        "url": "您的 GitHub 插件仓库链接 (例如：https://github.com/SECTL/SecRandom-plugin)",
        "branch": "插件仓库的分支（如：main）",
        "update_date": "插件更新日期（格式：yyyy/mm/dd）"
    }
}
```

后续更新时，您只需修改仓库中的 `plugin.json` 文件，更新版本号（`version`）。在客户端会自动获取插件仓库的 `plugin.json` 文件，对比版本号，若版本号 变动 则会提示用户更新。