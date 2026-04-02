# Legalize — 中华人民共和国宪法

> 中国宪法历史文献作为 Git 仓库 — 每部宪法是一个分支，每次修正是一个 commit。

本项目仿照 [legalize-dev/legalize-es](https://github.com/legalize-dev/legalize-es) 项目，旨在以 Git 版本控制的方式管理中华人民共和国宪法的发展历史。

## 概述

本仓库包含：

- **共同纲领** (1949年9月29日)
- **1954年宪法** (1954年9月20日)
- **1975年宪法** (1975年1月17日)
- **1978年宪法** (1978年3月5日)
- **1982年宪法** (1982年12月4日) 及历次修正案

## 分支结构

```
main                              ← 1982年宪法（含历次修正案）
├── common-program                ← 中国人民政治协商会议共同纲领 (1949)
├── constitution-1954             ← 第一部中华人民共和国宪法 (1954)
├── constitution-1975             ← 第二部宪法 (1975)
├── constitution-1978             ← 第三部宪法 (1978)
└── constitution-1982             ← 第四部宪法原始版本 (1982)
```

## 1982年后历次宪法修正案

| 修正案 | 通过日期 | 主要修改内容 |
|--------|----------|--------------|
| 第1次 | 1988年4月12日 | 私营经济合法化；土地使用权可转让 |
| 第2次 | 1993年3月29日 | 社会主义市场经济；家庭联产承包责任制 |
| 第3次 | 1999年3月15日 | 依法治国；邓小平理论；非公有制经济 |
| 第4次 | 2004年3月14日 | 三个代表重要思想；私有财产保护；人权入宪 |
| 第5次 | 2018年3月11日 | 习近平新时代中国特色社会主义思想；监察委员会；国家主席任期 |

## 快速开始

```bash
git clone https://github.com/legalize-cn/legalize-cn.git
cd legalize-cn

# 查看当前宪法（1982年+修正案）
git checkout main

# 查看1988年修正案
git log --oneline --all | grep 1988

# 查看宪法历史
git log --oneline main

# 比较两次修正案的差异
git diff <commit1> <commit2> -- cn-1982.md

# 查看共同纲领
git checkout common-program
```

## 目录结构

```
legalize-cn/
├── README.md
├── LICENSE
├── .gitignore
├── changelog/                     ← 修正案详细记录
│   ├── 1988-amendment.md
│   ├── 1993-amendment.md
│   ├── 1999-amendment.md
│   ├── 2004-amendment.md
│   └── 2018-amendment.md
├── common-program.md             ← 共同纲领
├── cn-1954.md                   ← 1954年宪法
├── cn-1975.md                   ← 1975年宪法
├── cn-1978.md                   ← 1978年宪法
└── cn-1982.md                   ← 1982年宪法（含修正案）
```

## 文件格式

每部宪法文件包含 YAML frontmatter：

```yaml
---
title: "中华人民共和国宪法"
identifier: "CN-1982"
type: "constitution"
adopted_date: "1982-12-04"
source: "全国人民代表大会"
jurisdiction: "cn"
---
```

## 数据来源

所有文本来自：

- 中国人大网 (www.npc.gov.cn)
- 中国政府网 (www.gov.cn)
- 国家法律法规数据库 (flk.npc.gov.cn)

## 相关项目

- [legalize-dev/legalize-es](https://github.com/legalize-dev/legalize-es) - 西班牙法律 Git 仓库
- [legalize-dev/legalize](https://github.com/legalize-dev/legalize) - Legalize 主项目

## 许可证

- 宪法文本：公共领域（政府官方文件）
- 项目结构、代码和文档：MIT License
