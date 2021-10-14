---
title: VCL-Book Starter
---

# Test
## 文档结构

书籍的所有页面在src/pages/book下，基本结构为：
```
index.md
chapter1
  - index.md
  - 01-foo.md
  - 02-bar.md
...
```
最外层的index.md为整个书籍的简介，点击右上角的<icon-carbon-book/>图标进入的就是这个界面，其中的目录是自动生成的，但是每次更新目录结构之后都需要重新生成，不能热更新。各个章节的目录名请使用chapter[1-9]，这是为了保证自动生成目录时顺序正确。各个章节的标题在各个章节下的index.md里，


## 图片

### 三级标题测试

#### 四级标题测试

## 代码
## 3D动画

<div class="text-center">
  <Three />
</div>

## 数学公式
