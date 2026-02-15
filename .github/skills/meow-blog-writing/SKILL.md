---
name: meow-blog-writing
description: 指导用户使用 MEOW 主题编写 Hexo 文章与页面，包含 Front-matter 字段、摘要规则与主题标签插件。适用于用户询问如何写文章或创建 MEOW 专属页面（标签、分类、友链、动态、相册等）时。
---

# 技能说明

当用户询问如何用 MEOW 主题写文章/页面，或如何使用 MEOW 标签插件时使用此技能。回答要简洁、可执行。
如需更详细步骤或完整示例，可按需引用本文档后面的分册：
- [文章写作指南](./posts.md)
- [页面创建指南](./pages.md)
- [标签插件手册](./plugins.md)
- [依赖与注意事项](./dependencies.md)

## 目标
- 提供准确的 MEOW Front-matter 选项与默认含义。
- 清晰说明摘要与封面的优先级与表现。
- 给出可直接复制的文章、页面、标签插件示例。
- 必要时提醒所需数据文件或依赖。

## 工作流程
1. 先确认需求：写文章、建页面，或使用标签插件。
2. 需要时给出对应的 Hexo 命令与 Front-matter 模板。
3. 补充 MEOW 特有字段并说明优先级规则。
4. 若是特色页面，指明 `source/_data` 或 `source/<page>` 中的必要文件。
5. 若是标签插件，给出最小语法与参数说明。
6. 用户需要深入配置时，引导查看对应分册并给出示例。

## Front-matter 指南（MEOW）
文章/页面常用字段：
- `title`, `date`, `tags`, `categories`
- `cover`: 文章封面图链接
- `excerpt`: 手动摘要文本
- `toc`: 本页是否启用目录
- `indent`: 段首缩进（覆盖主题全局设置）
- `thumbnail`: 归档页是否显示封面
- `sticky`: 首页置顶优先级（数值越大优先级越高）
- `lang`: 单页语言覆盖
- `author`: 覆盖作者名

### 摘要优先级
1. Front-matter 中的 `excerpt`
2. 正文中的 `<!-- more -->`
3. 自动截取到 `post.excerpt_length`

## 文章示例
```yaml
---
title: 我的第一篇 Meow 文章
date: 2026-02-15 10:00:00
tags: [Hexo, Meow]
categories: [记录]
cover: https://example.com/cover.jpg
excerpt: 手动摘要示例。
toc: true
indent: false
sticky: 5
thumbnail: true
lang: zh-CN
---
```

## 特色页面
如需完整流程和数据文件示例，请优先引用 [页面创建指南](./pages.md)。
### 标签 / 分类
创建页面：
- `hexo new page categories`
- `hexo new page tags`

Front-matter：
```yaml
---
title: 分类
date: 2026-02-15 10:00:00
type: category
---
```
```yaml
---
title: 标签
date: 2026-02-15 10:00:00
type: tag
---
```

### 动态（短文）
- `hexo new page essay`
- Front-matter: `type: essay`
- 数据文件：`source/_data/essay.yml`

最小数据示例：
```yaml
essay_info:
  author:
    小橘猫: https://example.com/avatar.jpg
essay_list:
  - content: "喵喵喵，Hello Meow!"
    date: 2026-02-15 12:00:00
```

### 友情链接
- `hexo new page friends`
- Front-matter: `type: friends`
- 数据文件：`source/friends/friends.js`（包含分类与链接列表的 JS 对象）

### 相册
- `hexo new page albums`
- Front-matter: `type: albums`
- 数据文件：`source/_data/albums.yml`
- 本地相册图片放在 `source/images/albums/<albumName>/`

本地相册页 Front-matter：
```yaml
---
title: 本地相册
date: 2026-02-15 10:00:00
type: album
album: album01
password:
---
```

外链相册页 Front-matter：
```yaml
---
title: 外链相册
date: 2026-02-15 10:00:00
type: album
album: album02
album_type: 1
password:
---
```

## 标签插件
如需完整插件语法与参数说明，请引用 [标签插件手册](./plugins.md)。
### 信息框 Note
```markdown
{% note pink %}
任意内容。
{% endnote %}
```

### 折叠块 Fold
```markdown
{% fold "Title" blue open %}
任意内容。
{% endfold %}
```

### 按钮 Button
```markdown
{% button %}
- name: Meow 主题仓库
  url: https://github.com/chanwj/hexo-theme-meow
  desc: 主题源码
  icon:
{% endbutton %}
```

### 选项卡 Tabs
```markdown
{% tabs demo,1 %}
<!-- tab 第一栏 -->
内容 A
<!-- endtab -->
<!-- tab 第二栏 -->
内容 B
<!-- endtab -->
{% endtabs %}
```

### 时间线 Timeline
```markdown
{% timeline "2026" %}
<!-- timeline Feb -->
主题更新记录。
<!-- endtimeline -->
{% endtimeline %}
```

### 标题 Title
```markdown
{% title '第一章：开始' %}
```

### 作品信息 Fiction
```markdown
{% fmeta %}
type: 同人作品
fandom: 示例作品
relationship: A/B
character: A, B
rating: 1
warning: 主要角色死亡
status: N
{% endfmeta %}
```

### 音乐播放器 Music
```markdown
{% music 1,local %}
- name: 歌曲
  artist: 歌手
  url: https://example.com/song.mp3
  cover: https://example.com/cover.jpg
  lrc:
{% endmusic %}
```

## 相关依赖（按需提示）
- `hexo-wordcount`: 字数统计与阅读时长需要。
- `image-size`: 本地相册需要。
- `hexo-blog-encrypt`: 加密相册需要。

## 输出要求
提供：
- 正确的 Front-matter 与简洁说明
- 可直接复制的最小示例
- 必要的数据文件位置与结构
