# 插件广场 (Plugin Market)

> 存储插件索引、Banner、介绍等信息。

## 📋 发布插件指南

### ⚠️ 重要注意事项

在发布插件之前，请确保满足以下要求：

1. **Release 发布**：在您的插件 GitHub 仓库中至少发布了一个 Release（将插件打包成 `.zip` 压缩包上传），否则插件将无法在 PluginMarket 中下载。

2. **插件图标**：您的插件显示在插件广场的图标需要放置在您的插件仓库主文件夹下，建议使用 `icon.png` 格式。

3. **版本号一致性**：请确保以下三处的版本号保持一致，否则客户端将无法获取到最新的插件信息：
   - 插件仓库中 `plugin.json` 文件的 `version` 字段
   - 插件市场中 `plugin_list.json` 文件的 `version` 字段
   - 插件仓库发布的 Release 版本号

### 🚀 发布步骤

若要发布插件，请按以下步骤操作：

1. **Fork 本项目**
2. **修改插件列表**：编辑 `./Plugins/plugin_list.json` 文件，按照指定格式添加您的插件信息
3. **提交审核**：提交 PR 等待审核即可

### 📝 插件信息格式

> **注意**：此格式与插件仓库中的 `plugin.json` 内容不同，请仔细检查格式！

```json
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

### 🔄 更新流程

后续更新插件时，您只需：

1. 修改插件仓库中的 `plugin.json` 文件
2. 更新版本号（`version`）
3. 发布新的 Release

客户端会自动获取插件仓库的 `plugin.json` 文件，对比版本号，若版本号发生变动则会提示用户更新。