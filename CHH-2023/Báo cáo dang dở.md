Đề cho một file crash dump `MEMORY.DMP`. Sử dụng tool Volatility3 để phần tích. Dùng plugn plist để xem các tiến trình đã chạy
```
Volatility 3 Framework 2.4.1
Progress:  100.00               PDB scanning finished
PID     PPID    ImageFileName   Offset(V)       Threads Handles SessionId       Wow64   CreateTime      ExitTime        File output

4       0       System  0xfa80024bb840  90      512     N/A     False   2023-05-31 18:18:24.000000      N/A     Disabled
268     4       smss.exe        0xfa8002c5e400  2       30      N/A     False   2023-05-31 18:18:24.000000      N/A     Disabled
356     340     csrss.exe       0xfa80037e7060  9       451     0       False   2023-05-31 18:18:26.000000      N/A     Disabled
440     340     wininit.exe     0xfa8003a68060  3       79      0       False   2023-05-31 18:18:26.000000      N/A     Disabled
460     448     csrss.exe       0xfa8003a67060  10      231     1       False   2023-05-31 18:18:26.000000      N/A     Disabled
520     448     winlogon.exe    0xfa8003ab6700  3       111     1       False   2023-05-31 18:18:26.000000      N/A     Disabled
528     440     services.exe    0xfa8003ab7810  7       207     0       False   2023-05-31 18:18:26.000000      N/A     Disabled
564     440     lsass.exe       0xfa8003aeab30  9       570     0       False   2023-05-31 18:18:26.000000      N/A     Disabled
572     440     lsm.exe 0xfa8003aec810  10      144     0       False   2023-05-31 18:18:26.000000      N/A     Disabled
672     528     svchost.exe     0xfa8003b6e3c0  10      356     0       False   2023-05-31 18:18:27.000000      N/A     Disabled
732     528     vmacthlp.exe    0xfa8003b9fb30  3       56      0       False   2023-05-31 18:18:27.000000      N/A     Disabled
768     528     svchost.exe     0xfa8003bd3b30  9       292     0       False   2023-05-31 18:18:27.000000      N/A     Disabled
868     528     svchost.exe     0xfa8003c18060  20      480     0       False   2023-05-31 18:18:27.000000      N/A     Disabled
924     528     svchost.exe     0xfa8003c52b30  16      377     0       False   2023-05-31 18:18:27.000000      N/A     Disabled
952     528     svchost.exe     0xfa8003c613a0  42      1036    0       False   2023-05-31 18:18:27.000000      N/A     Disabled
400     528     svchost.exe     0xfa8003cb24b0  12      542     0       False   2023-05-31 18:18:27.000000      N/A     Disabled
856     528     svchost.exe     0xfa8003ce3b30  15      364     0       False   2023-05-31 18:18:27.000000      N/A     Disabled
1116    528     spoolsv.exe     0xfa8003d6f250  15      338     0       False   2023-05-31 18:18:27.000000      N/A     Disabled
1148    528     svchost.exe     0xfa8003d91b30  19      316     0       False   2023-05-31 18:18:27.000000      N/A     Disabled
1340    924     dwm.exe 0xfa8003e38b30  5       124     1       False   2023-05-31 18:18:28.000000      N/A     Disabled
1372    1304    explorer.exe    0xfa8003e64960  39      1058    1       False   2023-05-31 18:18:28.000000      N/A     Disabled
1472    528     taskhost.exe    0xfa8003ea8410  8       145     1       False   2023-05-31 18:18:28.000000      N/A     Disabled
1544    528     VGAuthService.  0xfa8003f23b30  3       85      0       False   2023-05-31 18:18:28.000000      N/A     Disabled
1684    528     vmtoolsd.exe    0xfa8003f6f200  9       293     0       False   2023-05-31 18:18:28.000000      N/A     Disabled
1928    1372    vmtoolsd.exe    0xfa800407db30  6       186     1       False   2023-05-31 18:18:29.000000      N/A     Disabled
1288    528     svchost.exe     0xfa8004087060  5       103     0       False   2023-05-31 18:18:29.000000      N/A     Disabled
1316    672     WmiPrvSE.exe    0xfa8004b03060  10      211     0       False   2023-05-31 18:18:29.000000      N/A     Disabled
2136    528     dllhost.exe     0xfa8004b05b30  15      207     0       False   2023-05-31 18:18:29.000000      N/A     Disabled
2288    528     msdtc.exe       0xfa8004480b30  14      154     0       False   2023-05-31 18:18:30.000000      N/A     Disabled
2564    528     SearchIndexer.  0xfa80045344a0  13      616     0       False   2023-05-31 18:18:34.000000      N/A     Disabled
2844    672     WmiPrvSE.exe    0xfa80045b8530  10      239     0       False   2023-05-31 18:18:49.000000      N/A     Disabled
1736    1372    WINWORD.EXE     0xfa8003a6e060  13      443     1       False   2023-05-31 18:20:18.000000      N/A     Disabled
2792    528     svchost.exe     0xfa8003c86920  5       74      0       False   2023-05-31 18:20:18.000000      N/A     Disabled
2956    528     OSPPSVC.EXE     0xfa8003fcab30  3       129     0       False   2023-05-31 18:20:19.000000      N/A     Disabled
1916    528     svchost.exe     0xfa8003f83b30  12      321     0       False   2023-05-31 18:20:29.000000      N/A     Disabled
2484    868     audiodg.exe     0xfa8003c83b30  6       136     0       False   2023-05-31 18:26:32.000000      N/A     Disabled
1076    2228    taskmgr.exe     0xfa8004103b30  9       121     1       False   2023-05-31 18:27:43.000000      N/A     Disabled
```

Đề bài ở đây là `Báo cao dang dở` nên khả nằng là liên quan đến trình soạn thảo, mà ở đấy ta thấy có một tiến trình `WINWORK.EXE` được chạy. Đây là một tiến trình cửa ứng dụng Word. Tìm kiếm `doc` với plugin filescan để xem có file nào đang nghi không.
```
python ../../volatility3/vol.py -f MEMORY.DMP windows.filescan | grep -i doc
0x7e2226e0 100.0\Users\Public\Documents\desktop.ini     216
0x7e23a790      \Users\admin\Documents\desktop.ini      216
0x7e288070      \Users\admin\AppData\Roaming\Microsoft\Windows\Libraries\Documents.library-ms   216
0x7e32c070      \Users\admin\Documents  216
0x7e3e2070      \Users\admin\AppData\Roaming\Microsoft\Word\AutoRecovery save of Document1.asd  216
0x7e4862c0      \Windows\System32\mydocs.dll    216
0x7e5de070      \Windows\System32\shdocvw.dll   216
```
Tìm thấy file `AutoRecovery save of Document1.asd`. File .asd là một loại tập tin được tạo ra bởi Microsoft Word để lưu trữ thông tin tự động phục hồi. Khi bạn làm việc trên một tài liệu trong Word và chương trình bị đột ngột tắt hoặc máy tính bị khởi động lại mà không lưu tài liệu, Word sẽ tạo một tập tin .asd để lưu trữ phiên bản gần nhất của tài liệu. . Sử dụng plugin dumpfiles đê dump file này ra phân tích.

```
$ python ../../volatility3/vol.py -f MEMORY.DMP windows.dumpfile --physaddr 0x7e3e2070 
Volatility 3 Framework 2.4.2
Progress:  100.00               PDB scanning finished                                
Cache   FileObject      FileName        Result

DataSectionObject       0x7e3e2070      AutoRecovery save of Document1.asd      file.0x7e3e2070.0xfa8003d7b6d0.DataSectionObject.AutoRecovery save of Document1.asd.dat
```
vì đây là một file word, sử dụng tool unzip tách file ra phân tích
```
unzip file.0x7e3e2070.0xfa8003d7b6d0.DataSectionObject.AutoRecovery\ save\ of\ Document1.asd.dat -d res 
Archive:  file.0x7e3e2070.0xfa8003d7b6d0.DataSectionObject.AutoRecovery save of Document1.asd.dat
warning [file.0x7e3e2070.0xfa8003d7b6d0.DataSectionObject.AutoRecovery save of Document1.asd.dat]:  21752 extra bytes at beginning or within zipfile
  (attempting to process anyway)
  inflating: res/[Content_Types].xml  
  inflating: res/_rels/.rels         
  inflating: res/word/drawings/drawing1.xml  
  inflating: res/word/drawings/_rels/drawing1.xml.rels  
 extracting: res/word/media/image2.png  
 extracting: res/word/media/image1.png
```
Thấy có 2 file ảnh `res/word/media/image2.png` và  `res/word/media/image1.png` đáng ngờ. Mở ra được Flag

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20232002.png)
