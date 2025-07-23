# 合成计算器

一个用于计算 Minecraft 物品合成所需原料的 Web 工具，支持配方推导和合成路径规划。

本项目虽主要针对 Slimefun 开发，但理论上可通过修改配方数据文件来适用于任何 Minecraft 原版和模组物品。

[![GitHub license](https://img.shields.io/github/license/myworldzycpc/crafting-calculator)](LICENSE)
[![GitHub issues](https://img.shields.io/github/issues/myworldzycpc/crafting-calculator)](https://github.com/myworldzycpc/crafting-calculator/issues)
[![GitHub stars](https://img.shields.io/github/stars/myworldzycpc/crafting-calculator)](https://github.com/myworldzycpc/crafting-calculator/stargazers)

## 功能特点

- 🔍 物品搜索与自动补全
- 📦 已有物品列表（支持数量限制）
- 🧪 配方推导计算
- 📊 合成路径可视化
- ⚙️ 一键添加常用粉类物品（针对 Slimefun）
- 📱 响应式设计，适配移动设备

## 截图预览

![合成计算器界面](screenshot.png)

## 使用方法

1. 在输入框中输入要合成的物品名称
2. 在搜索结果中选择目标物品
3. 在"已有物品"区域添加您已有的原料
4. 点击"计算"按钮获取合成方案
5. 查看"所需物品"、"合成过程"和"剩余物品"

## 自定义配方

编辑 `recipes.js` 文件添加或修改配方：

```javascript
const recipes = {
    "物品名称": {
        type: "合成类型", // 如"工作台"
        map: [           // 合成矩阵（可选）
            ["原料1", null, "原料2"],
            [null, "原料3", null],
            ["原料4", null, "原料5"]
        ],
        ingredients: [   // 所需原料
            ["原料1", 数量],
            ["原料2"],    // 默认数量为1
            // ...
        ],
        count: 1         // 一次合成的产出数量（默认为1）
    },
    // 更多配方...
};
```

## 添加图标

1. 将图标文件放入 `icons` 目录
2. 在 `icons.js` 中添加映射关系：

```javascript
const icons = {
    "物品名称": "图标文件名（不含扩展名）",
    // ...
};
```

## 安装与运行

1. 克隆仓库：
   ```bash
   git clone https://github.com/myworldzycpc/crafting-calculator.git
   ```
2. 打开 `index.html` 文件即可使用

或者，也可以直接访问 [GitHub Pages](https://myworldzycpc.github.io/crafting-calculator/index.html)

## 贡献指南

欢迎提交 Issue 和 Pull Request！贡献步骤：
1. Fork 项目
2. 提交修改
3. 创建 Pull Request

## 许可证

本项目采用 [GPLv3 许可证](LICENSE) - 详情请参阅 LICENSE 文件。

---

**提示**：图标取自 [Slimefun Resourcepack Remake (Release v1.8.0)](https://github.com/xMikux/Slimefun-Resourcepack)。

## 文件结构

```
crafting-calculator/
├── index.html
├── main.js
├── recipes.js      # 配方数据
├── icons.js        # 图标映射
├── main.css        # 样式文件
├── LICENSE
├── README.md
└── icons/          # 图标目录
    ├── stone.png
    ├── iron_ore.png
    └── ...
```