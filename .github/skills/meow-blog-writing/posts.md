# 文章写作指南（MEOW）

本分册用于回答“如何写文章/如何设置文章 Front-matter/如何写摘要与封面”等问题。

## 何时引用本分册
- 用户询问文章 Front-matter 字段含义与优先级
- 用户想要封面、摘要、目录、置顶、语言等效果
- 用户想要模板或最小可用示例

## 创建文章
- 命令：`hexo new post "标题"`
- 默认生成文件：`source/_posts/<slug>.md`

## 推荐 Front-matter 模板
```yaml
---
title: 文章标题
date: 2026-02-15 10:00:00
tags: [Hexo, Meow]
categories: [记录]
cover: https://example.com/cover.jpg
excerpt: 这里是手动摘要
sticky: 5
toc: true
indent: false
thumbnail: true
lang: zh-CN
author: 你的名字
---
```

## 字段说明与优先级
- `excerpt`: 手动摘要优先级最高
- `<!-- more -->`: 置于正文中用于截断摘要
- 自动摘要：未配置前两者时，按 `post.excerpt_length` 自动截取

优先级顺序：
1. Front-matter `excerpt`
2. 正文 `<!-- more -->`
3. 自动摘要

## 封面与缩略图
- `cover`: 首页文章卡片封面图
- `thumbnail`: 归档页是否显示封面（单篇可覆盖主题配置）

## 目录与缩进
- `toc`: 单篇开/关文章目录
- `indent`: 单篇开/关段首缩进

## 置顶文章
- `sticky`: 数字越大优先级越高
- 若与主题或其他插件冲突，保持数字不同以便排序

## 语言
- `lang`: 单页语言覆盖，例如 `en` 或 `zh-CN`

## 常见示例
### 有摘要与封面
```yaml
---
title: 我的封面文章
date: 2026-02-15 10:00:00
cover: https://example.com/cover.jpg
excerpt: 这是一个简短摘要。
---
```

### 使用 more 截断摘要
```markdown
这里是摘要内容。
<!-- more -->
这里是正文内容。
```

## 输出建议
回答应包含：
- 文章 Front-matter 模板
- 关键字段含义
- 摘要优先级说明
