# 机器学习知识记忆网络

一个开源、无需后端的交互式机器学习知识图谱。项目基于《机器学习笔记》PDF重新组织知识结构，使用圆点表示概念、连线表示先修、包含、应用和对比关系。

## 在线访问

**[打开交互式机器学习知识图谱](https://douhu777.github.io/machine-learning-knowledge-map/)**

源代码仓库：https://github.com/douhu777/machine-learning-knowledge-map

## 在线功能

- 点击节点查看定义、学习重点、关键词和原文纠错
- 点击连线理解两个概念之间的关系
- 支持拖动画布、滚轮缩放和关键词搜索
- 自适应桌面端和移动端
- 不依赖数据库、账号或 ChatGPT，可作为普通静态网站部署

## 本地运行

项目没有第三方运行依赖。直接打开 `index.html` 即可，也可以启动本地静态服务器：

```powershell
python -m http.server 8000
```

然后访问 `http://localhost:8000`。

## 发布到 GitHub Pages

仓库包含 `.github/workflows/deploy-pages.yml`。推送到 `main` 分支后：

1. 打开仓库的 **Settings → Pages**。
2. 在 **Build and deployment** 中选择 **GitHub Actions**。
3. 工作流会将仓库根目录发布为 GitHub Pages 网站。

## 修改知识图谱

当前项目采用单文件静态实现，方便下载、教学和长期保存。打开 `index.html`，修改：

- `nodes`：节点名称、坐标、类别、摘要、学习重点和标签
- `edges`：起点、终点、关系类型与关系解释
- `colors`：节点类别配色

节点结构：

```js
[
  'node-id',
  '显示名称',
  x坐标,
  y坐标,
  '颜色分组',
  '知识类型',
  '详细摘要',
  '学习重点',
  ['标签1', '标签2']
]
```

连线结构：

```js
['起点ID', '终点ID', '关系名称', '关系解释']
```

## 内容边界

本项目是学习导航和记忆网络，不替代严谨教材。图谱中特别标记了原始笔记中偏差—方差、标准化、R²、逻辑回归及ADF检验等需要纠正的内容。旧版 `scikit-learn`、PyLTP、XGBoost 和 Neo4j 示例应按当前官方文档更新。

## 设计参考

交互布局参考了 [LAION Dataset Explorer](https://aella.inference.net/embeddings) 的全屏探索式界面，但本项目的代码、知识结构和视觉实现均为独立实现。

## License

[MIT](LICENSE)

