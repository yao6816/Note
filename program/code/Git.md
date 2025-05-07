
---
mac系統裡Git會跟隨Xcode一起安裝
ubuntu系統：
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install git
```

---
下載完後設定使用者名稱跟郵件：
```git
git config --global user.name "your name"
git config --global user.email "your mail address"
```

---
git初始化：
```git
git init
```

---
檢查狀態：
```git
git status
```

---
加入要追蹤的檔案；
```git
# add後加入追蹤的檔案名稱
git add programming-language
# 在add後面加一個 . 選擇全部的檔案
git add .
```

---
提交檔案快照：
```git
git commit -m "Enter the changes"
```

---
查看快照：
```git
git log # 按q可以退出

git log --oneline # 快速查看快照
```

---
恢復成之前的快照：
```git
git checkout fd01510 -- lab1
git checkout 快照版本 -- 檔案名 # 更改完後記得也要commit
```

---
