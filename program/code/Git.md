# Git 操作指南

## 在不同系統上安裝 Git

### macOS 系統
Git 會隨 Xcode 一起安裝。若尚未安裝，可輸入以下指令安裝 Xcode Command Line Tools：
```bash
xcode-select --install
```

### Ubuntu 系統
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install git
```

---

## 設定 Git 使用者資訊
```bash
git config --global user.name "your name"
git config --global user.email "your mail address"
```

---

## 初始化 Git 倉庫
```bash
git init
```

---

## 檢查目前狀態
```bash
git status
```

---

## 加入要追蹤的檔案

加入指定檔案：
```bash
git add programming-language
```

加入所有變更的檔案：
```bash
git add .
```

---

## 提交檔案快照
```bash
git commit -m "Enter the changes"
```

---

## 查看提交紀錄

查看完整快照紀錄：
```bash
git log
```

快速查看快照紀錄（單行顯示）：
```bash
git log --oneline
```

> 使用 `q` 鍵退出 `git log` 頁面。

---

## 恢復成之前的快照

恢復某個檔案為某個快照的狀態：
```bash
git checkout fd01510 -- lab1
```

通用格式：
```bash
git checkout <快照版本> -- <檔案名稱>
```

> 修改後請記得再次使用 `git commit` 提交。
