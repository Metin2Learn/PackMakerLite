# PackMakerLite

https://metin2.dev/topic/20776-eterpack-archiver-packmakerlite/

https://metin2.dev/topic/2482-how-to-unpack-official-patches/#comment-16854
https://metin2.dev/docs/pages/file-formats/eterpack-r9/

PackMakerLite (PML) ֧������ 0-1-2-3-4-5-6��

�ܶ���֮��metin2 ���͵Ĵ������£�

- ���� 0-���洢���޼���/ѹ�������Դ� .epk ����ȫ��ȡ��
- ���� 1-ѹ��-lzo���ļ���
- ���� 2-ѹ��������-xtea(lzo(file))
- ���� 3-ʹ�� Panama ����-�������� panama/ �ļ����б���һ���������˵� .iv ��Կ�������ݽ��������֤�׶κ�ɶ����ٷ����������� patch2��
- ���� 4-ʹ�û��������ܣ�cshybridcrypt��-�������ڷ���� package/ �ļ����б���һ�� .dat ��Կ�������ˡ������ݽ��������֤�׶κ�ɶ����������е� metin2_patch �ļ���
- ���� 5-������ 4 ���ƣ������ṩ�˷������˵�ͼ/<map_name>����ֻ���������ݷ��� <map_name> ��ͼ��ſɶ�ȡ���ݣ��ٷ����������ڵ���ĹѨ���ݡ�
- ���� 6-ѹ���ͼ���-xtea(snappy(file))


��֪�� EterPack ����
�ͺ�	����
���� 0   ���ļ��� RAW��û��ѹ������ܡ�
���� 1	���ļ�ʹ�� LZO ѹ��������ʹ�� XTEA��
���� 2	���ļ�ʹ�� LZO ѹ����Ȼ��ʹ�� EterPack ������Կͨ�� XTEA ���ܡ������仰˵������ MCOZ CryptedObject��
���� 3	���ļ�ʹ�ð����� ����
���� 4	��ϼ���
���� 5	���ж������ݵ�HybridCrypt
���� 6	���ļ�ʹ�� Snappy ѹ����Ȼ��ʹ�� EterPack ������Կͨ�� XTEA ���ܡ������仰˵������ MCSP CryptedObject��

### ��װ

�Թ���Ա���� ��install.bat��

�����ã�xtea ������չ��Ҫʹ�õİ����ͣ������� PackMakerLite.json �и��ģ�

### �����ļ�����

Ĭ�������ļ����� .eix �ļ�����Ŀ¼
������ root������������˳���������ã�
- 'root.json' (<packname>.json)
- 'PackMakerLite.json'
- 'C:\Users\Marty\root.json' (%userprofile%/<packname>.json)
- 'C:\Users\Marty\PackMakerLite.json' (%userprofile%/PackMakerLite.json)

### ���
PackMakerLite_p.bat �������
PackMakerLite_u.bat �������
PackMakerLite_PackAllDirectories.bat  �������
PackMakerLite_UnpackAll.bat           �������

```
{
// !!! ��Щѡ����ñ���ע�ͣ��������ǻḲ�������в�����

// ���� .log �ļ������ƣ�
//"log_name":"PackMakerLite",

// ���� cs .dat �ļ���ǰ׺��
//"cs_name":"",

// ���������ض��ļ���
"ignore_full_name": [".git", ".svn", ".vs", "desktop.ini"],

// ������Щ�ض��ļ���չ��
"ignore_file_extension": ["bak", "db", "wdp"],

// ��ÿ�� FiLeName ת��ΪСд�ġ�filename��
"force_filename_lowercase": false,

// ��� pack_type_by_list ��û��ƥ��Ĺ�����ʹ�ô˰�����
"default_pack_type": 2,

// �����ļ���չ��ָ��������
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

// ʹ�� parallel �� --parallel
//"parallel":true,

// ���Ϊ true��--hiddenfiles Ϊ true��--skipignorefiles Ϊ false�������������ļ���.XXX �򲻿ɼ���
//"hidden_files":true,

// Ĭ�� eterpack/eterpack.cpp ����
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

// magic δ���ܿ�
"eter_magic_epkd":"EPKD",
// magic ���ܿ�
"eter_magic_mcoz":"MCOZ",
// magic type6 ���ܿ�
"eter_magic_mcsp":"MCSP"
}
```


### ����

Thanks also to:
blackdragonx61 / Mali-type4-5 extract code / type 6 compress code
metin2team-type6 extract code

By martysama0134