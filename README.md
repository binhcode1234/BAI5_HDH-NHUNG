# BAI5_HDH-NHUNG
Bài 1 : Bài tập 01: Biên dịch ứng dụng với thư viện đã có
1.  Bật cJSON trong Buildroot và build lại OS tích hợp thư viện cJSON
<img width="975" height="697" alt="image" src="https://github.com/user-attachments/assets/6cf71e64-bdaa-4a0f-ab8b-fcd1fec8f85c" />

2.  Viết chương trình C/C++ có sử dụng thư viện CJSON thực hiện parse 01 gói tin JSON
thành các trường thông tin và in lên Terminal.
<img width="975" height="673" alt="image" src="https://github.com/user-attachments/assets/686fc542-d021-4323-8bc2-cc6fcd54892d" />

3.Thực hiện biên dịch chéo sử dụng Toolchain đã cập nhật ở bước 1 (VD: Tên là
HelloJSON.c)
<img width="975" height="691" alt="image" src="https://github.com/user-attachments/assets/dfe01783-e4ab-4eca-adb7-7d6e1a05d9ac" />
<img width="975" height="216" alt="image" src="https://github.com/user-attachments/assets/66107d2f-3a47-49b4-b582-8af6489af014" />

4.Biên dịch thành công chương trình HelloJSON.c và đưa xuống BBB
<img width="975" height="262" alt="image" src="https://github.com/user-attachments/assets/44781778-5673-4ba9-a7d9-71d9b4027c28" />

5. Khởi chạy thành công chương trình đã biên dịch.
- di chuyển vào thư mục chừa flie : cd/root
- cấp quyền thực thi : chmod +x HelloJSON
- chạy chương trình: ./HelloJSON
- kết quả :
<img width="975" height="115" alt="image" src="https://github.com/user-attachments/assets/6a653560-7cab-4b60-bea4-8d8b4290191e" />
Bài tập 02: Tự tạo thư viện cá nhân.
Yêu cầu: Tự tạo 01 thư viện đơn giản của riêng mình và ứng dụng.
sử dụng thư viện đó
1. Viết 01 thư viện đơn giản gồm 01 file .h và 01 file .c thực hiện 1 nhiệm vụ đơn giản như:
Cộng 2 số, Tìm số nguyên tố.... (tùy ý)

<img width="985" height="701" alt="image" src="https://github.com/user-attachments/assets/dc149bdf-7090-4f26-9194-ac36a6acf239" />
<img width="968" height="682" alt="image" src="https://github.com/user-attachments/assets/3d13690e-df15-4c8b-b5ef-a015eadcf573" />

2 + 3 .Biên dịch thành công thư viện ở bước 1 thành: Static Library (.a) và Dynamic Library.
(.so ), đưa thư viện đã biên dịch thành công ở bước 2 vào Sysroot.
<img width="975" height="644" alt="image" src="https://github.com/user-attachments/assets/7b2c03e5-621a-483f-915a-0e22ee938e40" />
4.Viết chương trình C/C++ có sử dụng thư viện đã tạo.
<img width="975" height="691" alt="image" src="https://github.com/user-attachments/assets/74aa7646-ce9d-44e1-aa41-260879e59425" />
5. Biên dịch chương trình với 2 loại thư viện (Thư viện tĩnh và Thư viện động) thành 2
chương trình.
<img width="975" height="161" alt="image" src="https://github.com/user-attachments/assets/bace75f9-3304-4b67-9799-70729db45a18" />
6. Đưa chương trình và thư viện đã biên dịch xuống BBB (Cả 2 chương trình) thử nghiệm
hoạt động.
<img width="975" height="467" alt="image" src="https://github.com/user-attachments/assets/d07bdcd1-2fc9-435f-a184-ca4cd48c875c" />
7. So sánh về kích thước của 2 chương trình đã tạo ở bước (5) về dung lượng, yêu cầu
phụ thuộc (sử dụng lệnh read-elf dependencies).
<img width="975" height="115" alt="image" src="https://github.com/user-attachments/assets/af65b449-054f-4138-b903-36f344c4592b" />
<img width="975" height="314" alt="image" src="https://github.com/user-attachments/assets/15e725ad-3185-4031-9bb8-c74ac877b686" />

Bài tập 03: Tích hợp ứng dụng và thư viện và Buildroot
Yêu cầu: Xây dựng chương trình có phụ thuộc vào cả 2 thư viện ở
Bài 1 và Bài 2 vào Buildroot có ràng buộc phụ thuộc.
BƯỚC 1: chuẩn bị thư mục chứa mã nguồn.
- tạo 1 thư mục riêng ngoài thư mục buildroot chứa mã nguồn cho bài 3 :
<img width="975" height="231" alt="image" src="https://github.com/user-attachments/assets/59dc5084-71fb-4039-9cab-ebb8ea43b444" />
- Tạo mã nguồn cho chương trình chính (Bài 3):
<img width="975" height="653" alt="image" src="https://github.com/user-attachments/assets/4432a336-cd8a-474a-a1f1-45dc6a988ec2" />
BƯỚC 2: Tạo package cho thư viện libmilyb trong buildroot 
<img width="975" height="41" alt="image" src="https://github.com/user-attachments/assets/e4a5b072-d7b8-4b6f-aad5-9f40159a9027" />
<img width="975" height="685" alt="image" src="https://github.com/user-attachments/assets/bed404a7-572f-40eb-8d18-d33fcd5e147a" />
<img width="975" height="684" alt="image" src="https://github.com/user-attachments/assets/5b3f37a1-2956-41cc-b1b1-617850a4bcb1" />

BƯỚC 3: Tạo package cho ứng dụng app_bai3 (KÈM ĐIỀU KIỆN PHỤ THUỘC)
Đây là Yêu cầu 4: Ràng buộc phụ thuộc để tự động bật cJSON và libmylib.
1.	Tạo thư mục package: mkdir -p ~/buildroot-2023.11.1/package/app_bai3
2.	Tạo file Config: nano ~/buildroot-2023.11.1/package/app_bai3/Config.in
<img width="975" height="32" alt="image" src="https://github.com/user-attachments/assets/acebb031-a2b8-4e82-9dd4-8f83ed92c355" />
<img width="975" height="690" alt="image" src="https://github.com/user-attachments/assets/bb983889-ceb0-401f-aefb-dd524762ab3f" />
<img width="975" height="687" alt="image" src="https://github.com/user-attachments/assets/4bfc1421-ec48-4c9a-9209-f56c11e69e00" />

BƯỚC 4: KHAI BÁO VÀO MENU CỦA BUILDROOT
Để 2 package trên hiện trong Menuconfig, pro phải nhúng chúng vào file tổng. Gõ lệnh: nano ~/buildroot-2023.11.1/package/Config.in Cuộn xuống tận cùng của file, trước dòng endmenu, dán 2 dòng này vào:
source "package/libmylib/Config.in"
source "package/app_bai3/Config.in"
<img width="975" height="687" alt="image" src="https://github.com/user-attachments/assets/74d1c80e-ec81-47c3-a449-94547e6c5b06" />

BƯỚC 5: BIÊN DỊCH VÀ KIỂM TRA (Yêu cầu 5)
1.	Di chuyển vào thư mục Buildroot: cd ~/buildroot-2023.11.1
2.	Mở giao diện cấu hình: make menuconfig
-	Vào phần Target packages (Kéo xuống dưới cùng).
-	Pro sẽ thấy app_bai3 và libmylib.
-	Di chuyển tới app_bai3 và ấn phím Space để chọn (hiện dấu [*]).
=> BƯỚC CHỤP ẢNH BÁO CÁO: Chụp lại màn hình này. Thầy sẽ thấy khi pro bật app_bai3, thì libmylib và cJSON (nếu pro vào thư mục Libraries/JSON kiểm tra) cũng sẽ tự động được chọn.
-	Thoát ra và Save lại (Save -> Exit).
3.	Chạy lệnh biên dịch: make (Đợi Buildroot chạy, có thể mất từ 5 - 15 phút tùy máy).
<img width="975" height="684" alt="image" src="https://github.com/user-attachments/assets/03cbbee7-dac8-46a0-ac55-c27ffa2a21dc" />
<img width="975" height="577" alt="image" src="https://github.com/user-attachments/assets/85ed904d-1624-4a2d-93df-07e145988466" />

BƯỚC 6: CHẠY THỬ NGHIỆM TRÊN BOARD BBB
1.	Khi lệnh make chạy xong, hệ điều hành mới đã có sẵn app của pro.
2.	Cắm thẻ nhớ vào PC, giải nén rootfs.tar (giống như tui đã hướng dẫn ở cuối bài 2):
3.	sudo mount /dev/sdb2 /mnt
4.	sudo tar -xvf ~/buildroot-2023.11.1/output/images/rootfs.tar -C /mnt/
5.	sync
6.	sudo umount /mnt
7.	sudo mount /dev/sdb2 /mnt
8.	sudo tar -xvf ~/buildroot-2023.11.1/output/images/rootfs.tar -C /mnt/
9.	sync
10.	sudo umount /mnt
11.	Cắm thẻ nhớ vào Board BBB, giữ nút S2 và cấp nguồn.
12.	Mở Picocom, đăng nhập root.
13.	Bài 3 : KHÔNG CẦN copy file, KHÔNG CẦN cấp quyền chmod, KHÔNG CẦN export đường dẫn thư viện nữa. Hệ điều hành đã làm sẵn mọi thứ. Pro chỉ cần gõ đúng 1 chữ:
14.	app_bai3
<img width="975" height="434" alt="image" src="https://github.com/user-attachments/assets/fe267b48-d8c7-4c24-8245-ed97174af504" />
<img width="975" height="190" alt="image" src="https://github.com/user-attachments/assets/2fd02eba-8051-475a-8e56-a48208740e0a" />



















  




