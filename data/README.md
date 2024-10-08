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

## vocal 歌姬配置文件格式

```json5
{
    // 媒体文件列表，沿用 mikutap 固定格式 索引.mp3
    // 索引从 0 开始，最多支持 32 个文件
    "media": {
        // 最好以 base64 形式存储，以免链接失效导致无法使用
        "0.mp3": "data:audio/mp3;base64,(中间省略)"
        // 后面省略
    },
    // 覆写画面颜色列表 (可选选项)
    // 歌姬的优先级比背景音轨高，如果歌姬有该选项，优先使用歌姬的选项
    "color_map": [ "#FFFFFF", "#000000", "#232323" ],
    // 暂不清楚详细用途的数值，按作用猜测为 delay(延时)
    "d_value": {
        // 默认值
        "default": 0.05,
        // 某个媒体文件的特殊值
        "6.mp3": 0.08
    },
    // 媒体音量调整
    "volume": {
        // 默认值
        "default": 1,
        // 某个媒体文件的特殊值
        "1.mp3": 1.3
    }

}
```

## tracks 背景音轨配置文件格式

```json5
{
    // 调整 bpm (播放速度)
    "bpm": 140,
    // 轨道列表，背景音乐长度按音符最多的轨道计算
    "tracks": [
        {
            // 非必要选项，用于提示编辑者这个轨道是什么轨道
            "comment": "鼓组",
            // 是否循环，如果开启，该轨道的音符将会按音乐长度填满整个轨道
            "loop": true,
            // 轨道内的音符列表，-1表示不发声，其余数字则使用 media 中的 数字.mp3 音频
            "notes": [
                0,1,2,1
            ]
        },
        {
            "comment": "钢琴",
            "notes": [
                3,4,4, 3,4,4, 3,4,4, 3,4,4, 3,4,3,4,
                5,6,6, 5,6,6, 5,6,6, 5,6,6, 5,6,5,6,
                7,8,8, 7,8,8, 7,8,8, 7,8,8, 7,8,7,8,
                9,10,10, 9,10,10, 9,10,10, 9,10,10, 9,10,9,10
            ]
        }
    ],
    // 媒体文件列表，沿用 mikutap 固定格式 索引.mp3
    // 索引从 0 开始，加多少都行，为了文件大小着想，最好不要无脑叠素材，用不到的就删掉
    "media": {
        // 最好以 base64 形式存储，以免链接失效导致无法使用
        "0.mp3": "data:audio/mp3;base64,(中间省略)"
        // 后面省略
    },
    // 覆写画面颜色列表 (可选选项)
    // 歌姬的优先级比背景音轨高，如果歌姬有该选项，优先使用歌姬的选项
    "color_map": [ "#FFFFFF", "#000000", "#232323" ],
    // 媒体音量调整
    "volume": {
        // 默认值
        "default": 1.2,
        // 某个媒体文件的特殊值
        "1.mp3": 0.6
    }
}
```
