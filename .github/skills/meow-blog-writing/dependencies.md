# 依赖与注意事项（MEOW）

本分册用于提醒用户某些功能需要额外依赖或注意事项。

## 依赖插件
- `hexo-wordcount`: 字数统计与阅读时长
- `image-size`: 本地相册需要
- `hexo-blog-encrypt`: 加密相册需要

## 常见注意事项
- 摘要优先级：`excerpt` > `<!-- more -->` > 自动摘要
- `cover` 仅影响文章封面，归档页显示由 `thumbnail` 控制
- `toc`、`indent` 可单篇覆盖主题设置
- 相册集页面必须命名为 `albums`，友链页面必须命名为 `friends`
