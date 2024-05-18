# RE_Challenge1
![image](https://github.com/NamDT5125/fusec/assets/69895129/aa02afe0-118a-4661-b206-dedd3ab2eb35)
Đầu tiên ta đưa vào DIE để xem file, đây là file ELF64, chạy thử trên linux:
![image](https://github.com/NamDT5125/fusec/assets/69895129/fcd5d657-02fc-4a9b-aaff-2403f10b4940)
FIle yêu cầu nhập vào license key, nhập sai thì in Incorrect key, ta thử đưa vào IDA:
![image](https://github.com/NamDT5125/fusec/assets/69895129/31dda014-a5bb-42aa-aa5c-e74a8fb0e225)
Có 38 giá trị v7 và v8, ta biết được độ dài key là 38 không tính FUSec{ và }, kiểm tra kĩ hàm `check_license_key`:
![image](https://github.com/NamDT5125/fusec/assets/69895129/cfcc7dea-ef06-44a8-ace3-cefc897486da)
Nhìn trong rất đơn giản, ta có thể decode lại hoặc debug, mình lười nên debug:
![image](https://github.com/NamDT5125/fusec/assets/69895129/b94814c2-9200-4fe0-bc10-96fa5e4c0dc4)
Ở đây ta check `dl`, chính là lưu trữ các kí tự của flag
Flag: `FUSec{sjdcnksduqisjcdnmclsudhcwesafvfvasdsdd}`
