# PackMakerLite

https://metin2.dev/topic/20776-eterpack-archiver-packmakerlite/

https://metin2.dev/topic/2482-how-to-unpack-official-patches/#comment-16854
https://metin2.dev/docs/pages/file-formats/eterpack-r9/

PackMakerLite (PML) 支持类型 0-1-2-3-4-5-6。

总而言之，metin2 类型的处理如下：

- 类型 0-仅存储（无加密/压缩；可以从 .epk 中完全读取）
- 类型 1-压缩-lzo（文件）
- 类型 2-压缩并加密-xtea(lzo(file))
- 类型 3-使用 Panama 加密-您必须在 panama/ 文件夹中保存一个服务器端的 .iv 密钥。（内容仅在身份验证阶段后可读）官方仅将其用于 patch2。
- 类型 4-使用混合密码加密（cshybridcrypt）-您必须在服务端 package/ 文件夹中保存一个 .dat 密钥服务器端。（内容仅在身份验证阶段后可读）几乎所有的 metin2_patch 文件。
- 类型 5-与类型 4 类似，但还提供了服务器端地图/<map_name>。（只有以玩家身份访问 <map_name> 地图后才可读取内容）官方仅将其用于地下墓穴数据。
- 类型 6-压缩和加密-xtea(snappy(file))


已知的 EterPack 类型
型号	描述
类型 0   该文件是 RAW，没有压缩或加密。
类型 1	该文件使用 LZO 压缩，但不使用 XTEA。
类型 2	该文件使用 LZO 压缩，然后使用 EterPack 内容密钥通过 XTEA 加密。（换句话说，就是 MCOZ CryptedObject）
类型 3	该文件使用巴拿马 加密
类型 4	混合加密
类型 5	带有额外数据的HybridCrypt
类型 6	该文件使用 Snappy 压缩，然后使用 EterPack 内容密钥通过 XTEA 加密。（换句话说，就是 MCSP CryptedObject）

### 安装

以管理员运行 “install.bat”

其设置（xtea 键、扩展、要使用的包类型）可以在 PackMakerLite.json 中更改：

### 配置文件放置

默认配置文件放在 .eix 文件所在目录
假如打包 root，它将按以下顺序搜索设置：
- 'root.json' (<packname>.json)
- 'PackMakerLite.json'
- 'C:\Users\Marty\root.json' (%userprofile%/<packname>.json)
- 'C:\Users\Marty\PackMakerLite.json' (%userprofile%/PackMakerLite.json)

### 解读
PackMakerLite_p.bat 打包命令
PackMakerLite_u.bat 解包命令
PackMakerLite_PackAllDirectories.bat  打包所有
PackMakerLite_UnpackAll.bat           解包所有

```
{
// !!! 有些选项最好保留注释！否则它们会覆盖命令行参数！

// 设置 .log 文件的名称：
//"log_name":"PackMakerLite",

// 设置 cs .dat 文件的前缀：
//"cs_name":"",

// 忽略以下特定文件名
"ignore_full_name": [".git", ".svn", ".vs", "desktop.ini"],

// 忽略这些特定文件扩展名
"ignore_file_extension": ["bak", "db", "wdp"],

// 将每个 FiLeName 转换为小写的“filename”
"force_filename_lowercase": false,

// 如果 pack_type_by_list 中没有匹配的规则，则使用此包类型
"default_pack_type": 2,

// 根据文件扩展名指定包类型
"pack_type_by_list": [
/*commented
["mss", 0],
["mse", 1],
["msf", 2],
["spt", 0],
["atr", 1],
["dds", 2],
["raw", 0],
["wtr", 1],
["mde", 2],
["tga", 0],
["txt", 1],
["msk", 2],
["msa", 0],
["msm", 1],
["py", 2]*/
],

// 使用 parallel 或 --parallel
//"parallel":true,

// 如果为 true（--hiddenfiles 为 true，--skipignorefiles 为 false），则打包隐藏文件（.XXX 或不可见）
//"hidden_files":true,

// 默认 eterpack/eterpack.cpp 加密
"eter_pack_index_ext":".eix",
"eter_pack_data_ext":".epk",
"eter_pack_index_key": [
45129401,
92367215,
681285731,
1710201
],
"eter_pack_data_key": [
78952482,
527348324,
1632942,
486274726
],

// magic 未加密块
"eter_magic_epkd":"EPKD",
// magic 加密块
"eter_magic_mcoz":"MCOZ",
// magic type6 加密块
"eter_magic_mcsp":"MCSP"
}
```


### 作者

Thanks also to:
blackdragonx61 / Mali-type4-5 extract code / type 6 compress code
metin2team-type6 extract code

By martysama0134