# 注意

2021年3月5日，官方更新了 Steam 版游戏，大幅改进了中文翻译，所以你不再需要这个补丁了。（而且这个补丁应该会和新版游戏不兼容）

# 汉化补丁下载

[0.2.2 先行版下载](https://github.com/JasonWei512/Shantae-and-the-Seven-Sirens-Chinese-Retranslation-Project/releases/download/0.2.2/localization.pak.zip) | [国内镜像](http://github.strcpy.cn/JasonWei512/Shantae-and-the-Seven-Sirens-Chinese-Retranslation-Project/releases/download/0.2.2/localization.pak.zip)

适用于 [Steam 版](https://store.steampowered.com/app/1191630/Shantae_and_the_Seven_Sirens/)，解压后覆盖 ```游戏目录/data/localization.pak```。

基本可用于游玩。已在游戏内测试过一轮，修改了部分语句的翻译，统一了部分标点。可能仍有极少数没被测试到的文本翻译和显示错误。

⚠注意：[有用户反映用了以后不能解锁成就。](https://github.com/JasonWei512/Shantae-and-the-Seven-Sirens-Chinese-Retranslation-Project/issues/3)

# 概述

[![生成汉化补丁](https://github.com/JasonWei512/Shantae-and-the-Seven-Sirens-Chinese-Retranslation-Project/workflows/%E7%94%9F%E6%88%90%E6%B1%89%E5%8C%96%E8%A1%A5%E4%B8%81%E3%80%80%E3%80%80/badge.svg)](https://github.com/JasonWei512/Shantae-and-the-Seven-Sirens-Chinese-Retranslation-Project/actions?query=workflow%3A%E7%94%9F%E6%88%90%E6%B1%89%E5%8C%96%E8%A1%A5%E4%B8%81%E3%80%80%E3%80%80)

Shantae and the Seven Sirens 的中文机翻过于严重，所以我重新翻译了一遍。最终目标是能成为游戏的官方中文文本。

如果发现错别字、翻译错误和文本显示错误，请在 [Github 的 issues](https://github.com/JasonWei512/Shantae-and-the-Seven-Sirens-Chinese-Retranslation-Project/issues) 中提出。

# 说明

游戏的文本位于 ```游戏目录/data/localization.pak``` 中。文件为二进制，每条文本以UTF8编码，之间用全零字节隔开。

文本对象中的各成员说明：
- Text：该条文本的内容
- OriginalText（可选）：英文原文文本
- StartAddress：这条文本的首个字节在 ```localization.pak``` 中的位置（从零开始数，用十进制表示）
- EndAddress：这条文本可用的最后一个字节的位置，即下一条文本首个字节的前两个字节的位置（为了让两条文本之间最少有一个零字节隔开，否则游戏中文本会出重复的Bug）
- MaxLength：这条文本以UTF8编码后允许的最大字节数（即：EndAddress - StartAddress + 1）
