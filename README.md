# 用前须知

本文是关于 **DiffSinger 声库：Ria / 狸安** 的特性、使用规范及制作用参考的说明。请在**仔细阅读本文且同意相关条款后**再进行使用。

## 更新日志

- 2025.01.18

  - 增加 [TPSE](https://github.com/KakaruHayate/DiffSinger/tree/TPSE) 分支的声库版本。该版本未新增采样及更改标记。详情请看 [Release](https://github.com/RibosomeK/RiaDiffSinger/releases/tag/v0.4-tpse) 页面。

- 2025.01.14

  - 增加自动音高和微调声码器两个扩展包，适用于 [Ria-DiffSinger-v0.4](https://github.com/RibosomeK/RiaDiffSinger/releases/tag/v0.4) 以及 [Ria-DiffSinger-v0.4-lynxnet](https://github.com/RibosomeK/RiaDiffSinger/releases/tag/v0.4-lynxnet)， 使用方式参见 [Release](https://github.com/RibosomeK/RiaDiffSinger/releases/tag/v0.4-dlc) 页面。

- 2024.09.15

  - 增加 [multi-dict](https://github.com/openvpi/DiffSinger/discussions/203) 分支的声库版本。该版本未新增采样及更改标记。该版本使用需求 OpenUtau 版本 v0.1.543.0 及以上。

- 2024.09.14
  - 增加 [lynxnet](https://github.com/openvpi/DiffSinger/pull/200) 分支的声库版本。该版本未新增采样及更改标记。

---

1. [声库特性](#声库特性)
   1. [基本信息](#基本信息)
   1. [音素（暂行）](#音素暂行)
      1. [元音](#元音)
      1. [音尾](#音尾)
      1. [辅音](#辅音)
      1. [特殊音素](#特殊音素)
   1. [字典文件](#字典文件)
1. [使用方式](#使用方式)
1. [使用规范](#使用规范)
1. [已知不符预期的表现（Bugs）](#已知不符预期的表现bugs)
1. [致谢](#致谢)

---

## 声库特性

### 基本信息

姓名：Ria / 狸安

收录语种：**粤语（1hr）**、日语（30mins）、普通话（30mins）

中之人：RibosomeK

音素方案：类 ARPABET

训练步长：76k

唱法模型：音素长度（duration）、张力（tension）、发声（voicing）、气声（breathiness）

可用音域：A2~G#4

试听曲：

- 粤语：[Dec.](https://www.bilibili.com/video/BV1KT5JznE7R)、[詩](https://www.bilibili.com/audio/au4489066)、[視愛睇驗](https://www.bilibili.com/video/BV1HLpSexEWj)
- 普通话：[火星沼泽](https://www.bilibili.com/video/BV1GKpceMEPt)
- 日语：[セブンティーナ](https://www.bilibili.com/video/BV1r7ifYAENK/)、[少女レイ](https://www.bilibili.com/audio/au4494584)、[ドーナツホール](https://www.bilibili.com/audio/au4498425)

### 音素（暂行）

---

<del>**DiffSinger 已正式推出[多语言字典分支版本](https://github.com/openvpi/DiffSinger/tree/multi-dict)及其[说明](https://github.com/openvpi/DiffSinger/discussions/203)，预计在 OpenUTAU 对其正式后会对现行音素方案进行少量修改。**</del>

**2024.08.22 更新：关于多字典分支，经测试后预计后续更新不会更新适配，而是保留现行合并方案。**

---

本声库的音素方案修改自 [ARPABET](https://en.wikipedia.org/wiki/ARPABET)，并借用了 [X-SAMPA](https://en.wikipedia.org/wiki/X-SAMPA) 中的一些概念，在只包含小写字母和半角分号 `:` 的情况写囊括了粤语、日语、普通话、英语的发音。其中**元音以 2 位小写字母表示；辅音以 1~2 位小写字母表示；音尾以半角分号 `:` 加 1 位小写字母表示**。不同于原 ARPABET 方案的地方会以星号 <b>`*`</b> 标记。另外包括的特殊音素统一为 DiffSinger 保留音素的格式，即双大写字母。

**注：本声库不包含英语采样及其独占音素！**

#### 元音

| 音素记号 | 粤语        | 普通话     | 日语      | 英语                 |
| -------- | ----------- | ---------- | --------- | -------------------- |
| aa       | 啊 **aa**   | 啊 **a**   | あ **a**  | l**o**t              |
| ae       | 不 b**a**t  |            |           |                      |
| ah       | 包 b**aa**u | 包 b**a**o |           | str**u**t            |
| ax       |             |            |           | **a**bout            |
| ea       | 石 s**e**k  |            |           | tr**a**p<b>\*</b>    |
| eh       | 啤 b**e**   | 叶 y**e**  | え **e**  | dr**e**ss            |
| eo       | 春 c**eo**n |            |           |                      |
| er       |             | 儿 **e**r  |           | b**ir**d             |
| ex       |             | 的 d**e**  |           |                      |
| ih       | 星 s**i**ng | 杯 b**e**i |           | b**i**t              |
| ir       |             | 只 zh**i** |           |                      |
| ix       |             | 字 z**i**  |           |                      |
| iy       | 衣 j**i**   | 衣 y**i**  | い **i**  | b**ea**t             |
| nn       |             |            | ん **nn** |                      |
| oa       | 波 b**o**   |            |           | th**ou**ght<b>\*</b> |
| oe       | 朵 d**oe**  |            |           |                      |
| oh       |             | 罗 lu**o** | お **o**  |                      |
| ox       | 寳 b**o**u  | 凑 c**o**u |           | l**o**w<b>\*</b>     |
| uh       |             |            |           | f**oo**t             |
| uw       | 烏 w**u**   | 乌 w**u**  |           | g**oo**se            |
| ux       |             |            | う **u**  |                      |
| vw       | 與 j**yu**  | 与 y**u**  |           |                      |

#### 音尾

| 音素记号 | 粤语        | 普通话      | 日语 | 英语              |
| -------- | ----------- | ----------- | ---- | ----------------- |
| :g       | 倉 co**ng** | 仓 ca**ng** |      | si**ng**<b>\*</b> |
| :i       | 拜 baa**i** | 白 ba**i**  |      | bu**y**<b>\*</b>  |
| :k       | 白 ba**k**  |             |      |                   |
| :l       |             |             |      | a**ll**<b>\*</b>  |
| :m       | 參 caa**m** |             |      | sa**me**<b>\*</b> |
| :n       | 產 caa**n** | 班 ba**n**  |      | sa**n**d<b>\*</b> |
| :p       | 輯 ca**p**  |             |      |                   |
| :r       |             |             |      | a**r**t<b>\*</b>  |
| :t       | 不 ba**t**  |             |      |                   |
| :u       | 包 baa**u** | 包 ba**o**  |      | lo**w**<b>\*</b>  |

#### 辅音

| 音素记号 | 类型      | 粤语        | 普通话      | 日语       | 英语                 |
| -------- | --------- | ----------- | ----------- | ---------- | -------------------- |
| b        | stop      | 巴 **b**aa  | 巴 **b**a   |            |                      |
| bb       | stop      |             |             | ば **b**a  | **b**at<b>\*</b>     |
| c        | affricate | 擦 **c**aat | 擦 **c**a   |            |                      |
| ch       | affricate |             | 吃 **ch**i  |            |                      |
| d        | stop      | 打 **d**aa  | 打 **d**a   |            |                      |
| dd       | stop      |             |             | だ **d**a  | **d**ig<b>\*</b>     |
| dh       | fricative |             |             |            | **th**is             |
| dx       | liquid    |             |             |            | be**tt**er<b>\*</b>  |
| f        | fricative | 發 **f**aat | 发 **f**a   |            | **f**ar              |
| fh       | fricative |             |             | ふ **f**u  |                      |
| g        | stop      | 家 **g**aa  | 改 **g**ai  |            |                      |
| gg       | stop      |             |             | が **g**a  | **g**et<b>\*</b>     |
| h        | fricative | 哈 **h**aa  | 哈 **h**a   | は **h**a  | **h**i<b>\*</b>      |
| j        | affricate |             | 家 **j**ia  |            |                      |
| jx       | affricate |             |             | ち **ch**i | **ch**urch<b>\*</b>  |
| jh       | affricate |             |             |            | **j**udge            |
| jz       | fricative |             |             | じ **j**i  |                      |
| k        | stop      |             |             | か **k**a  | **k**it              |
| kh       | stop      | 卡 **k**aa  | 卡 **k**a   |            |                      |
| l        | liquid    | 啦 **l**aa  | 啦 **l**a   |            | **l**ie              |
| m        | nasal     | 馬 **m**aa  | 吗 **m**a   | ま **m**a  | **m**y               |
| n        | nasal     | 那 **n**aa  | 那 **n**a   | な **n**a  | **n**ight            |
| ng       | nasal     | 啞 **ng**aa |             | ガ **ng**a |                      |
| p        | stop      |             |             | ぱ **p**a  | **p**et              |
| ph       | stop      | 怕 **p**aa  | 怕 **p**a   |            |                      |
| q        | affricate |             | 恰 **q**ia  |            |                      |
| r        | liquid    |             |             | ら **r**a  |                      |
| rx       | liquid    |             | 日 **r**i   |            | **r**ead             |
| s        | fricative | 沙 **s**aa  | 撒 **s**a   | さ **s**a  | **s**ad              |
| sh       | fricative |             | 是 **sh**i  |            | **sh**e              |
| t        | stop      |             |             | た **t**a  | **t**ed              |
| tf       | fricative |             |             |            | **th**ing<b>\*</b>   |
| th       | stop      | 他 **t**aa  | 他 **t**a   |            |                      |
| ts       | affricate | 渣 **z**aa  | 杂 **z**a   | つ **ts**u | ca**ts**<b>\*</b>    |
| v        | fricative |             |             |            | **v**ase             |
| w        | semivowel | 哇 **w**aa  | 哇 **w**a   | わ **w**a  | **wh**ite            |
| x        | fricative |             | 下 **x**ia  | し **sh**i |                      |
| y        | semivowel | 也 **j**aa  | 亚 **y**a   | や **y**a  | **y**et              |
| yv       | semivowel | 魚 **j**yu  | 元 **yu**an |            |                      |
| z        | fricative |             |             | ざ **z**a  | **z**oo              |
| zh       | affricate |             | 只 **zh**i  |            |                      |
| zr       | fricative |             |             |            | mea**su**re<b>\*</b> |

#### 特殊音素

- `SP`：DiffSinger 保留音素，表示空白部分
- `AP`：DiffSinger 保留音素，表示呼吸音
- `CL`：表示类似喉塞音的部分（不推荐使用）
- `RP`：表示语尾息（不推荐使用，使用时可搭配气声参数使用）

### 字典文件

本声库一共包含了 4 份字典：`dsdict.yaml`、`dsdict-zh-yue.yaml`、`dsdict-zh.yaml`、`dsdict-ja.yaml`，分别对应默认音素器 `DIFFS`、粤语音素器 `DIFFS ZH-YUE`、中文音素器 `DIFFS-ZH`、日语音素器 `DIFFS-JA`。

默认字典 `dsdict.yaml` 为了区分三种不同的语言，分别使用了粤拼（JyutPing）、注音（ㄅㄆㄇㄈ）、平假名（ひらがな）作为输入方式。在需要混用不同语言的情况下可以使用默认音素器 `DIFFS` 。一般情况下不推荐使用。

粤语字典 `dsdict-zh-yue.yaml` <del>内除了包含粤拼作为输入方式外，还包含了大陆地区通用规范汉字约 8000 个，香港地区常用字字表约 4700 个，即还可以输入汉字字符作为歌词。</del> 由于 OpenUTAU 自带 G2P，先仅包含粤拼。使用时请选择 `DIFFS ZH-YUE` 作为音素器，并请注意由于多音字的存在，使用汉字字符作为歌词输入不可能百分百得到合适的发音，还请手动调整。

普通话字典 `dsdict-zh.yaml` <del>则以拼音（pinyin）、注音、汉字字符作为输入方式。其中汉字字符包含大陆地区通用规范汉字约 8000 个，台湾地区国字标准字体表-常用（甲表）约 4800 个，台湾地区国字标准字体表-次常用（乙表）约 6300 个。</del> 同样改用 OpenUTAU 自带的 G2P。使用时请选择 `DIFFS-ZH` 作为音素器，同样的请注意，使用汉字字符作为歌词输入时可能存在的不合适发音。

日语字典 `dsdict-ja.yaml` 包含了平假名和一部分用作外来语的片假名，以及其对应的罗马字（romaji）。使用时请选择 `DIFFS-JA` 作为音素器。

## 使用方式

1. 编辑器请使用 [OpenUTAU](https://github.com/stakira/OpenUtau) 0.1.529 及以上的版本
2. 请前往 [Release](https://github.com/RibosomeK/RiaDiffSinger/releases) 下载任一版本的声库`（Ria-*.zip）`，当前推荐 lynxnet 分支版本
3. 请下载声码器 [NSF-HiFiGAN](https://github.com/openvpi/vocoders/releases)，下载文件后缀名为 `.oudep` 的文件，并作为依赖安装到 OpenUTAU 中。安装方式为在 OpenUTAU 的编辑器界面的菜单栏上选择 `工具 -> 安装依赖项（.oudep)`，并选择方才下载的声码器进行安装
4. 在 OpenUTAU 的编辑器界面的菜单栏上选择 `工具 -> 安装歌手`，并选择声库压缩包，按照提示，在出现 `歌手类型` 时选择 `diffsinger` 进行安装
5. 更详细的使用方式请参阅 [OpenUTAU 文档](https://opensynth.miraheze.org/wiki/OpenUTAU/%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95)

## 使用规范

1. 本声库使用规范默认采用**白名单**，只有本节提及的使用方式是被允许的
2. 经该声库直接输出的音频文件，**可以**直接或经过重采样、混音、母带（以下简称加工），以媒体方式（以下简称媒体）进行传播展示，**且需要**注明声库的任一姓名。
3. 加工过程中所使用插件、效果器的类型**不能**包括 RVC（real-time voice changer）、SVC（singing voice changer）等具有变声器效果的软件
4. 媒体**不能**包含或用于制造：hate speech（仇恨发言）、spamming（骚扰）、trolling（钓鱼式发言）、fighting words（引战）

## 已知不符预期的表现（Bugs）

1. 开头元音可能会带有爆破辅音，可以在前面添加音符 `AP` 解决
2. 部分辅音可能会出现发声不明显，如 `[n]`、`[l]`、`[h]`，手动调整长度可能会改善该状况
3. 部分开头辅音可能会过短，请手动调节长度
4. 长音符音尾部分可能会过长，请手动调节长度
5. 部分情况下介音长度可能会过长，请手动调节长度

## 致谢

- [DiffSinger](https://github.com/openvpi/DiffSinger)
- [DiffSinger 教程](https://openvpi-docs.feishu.cn/wiki/KmBFwoYDEixrS4kHcTAcajPinPe)
- [OpenUTAU](https://github.com/stakira/OpenUtau)
- [OpenCC](https://github.com/BYVoid/OpenCC)
- [pytextgrid](https://github.com/kylebgorman/textgrid)
- [pypinyin](https://github.com/mozillazg/python-pinyin)
- [pycantonese](https://pycantonese.org/jyutping.html)
- [pyzhuyin](https://pypi.org/project/pyzhuyin/)
- [汉字标准](https://github.com/kitty-panics/cn-tables)
- [漢語多功能字庫](https://humanum.arts.cuhk.edu.hk/Lexis/lexi-mf/)
