# 歌姬与背景音轨数据库

在这里存放歌姬(vocal)与背景音轨(music)配置文件，这些配置将会在[演示站](https://uta.mrxiaom.top/)的 `: 选择 :` 菜单中显示。

+ 歌姬示例配置 [mikuv4x](vocal/mikuv4x.json) - daniwell 制作，MrXiaoM 翻制
+ 背景音轨示例配置 [mikutap](music/mikutap.json) - daniwell 制作，MrXiaoM 翻制

可视化编辑器正在编写中，在编写完成之前只能先这样手动编辑啦。

## 自动选择参数

在网址添加 query 参数即可在歌姬、背景音轨列表加载完成后自动选中。目前只支持选中预设的歌姬或背景音轨，不支持使用自定义。

+ `vocal=歌姬` 选中歌姬
+ `music=背景音轨` 或 `tracks=背景音轨` 选中背景音轨

以下是几个示例
```
https://uta.mrxiaom.top/?vocal=Warma
https://uta.mrxiaom.top/?vocal=蒼姫ラピス&tracks=mikutap
```
