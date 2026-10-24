# 第五人格战术演练学习工具 — 越南语个人本地化版（中文 / 越南语双语）

> **原作 / Bản gốc:** 第五人格战术演练学习工具 · 北京大学第五人格赛事（PIL）
> 原版页面：<https://pil-tactical-friend.ok.kimi.link/>　·　越南语翻译：**Steam_LILITALES**
> 源码：<https://github.com/lilyputina-hue>

本仓库是**北京大学第五人格赛事（PIL）**开发的《第五人格战术演练学习工具》的**越南语个人本地化版**，
供越南队日常训练查阅。原作者已明确许可个人本地化，条件是**注明开发者来源**——本页页头横幅与页脚
均已按要求署名。

## 双语切换

页面右上角有 **中文 / Tiếng Việt** 切换按钮：

- **原地切换，不刷新页面**——不会丢失当前状态
- 所选**地图**、**页签**（区域选择 / 密码机推演 / 战术面板）、**推演标记**、**战术面板上的造物与测距线**
  全部原样保留
- 语言偏好记在 `localStorage`（键名 `idv5_lang`），下次打开自动恢复

实现方式：所有界面文字在运行时经 `T()` 取自内置的 `I18N` 词典（中文 → 越南语），
静态 HTML 由 DOM 遍历替换，动态内容在重新渲染时生成；切回中文时按记录精确还原。

## 文件说明

| 文件 | 说明 |
|---|---|
| `index.html` | **全部内容**：单文件，同时支持中文与越南语，运行时切换 |
| `README.md` | 本文件 |
| `.github/workflows/pages.yml` | GitHub Pages 自动发布工作流 |
| `.nojekyll` | 让 GitHub Pages 原样托管静态文件 |

## 部署到 GitHub Pages

本项目**无需构建**，全部内容就是一个静态 HTML 文件。

1. 新建一个仓库（public），把本目录内容推到仓库根目录。
2. **Settings → Pages → Build and deployment → Source**：选择 *Deploy from a branch*，
   branch 选 `main`，目录选 `/(root)`。
3. 访问 `https://<用户名>.github.io/<仓库名>/`。

仓库内已附带 `.github/workflows/pages.yml`，推送后也可直接走 Actions 发布。

## 本地预览

```bash
python -m http.server 8000
# 浏览器打开 http://localhost:8000/
```

## 术语对照表

角色名与玩法术语取自 [Identity V Wiki Tiếng Việt](https://id5.fandom.com/vi/)。

| 中文（原作） | 越南语 | 备注 |
|---|---|---|
| 求生者 / 监管者 | Kẻ Sống Sót / Thợ Săn | wiki 官方译名 |
| 密码机 / 破译 | Máy Mã Hóa / Giải Mã | |
| 地窖 / 逃生门 | Hầm Chứa / Cửa Thoát Hiểm | |
| 军工厂 | Nhà Máy Quân Sự | Arms Factory |
| 圣心医院 | Bệnh Viện Thánh Tâm | Sacred Heart Hospital |
| 红教堂 | Nhà Thờ Đỏ | The Red Church |
| 湖景村 | Làng Hồ Phong Cảnh | Lakeside Village |
| 月亮河公园 | Công Viên Sông Trăng | Moonlit River Park |
| 里奥的回忆 | Ký Ức Leo | Leo's Memory |
| 永眠镇 | Thị Trấn Ngủ Đông | Eversleeping Town |
| 唐人街 | Phố Tàu | China Town |
| 不归林 | Rừng Tối | Darkwoods |
| 咒术师 | Mỹ Nhân | Enchantress |
| 厂长 | Tro Địa Ngục | Hell Ember |
| 鹿头 | Kẻ Gác Rừng | Game Keeper |
| 红蝶 | Geisha | |
| 黄衣之主 | Trùm Áo Vàng | The Feaster |
| 宿伞之魂 | Hồn Dù Tạ | Wu Chang |

地图名与个别较新的角色未收录于越南语 wiki，采用游戏内英文名或通用译法（如 `Hullabaloo`、
`Bartender`），可在 `index.html` 的 `I18N` 词典里直接修改。

## 怎么改

界面文字全部集中在 `index.html` 顶部的 `const I18N = { ... }` 词典里（中 → 越），
改完保存刷新即可。中文原文对照 <https://pil-tactical-friend.ok.kimi.link/>。

## 致谢

- 原作与数据：**北京大学第五人格赛事（PIL）**
- 越南语翻译与本地化：**Steam_LILITALES**
- 原版作者已授权个人本地化并要求注明来源，本项目已署名。
