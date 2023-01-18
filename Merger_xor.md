#Merger Xor
---
-Đề bài cho môt file C và một file Text
![](https://www.bing.com/images/blob?bcid=r..xUhDRkSMF-A)
File python
~~~C
#include<stdio.h>
#include<string.h>

int 
get_first_4_bit(unsigned char target){
	return target&0xf;
}

int
get_later_4_bit(unsigned char target){
	return (target>>4)&0xf;
}

void
Flat(unsigned char *input,int len){
	unsigned char first_4_bit,later_4_bit,block,cipher[1024];
	for(int idx=0;idx<len;idx++){
		first_4_bit = get_first_4_bit(input[idx]);
		later_4_bit = get_later_4_bit(input[(idx+1)%len]);
		// merging...
		block = (first_4_bit << 4) + later_4_bit;
		cipher[idx] = input[idx]^block;
	}
	memmove(input,cipher,len);
}

int main(){
	unsigned char input[1024],result[1024];
	printf("[+] FLAG: ");
	scanf("%s",input);
	int len = strlen((const char*)input);
	Flat(input,len);
	Flat(input,len);
	Flat(input,len);
	Flat(input,len);
	Flat(input,len);
	printf("[+] Cipher: ");
	for(int i=0;i<len;i++) 
		printf("0x%02x,",input[i]);
	
	return 1;
}

 
~~~
File text
~~~txt
[+] Cipher: 
0x98,0x02,0xaa,0x9b,0xfe,0xdc,0x44,0x73,0xef,0x9d,0x40,0xdd,0xd8,0x05,0xc9,0xea,0x51,0xcd,0xab,0x01,0x77,0x14,0x8c,0x62,0x51,0xea,0x41,0xbe,0xae,0x33,0x23,0xd9,0x9d,0xfe,0x22,0x36,0xdb,0x23,0xfa,0x72,0x36,0xfd,0xb9,0xbc,0x11,0x04,0xfc,0xc8,0xdf
~~~
- Đọc xong code ta có thể thấy được cách thức encrypt là: chia đôi mỗi byte trong chuỗi, sau đó với mỗi 4 bit vừa chia xor với 4 bit bên phải nó được được chuỗi mới. Encrypt 5 lần thì thu được chuỗi cipher trong file text.
- Solve: Sử dụng bruteforce
	- Đầu tiên chọn 2 byte đầu cho chuỗi từ các giá trị 0 đến 255 sau đó encrypt và so sánh với byte đầu tiên trong cipher. Nếu đúng thì quay lui hết các byte còn lại cho đến khi hết chuỗi, còn sai thì chọn lại cho đến khi đúng.
	- Sau khi chọn được hết các byte thì gán chuỗi đó cho cipher và lặp lại như trên 4 lần nữa. Nếu chuỗi có chứa 'KCSC{' ở đầu thì tìm được flag.
- Dưới đây là code :
~~~py
sample_main = [0x98,0x02,0xaa,0x9b,0xfe,0xdc,0x44,0x73,0xef,0x9d,0x40,0xdd,0xd8,0x05,0xc9,0xea,0x51,0xcd,0xab,0x01,0x77,0x14,0x8c,0x62,0x51,0xea,0x41,0xbe,0xae,0x33,0x23,0xd9,0x9d,0xfe,0x22,0x36,0xdb,0x23,0xfa,0x72,0x36,0xfd,0xb9,0xbc,0x11,0x04,0xfc,0xc8,0xdf]


def brute(sam,index,p_now,ret,flat_count):
    if index == (len(sam) - 1):
        #print("[+]Finding....")
        ret_0 = ret[0]
        ret_end = ret[len(sam)-1]
        flatten = ((ret_end&0xf)<<4)+((ret_0>>4)&0xf)
        
        if (flatten^p_now) == sam[index]:
            if bytes(ret)[0:4] == b"KCSC":
                print(f"Found : {bytes(ret)} ,flat_count = {flat_count}")
                exit(0)
            if flat_count == 5:
                return 1
            get_flag(ret,flat_count)
    else:
        for i in range(256):
            flat = ((p_now&0xf)<<4)+((i>>4)&0xf)
            if (p_now^flat) == sam[index]:
                ret[index+1] = i
                brute(sam,index+1,i,ret,flat_count)
                ret[index+1] = 0

def get_flag(sample,flat_count):
    ret = [0]*len(sample)
    for i in range(256):
        for j in range(256):
            flat = ((i&0xf)<<4) + ((j>>4)&0xf)
            if (flat^i) == sample[0]:
                ret[0] = i
                ret[1] = j
                brute(sample,1,j,ret,flat_count+1)
                ret[0] = 0
                ret[1] = 0
get_flag(sample_main,0)

~~~
