# Legalize — 中华人民共和国宪法

> 中国宪法历史文献作为 Git 仓库 — 每部宪法是一个分支，每次修正是一个 commit。

本项目仿照 [legalize-dev/legalize-es](https://github.com/legalize-dev/legalize-es) 项目，旨在以 Git 版本控制的方式管理中华人民共和国宪法的发展历史。

## 分支结构

| 分支 | 内容 | 通过日期 |
|------|------|----------|
| `main` | 1982年宪法 + 5次修正案 | 1982-12-04 |
| `constitution-1982` | 1982年宪法原始版本 | 1982-12-04 |
| `constitution-1978` | 1978年宪法 | 1978-03-05 |
| `constitution-1975` | 1975年宪法 | 1975-01-17 |
| `constitution-1954` | 1954年宪法 | 1954-09-20 |
| `common-program` | 共同纲领 | 1949-09-29 |

## 修正案 Commit 历史

```bash
git log --oneline main

2708284 2018年宪法修正案
fdca68b 2004年宪法修正案
6d223dd 1999年宪法修正案
facefa2 1993年宪法修正案
5d43913 1988年宪法修正案
b86584f 添加 1982 年宪法原始版本
```

## 历次修正案

| 修正案 | 通过日期 | 主要修改 |
|--------|----------|----------|
| 第1次 | 1988-04-12 | 私营经济合法化；土地使用权可转让 |
| 第2次 | 1993-03-29 | 社会主义市场经济；多党合作制度 |
| 第3次 | 1999-03-15 | 依法治国；邓小平理论 |
| 第4次 | 2004-03-14 | 三个代表；人权入宪；私有财产保护 |
| 第5次 | 2018-03-11 | 习近平思想；党的领导；监察委员会；国家主席任期 |

## 快速开始

```bash
# 克隆项目
git clone https://github.com/legalize-cn/legalize-cn.git
cd legalize-cn

# 查看当前宪法（1982年+修正案）
git checkout main

# 查看1988年修正案内容
git show 5d43913

# 比较宪法版本差异
git diff constitution-1975 constitution-1982

# 查看共同纲领
git checkout common-program

# 查看某个条款的修改历史
git log -p --all -S "人权" -- cn-1982.md
```

## 目录结构

```
legalize-cn/
├── README.md
├── LICENSE
├── CHANGELOG.md              # 修正案概要
├── changelog/                # 修正案详细内容
│   ├── 1988-amendment.md
│   ├── 1993-amendment.md
│   ├── 1999-amendment.md
│   ├── 2004-amendment.md
│   └── 2018-amendment.md
├── common-program.md         # 共同纲领
├── cn-1954.md              # 1954年宪法
├── cn-1975.md              # 1975年宪法
├── cn-1978.md              # 1978年宪法
└── cn-1982.md              # 1982年宪法（含修正案）
```

## 数据来源

- 中国人大网 (www.npc.gov.cn)
- 中国政府网 (www.gov.cn)
- 国家法律法规数据库 (flk.npc.gov.cn)

## 相关项目

- [legalize-dev/legalize-es](https://github.com/legalize-dev/legalize-es) - 西班牙法律 Git 仓库
- [legalize-dev/legalize](https://github.com/legalize-dev/legalize) - Legalize 主项目

## 许可证

- 宪法文本：公共领域（政府官方文件）
- 项目结构、代码和文档：MIT License
