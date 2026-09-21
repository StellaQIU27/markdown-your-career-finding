# Markdown Your Career Finding

一个给求职季用的投递台账：同时记录**企业秋招、博后申请、高校教职**三条线的投递情况和推进情况。手机上能直接打开和编辑，随时导出成 Markdown。

A lightweight job-search tracker for people running several tracks at once — industry roles, postdoc applications and faculty positions. Phone-first, no backend, exports to Markdown.

## 三种用法

| 方式 | 适合 | 文件 |
|---|---|---|
| 网页版 | 手机 / 电脑随手记，状态一键切换 | `index.html` |
| Markdown 模板 | 喜欢纯文本、想放进笔记或 Git 仓库 | `templates/tracker.md` |
| Excel 表 | 习惯表格、需要筛选和统计 | `python3 scripts/make_xlsx.py` 生成 |

## 网页版

直接用浏览器打开 `index.html`，或者开启 GitHub Pages 后用手机访问。

- 三个分类：企业 / 博后 / 高校教职，每类的字段名会跟着变（公司 ↔ 单位 ↔ 学校，岗位类型 ↔ 合作导师）。
- 状态下拉直接改，改动会自动在"推进记录"里记一笔；改成"已投递"时自动补上投递日期。
- 每条记录有一个推进时间线：投递、笔试、每一轮面试都可以记。
- 顶部按"待投 / 已投待回复 / 面试中 / Offer / 已结束"分组计数，点一下就是筛选。
- **导出 Markdown**：生成三张表 + 每条记录的时间线，粘进任何 `.md` 文件。
- **导出 / 导入 JSON**：换设备时搬数据用。

数据只保存在**当前浏览器的 localStorage** 里，不会上传到任何地方。代价是：换手机或清理浏览器数据前，记得先导出 JSON 备份。

## 状态口径

`待投递 → 待提交 → 已投递 → 简历筛选中 → 笔试/测评 → 一面 → 二面 → 三面/终面 → HR面 → Offer`，结束态为 `未通过` / `已放弃`。

## Excel 版

```bash
pip install openpyxl
python3 scripts/make_xlsx.py my-tracker.xlsx
```

生成四个工作表：总览（公式自动统计各状态数量）、企业秋招、博后申请、高校教职。状态、优先级、岗位类型是下拉菜单，整行按状态着色。

## 隐私

仓库里只有工具和示例数据。不要把自己的真实投递记录、简历或联系方式提交到公开仓库。

## License

MIT
