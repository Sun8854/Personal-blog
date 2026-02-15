# 标签插件手册（MEOW）

本分册用于回答“如何使用 MEOW 内置标签插件”的问题。

## 何时引用本分册
- 用户要求特定插件语法与参数
- 用户需要可复制的最小示例

## Note 信息框
```markdown
{% note pink %}
任意内容。
{% endnote %}
```

可选样式：`pink`/`yellow`/`blue`/`green`/`purple`/`light`

## Fold 折叠块
```markdown
{% fold "标题" blue open %}
任意内容。
{% endfold %}
```

参数说明：
- 标题必填；含空格需加引号
- `style` 可选同 Note
- `open` 表示默认展开

## Button 按钮
```markdown
{% button %}
- name: Meow 主题仓库
  url: https://github.com/chanwj/hexo-theme-meow
  desc: 主题源码
  icon:
{% endbutton %}
```

## Tabs 选项卡
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

参数说明：
- `demo` 为模块唯一 id
- `1` 为默认打开的选项卡索引

## Timeline 时间线
```markdown
{% timeline "2026" %}
<!-- timeline 2 月 -->
主题更新记录。
<!-- endtimeline -->
{% endtimeline %}
```

## Title 居中标题
```markdown
{% title '第一章：开始' %}
```

## Fiction 作品信息
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

## Music 音乐播放器
```markdown
{% music 1,local %}
- name: 歌曲
  artist: 歌手
  url: https://example.com/song.mp3
  cover: https://example.com/cover.jpg
  lrc:
{% endmusic %}
```

提示：如仅在单篇使用播放器，可在 Front-matter 加 `music: true`，并关闭全局播放器。
