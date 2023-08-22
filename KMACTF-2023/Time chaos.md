

# Phân tích 

Mở file bằng `Wireshark` nên thì thấy thời gian đã bị thay đổi có các số âm

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-06-20%20174705.png)

Thử sắp xếp lại thời gian và để ý phần data của mỗi gói thấy có vẻ khả nghi 

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-06-20%20175048.png)

# Solved

Dùng tool tshark để lấy time và data của các gói tin:

```
tshark -nr Time_chaos.pcap -T fields -e data.data | xxd -r -p > data.txt 

tshark -nr Time_chaos.pcap -T fields -e frame.time_relative > time.txt

```

Viết script để sắp xếp lại time và data:

```python

data = []
time = []
with open("data.txt",'r') as d:
    read_data = d.read()
    for i in read_data:
        data.append(i)
with open("time.txt",'r') as t:
    read_time = t.readlines()
    for i in read_time:
        time.append(float(i[:-1]))
for i in range(len(time)-1):
    for j in range(i,len(time)):
        if time[j]<time[i]:
            time[i],time[j]=time[j],time[i]
            data[i],data[j]=data[j],data[i]
print(''.join(data))

```

Ta được flag: `KMACTF{C0d3_cun9_du0c_t0Ol_Cun9_DuOc_nHun9_h1_v0n9_b4n_kh0n9_l@m_m0t_c4cH_tHu_C0nG}`
