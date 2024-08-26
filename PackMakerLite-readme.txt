Run install.bat as admin OR copy the following files in "c:\windows\system32\":
 PackMakerLite.exe
 PackMakerLite_p.bat
 PackMakerLite_u.bat

To get menu integration, run:
 PML_Pack.add.reg
 PML_Unpack.add.reg

--------------------------------------
If you want to customize the tool,
 copy and edit PackMakerLite.json in the relative working directly
 (where the .eix files are present)
 (PackMakerLite.json.sample contains a sample of any customizable field)

If you want to customize only a specific pack (e.g. ETC),
 just rename it as <packname>.json (e.g. etc.json)

Since v2.3, you can globally load the json files from %userprofile%
 as well if the local ones are missing.
 (%userprofile% = C:\Users\<username>)

Since v2.6, the packer loads "cshybridcrypt_<packname>.dat" with --load_cs <packname> to unpack type 4-5.
 i.e. it must be used before -u/--unpack, not after

Since v2.7, --load_cs and --create_cs can be omitted with --typeforce


tl;dr if you try to pack root, it will search the settings in the following order:
 'root.json' (<packname>.json)
 'PackMakerLite.json'
 'C:\Users\Marty\root.json' (%userprofile%/<packname>.json)
 'C:\Users\Marty\PackMakerLite.json' (%userprofile%/PackMakerLite.json)


以管理员身份运行 install.bat 或将以下文件复制到“c:\windows\system32\”中：
PackMakerLite.exe
PackMakerLite_p.bat
PackMakerLite_u.bat

要获取菜单集成，请运行：
PML_Pack.add.reg
PML_Unpack.add.reg

-----------------------
如果您想要自定义该工具，
直接在相关工作环境中复制并编辑 PackMakerLite.json
（其中存在 .eix 文件）
（PackMakerLite.json.sample 包含任何可自定义字段的示例）

如果您只想自定义特定包（例如 ETC），
只需将其重命名为 <packname>.json（例如 etc.json）

自 v2.3 起，如果缺少本地文件，您也可以从 %userprofile% 全局加载 json 文件。
(%userprofile% = C:\Users\<username>)

自 v2.6 起，打包程序使用 --load_cs <packname> 加载“cshybridcrypt_<packname>.dat”以解压类型 4-5。
即，必须在 -u/--unpack 之前使用，而不是之后

自 v2.7 起，可以使用 --typeforce 省略 --load_cs 和 --create_cs

tl;dr 如果您尝试打包 root，它将按以下顺序搜索设置：
'root.json' (<packname>.json)
'PackMakerLite.json'
'C:\Users\Marty\root.json' (%userprofile%/<packname>.json)
'C:\Users\Marty\PackMakerLite.json' (%userprofile%/PackMakerLite.json)