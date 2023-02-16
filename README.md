# CBJS reconnaisance challenge writeup

Dưới đây là challenge mình giải được khi tham gia RECONNAISSANCE workshop do Cyberjutsu tổ chức

**Mục tiêu**: khai thác từ ip 128.199.157.202, tìm ra 5 flag 

## Flag 1 và 2:

Tiến hành scan mục tiêu bằng công cụ ffuf và wordlists common.txt 

![image](https://user-images.githubusercontent.com/90508803/219464315-e8a1a1b1-2d96-4dff-9e49-8fad2c297146.png)


check lần lượt các endpoint từ kết quả scan

![image](https://user-images.githubusercontent.com/90508803/219464877-b78028ed-ba8c-4a80-921d-f228db3f7280.png)


Ở endpoint /robots.txt ta có kết quả

![image](https://user-images.githubusercontent.com/90508803/219465300-01da7cd0-8201-4132-beae-059104075e20.png)

Tiếp tục kiểm tra secret file xuất hiện flag 1

`CBJS{794a90_N1ceeeee_recon_crawler}`

![image](https://user-images.githubusercontent.com/90508803/219465776-591df76e-03cd-42e0-8291-a7750d369eee.png)


Ở endpoint /test xuất hiện flag 2

`CBJS{d91931_sometimes_the_developers_forget_their_endpoints}`

![image](https://user-images.githubusercontent.com/90508803/219466478-00b4159a-e5b2-4d4a-b9f2-f3ccdf3083c3.png)

## Hint flag 3,4,5 

![image](https://user-images.githubusercontent.com/90508803/219467310-3ef88713-60b7-4b8f-ae96-a499cfb1fe20.png)

# Flag 3 và 4

Dựa vào hint được cung cấp ta tiến hành scan parameter bằng công cụ arjun 

Tìm được 1 parameter là debug

![image](https://user-images.githubusercontent.com/90508803/219469102-ba52ae66-b64a-42ed-8d6b-9607c2e52e6f.png)

Truy cập url với parameter ta được flag 4

`FLAG=CBJS{5d991c_h1dden_p4ram_is_hidden_gem}`

![image](https://user-images.githubusercontent.com/90508803/219469428-0f6f6bc9-ad95-4a2b-859c-9bee89600921.png)

Đồng thời xuất hiện file '/common/common.php', tiếp tục kiểm tra xuất hiện kết quả như sau:

![image](https://user-images.githubusercontent.com/90508803/219469964-f3b74fa6-b1b5-4364-8b68-824441608444.png)

Xuất hiện tiếp file '/common/db.php', đây là 1 file liên quan đến database như gợi ý đã cho

![image](https://user-images.githubusercontent.com/90508803/219470369-b3f6f40e-8a70-4096-ba3d-ba5922214827.png)

Từ dòng này cho ta biết thông tin truy cập database

![image](https://user-images.githubusercontent.com/90508803/219470974-58992542-124d-4d0e-86d0-27ade5b1506b.png)

url của database sẽ có dạng `mongodb://128.199.157.202:27017`

Sử dụng MongoDB Compass để truy cập database , kiểm tra các table , xuất hiện flag 3

`CBJS{fa6d7c_people_usually_f0rget_about_ports}`

![image](https://user-images.githubusercontent.com/90508803/219473414-a9942ebe-9bc0-48cc-b5b3-6c46262bf13b.png)












