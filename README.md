# 自建 DSH 插件市场索引

这个仓库只放一个文件：`index.json` —— DeepSeek Harness「插件 → 发现」可读取的插件市场索引（format 1）。

内容 = [开放插件市场](https://github.com/polang233/dsh-plugin-index) 的完整索引（914 个插件）+ 额外收录的 `dsh-find-skill@0.2.1`，共 915 条。

## 发布到 GitHub Pages

1. GitHub 右上角 **+ → New repository**，名字填 `dsh-index`，可见性选 **Public**，不要勾选任何初始化文件，**Create repository**。
2. 进入新仓库 → **Add file → Upload files**，把本目录的 `index.json` 拖进去 → **Commit changes**。
3. 仓库 **Settings → Pages**：**Source** 选 `Deploy from a branch`，**Branch** 选 `main` + `/ (root)`，**Save**。
4. 等 1～2 分钟，Pages 页面顶部会出现 `Your site is live at https://<用户名>.github.io/dsh-index/`。

索引 URL（填进 DSH 的就是这个）：

```
https://<用户名>.github.io/dsh-index/index.json
```

不想等 Pages 生效也可以直接用 raw 地址（提交后立即可用，且是 200 直出、不跳转）：

```
https://raw.githubusercontent.com/<用户名>/dsh-index/main/index.json
```

## 在 DSH 里添加

**插件 → 发现 → 添加索引源** → 粘贴上面的 URL → **添加**。之后就能搜索、浏览、安装。

## 注意

- 相对图标路径（`icons/...`）没有一并上传，加载失败时 UI 会回落到默认插图，不影响安装。
- 这是**静态快照**：开放插件市场的源数据每 6 小时重建，这份不会自动更新。想更新就重新下载 `https://dshopen.org/index.json`、把 `dsh-find-skill` 那条塞回去（或直接替换上游文件再补一条）、重新上传。
- 索引由第三方内容组成，安装任何插件前请自行确认来源可信。
