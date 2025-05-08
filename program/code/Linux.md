## 查看指令用法：
進入man page裡要離開，按q
```bash
man
man ls
```

---
## 顯示目前在電腦的位置：
```bash
pwd
```

---
## 顯示所在資料夾裡的導案：
ls:查看內容<br>
ls -a:顯示包含隱藏的檔案/資料夾<br>
ls -l:可以查看到檔案的詳細資料<br>
ls -la:可以同事查看到以上兩種資訊
```bash
ls
ls -a
ls -l
ls -la
```

---
## 更換位置：
```bash
cd
cd your-folder-name
```

---
## 創建檔案或資料夾：
```bash
touch your-file-name.md

mkdir your-folder-name
```

---
## 顯示檔案的內容：
```bash
cat your-file-name.???
```

---
## 刪除檔案或資料夾：
```bash
rm the-file-you-want-to-delete

rm -r the-folder-you-want-to-delete

rm -rf (forced deletion, use with caution)
```

---
## 複製檔案或資料夾：
```bash
cp you-want-to-cope-file where-you-want-to-put

cp -r you-want-to-cope-folder where-you-want-to-put
```

---
## 移動位置/改名：
```bash
mv original-file-location(original-file-name)
```

---
## 下載指令：
### wget:
```bash
wget https://www.example.com/somefile.zip
```
把下載的檔案存為指定的檔名
```bash
wget -o file-name.zip https://www.example.com/somefile.zip
```
如果下載中斷，可以從上次中斷的地方繼續下載
```bash
wget -c https://www.example.com/somefile.zip
```
在背景下載
```bash
wget -b https://www.example.com/somefile.zip
```

### curl:
```bash
curl -O https://www.example.com/document.pdf
```
指定檔案名稱
```bash
curl -O mydoc.pdf https://www.example.com/document.pdf
```
斷點續傳
```bash
curl -C - -O https://www.example.com/bigfile.mkv
```
安靜模式，不顯示進度條跟報錯
```bash
curl -s -O https://www.example.com/bigfile.mkv
```
