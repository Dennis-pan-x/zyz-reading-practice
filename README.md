# PASSAGE by ZYZ｜雅思阅读练习

个人雅思阅读练习项目。本仓库保存练习网页的当前版本，以及从浏览器导出的完整练习记录备份（成绩、用时、笔记、复盘）。

## 目录

| 路径 | 内容 |
|------|------|
| `PASSAGE-by-ZYZ-IELTS-Reading-2026-10-07-r2.html` | 练习网页（当前版本，电脑 Chrome 打开） |
| `使用说明.txt` | 官方使用与备份/恢复说明 |
| `records/ZYZ-Reading-Personal-Backup-YYYY-MM-DD.json` | 完整备份，按导出日期命名，越新越靠后 |

## 怎么用

1. 打开仓库页面，点开 `.html` 文件 → 右上角 **Download raw file**（或 `git clone`）
2. 下载后是普通文件，直接用 Chrome 打开（不要用预览窗口）
3. 练习记录保存在当前浏览器中，换电脑/换浏览器/清缓存前先备份

## 恢复记录

网页 → **记录 → 数据恢复** → 选择 `records/` 下的 JSON → 选「完整备份」→ 按提示核对恢复内容。

## 更新流程

1. 旧版网页里先 **记录 → 立即完整备份**，把 JSON 存到 `records/`（文件名带当天日期）
2. 把新版 HTML 放进仓库根目录（文件名保留版本号，不覆盖旧文件，Git 会保留历史）
3. 提交并推送：

```bash
cd ~/zyz-latest
git add -A
git commit -m "备份 2026-10-20 记录；更新网页到 2026-10-07-r2"
git push
```

## 推送失败怎么办

本机全局配置了 `http.https://github.com.proxy = http://127.0.0.1:7897`（Clash）。代理没开时推送会报 `Failed to connect to 127.0.0.1 port 7897`：

- 先打开 Clash Verge（提供 7897 端口），再 `git push`
- 或者绕过代理直连：`git -c "http.https://github.com.proxy=" push`

本仓库已把该代理项设为空（直连优先）。直连时好时坏，失败就多重试几次或挂上代理。

## 说明

- 仓库为**公开**，`records/` 中的 JSON 含每次练习的成绩、用时和笔记，不含邮箱、电话等个人信息。
- Git 对 HTML 有压缩存储，单个版本约 26MB；同一版本反复修订会累积历史体积，旧版本网页如无需要可删除后提交。
