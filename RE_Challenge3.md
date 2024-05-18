# RE_Challenge3
Ta ném vào DIE để check, thấy được pack bằng UPX, ta unpack bằng `upx -d -o re3 '/var/run/vmblock-fuse/blockdir/cRAeXe/RE_Challenge3' `:
![image](https://github.com/NamDT5125/fusec/assets/69895129/3320fd36-2bde-4c98-a606-0d6fc3edda0a)

Ta chạy thử chương trình xem như nào:
![image](https://github.com/NamDT5125/fusec/assets/69895129/a8bef0d7-d222-4439-8adb-70b42dbc6669)

Ta có vẻ dùng file sai cách, ném file vào IDA để xem:
![image](https://github.com/NamDT5125/fusec/assets/69895129/a424357b-d081-4ef6-8310-7b0ce8ef77ff)

Mấy cái kia không quan trọng bằng cái hàm `decrypt_flag`, mở thử xem có flag không:
![image](https://github.com/NamDT5125/fusec/assets/69895129/3b0c789f-b2d2-492c-8306-1ca0b2dce032)

Ta thấy v8 là có chứa flag được mã hóa và hàm `substitute_and_permute` làm gì đó với flag, mở luôn hàm:
![image](https://github.com/NamDT5125/fusec/assets/69895129/5bb885ae-89cf-49ec-a15f-694c29c729d4)

Nhìn mấy cái tính toán hơi phức tạp, ta có thể decode lại, do mình ngu toán nên debug:
![image](https://github.com/NamDT5125/fusec/assets/69895129/9fd54ea8-789d-430f-afcc-03ded95f5a67)
![image](https://github.com/NamDT5125/fusec/assets/69895129/2eb35dfd-88da-4f0d-817f-c39c1ba4496f)

Flag nằm trong *a1: `FUSec{Y0ugotm2friendscongrat}`
