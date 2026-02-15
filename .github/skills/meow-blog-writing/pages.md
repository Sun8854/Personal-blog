# 页面创建指南（MEOW）

本分册用于回答“如何创建分类/标签/友链/动态/相册”等 MEOW 特色页面。

## 何时引用本分册
- 用户询问创建分类、标签、友链、动态、相册页面
- 用户询问需要的 data 文件位置与结构
- 用户询问页面 Front-matter 应该如何写

## 分类与标签
### 创建页面
- `hexo new page categories`
- `hexo new page tags`

### Front-matter
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

## 动态（Essay）
### 创建页面
- `hexo new page essay`

### Front-matter
```yaml
---
title: 🐈动态
date: 2026-02-15 10:00:00
type: essay
---
```

### 数据文件
- 位置：`source/_data/essay.yml`

最小示例：
```yaml
essay_info:
  author:
    小橘猫: https://example.com/avatar.jpg
essay_list:
  - content: "测试说说~~Hello World!"
    date: 2026-02-15 12:00:00
```

## 友情链接
### 创建页面
- `hexo new page friends`

### Front-matter
```yaml
---
title: 🍻友情链接
date: 2026-02-15 10:00:00
type: friends
---
```

### 数据文件
- 位置：`source/friends/friends.js`

最小示例：
```js
const friendsData = {
  friends: [
    {
      class: { name: "小伙伴们", desc: "随机排列", random: true },
      list: [
        {
          name: "示例站点",
          url: "https://example.com",
          avatar: "https://example.com/avatar.jpg",
          desc: "一句话介绍"
        }
      ]
    }
  ]
};

module.exports = friendsData;
```

## 相册
### 创建相册集页面
- `hexo new page albums`

### Front-matter
```yaml
---
title: 📸相册集
date: 2026-02-15 10:00:00
type: albums
---
```

### 数据文件
- 位置：`source/_data/albums.yml`

最小示例：
```yaml
albums_list:
  album01:
    name: 本地相册
    cover: images/albums/album01/cover.jpg
    span: 2
  album02:
    name: 外链相册
    cover: https://example.com/cover.jpg
    images:
      图 1: https://example.com/1.jpg
      图 2: https://example.com/2.jpg
```

### 本地相册页面
```yaml
---
title: 本地相册
date: 2026-02-15 10:00:00
type: album
album: album01
password:
---
```

### 外链相册页面
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

### 本地图片目录
- `source/images/albums/<albumName>/`
