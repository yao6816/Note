
這份文件旨在幫助初學者快速上手常用的 Linux 指令。

## 檔案與目錄操作

### 1. 查看指令用法 (`man`)
當你不確定某個指令如何使用時，`man` (manual) 指令會顯示該指令的詳細說明文件。
-   **基本語法：**
    ```bash
    man [指令名稱]
    ```
-   **範例：**
    ```bash
    man ls  # 查看 ls 指令的說明
    ```
-   **離開manpage：** 按`q`鍵

### 2. 顯示目前所在位置 (`pwd`)
`pwd` (print working directory) 指令會顯示你目前所在的完整路徑。
-   **基本語法：**
    ```bash
    pwd
    ```

### 3. 列出檔案與目錄 (`ls`)
`ls` (list) 指令用於顯示目前目錄下的檔案與子目錄。
-   **基本語法：**
    ```bash
    ls
    ```
-   **常用選項：**
    -   `ls`: 列出當前目錄的內容
    -   `ls -a`: 列出所有檔案，包括隱藏的檔案（以`.`開頭的檔案）
    -   `ls -l`: 以長格式顯示檔案詳細資訊 (權限、擁有者、大小、修改日期)
    -   `ls -la`: 結合 `-l` 和 `-a` 選項，顯示所有檔案的詳細資訊
    -   `ls -lh`: 以人類可讀的格式顯示檔案大小 (例如：1K, 234M, 2G)

-   **範例：**
    ```bash
    ls
    ls -a
    ls -l
    ls -la
    ls -lh ~/Desktop/program # 列出指定路徑的內容
    ```

### 4. 切換目錄 (`cd`)
`cd` (change directory) 指令用於切換目前的工作目錄。
-   **基本語法：**
    ```bash
    cd [目標目錄路徑]
    ```
-   **常用操作：**
    -   `cd`: 切換到目前使用者的家目錄
    -   `cd Desktop`: 切換到名為 Desktop 的子目錄
    -   `cd ..`: 切換到上一層目錄
    -   `cd /`: 切換到根目錄
    -   `cd ~`: 切換到目前使用者的家目錄 (與單獨`cd`指令效果相同)

-   **範例：**
    ```bash
    cd /User/name
    cd my_project
    cd ..
    ```

### 5. 創建檔案與目錄

#### 創建檔案 (`touch`)
`touch`指令可以用來創建一個新的空檔案。
-   **基本語法：**
    ```bash
    touch [檔名]
    ```
-   **範例：**
    ```bash
    touch your-file-name.md
    touch index.html style.css script.js # 一次創建多個檔案
    ```

#### 創建目錄 (`mkdir`)
`mkdir`(make directory) 指令用於創建新的目錄。
-   **基本語法：**
    ```bash
    mkdir [目錄名稱]
    ```
-   **常用選項：**
    -   `mkdir -p your-folder/sub-folder`: 如果父目錄不存在，`-p`選項會一併創建所需的父目錄。

-   **範例：**
    ```bash
    mkdir your-folder-name
    mkdir -p projects/web/assets
    ```

### 6. 顯示檔案內容 (`cat`)
`cat` (concatenate) 指令主要用於將檔案內容輸出到標準輸出 (通常是終端機畫面)。
-   **基本語法：**
    ```bash
    cat [檔名]
    ```
-   **範例：**
    ```bash
    cat your-file-name.txt
    cat file1.txt file2.txt > combined.txt # 將多個檔案合併到一個新檔案
    ```
-   **注意事項：**
    對於非常大的檔案，使用`cat`可能會導致終端機被大量文字淹沒。可以考慮使用`less`或`more`指令分頁查看。

### 7. 刪除檔案與目錄 (`rm`)
`rm`(remove) 指令用於刪除檔案或目錄。使用此指令時務必小心，因為刪除的檔案通常無法輕易恢復。
-   **刪除檔案：**
    ```bash
    rm the-file-you-want-to-delete.txt
    ```
-   **刪除目錄（及其內容）：**
    `rm -r`：`-r`(recursive) 選項表示遞迴刪除目錄及其所有內容。
    ```bash
    rm -r images_backup
    ```
-   **強制刪除（慎用）：**
    `rm -rf`：`-f`(force) 選項表示強制刪除，不進行任何提示。此操作非常危險，請再三確認後使用。
    ```bash
    # 警告：以下指令會無提示強制刪除，請謹慎使用
    rm -rf old_project
    ```

### 8. 複製檔案與目錄 (`cp`)
`cp`(copy) 指令用於複製檔案或目錄。
-   **複製檔案：**
    ```bash
    cp [來源檔案] [目標路徑/新檔名]
    ```
-   **範例：**
    ```bash
    cp source-file.txt destination-folder/
    cp important-data.doc important-data-backup.doc
    ```
-   **複製目錄及其內容：**
    需要使用`-r`(recursive) 選項。
    ```bash
    cp -r my_app /backup/my_app_v1
    ```

### 9. 移動檔案與目錄 / 重新命名 (`mv`)
`mv`(move) 指令用於移動檔案或目錄，也可以用來重新命名檔案或目錄。
-   **移動檔案或目錄：**
    ```bash
    mv [來源檔案/目錄] [目標路徑]
    ```
-   **範例：**
    ```bash
    mv report.pdf documents/
    mv old-project/ archive/
    ```
-   **重新命名檔案或目錄：**
    如果來源和目標都在同一個目錄下，且目標名稱與來源不同，則效果為重新命名。
    ```bash
    mv old-file-name.txt new-file-name.txt
    ```

### 10. 網路下載指令

#### `wget`
`wget` 是一個非互動式的網路下載工具，可以在背景下載檔案。

-   **基本下載：**
    ```bash
    wget [https://www.example.com/somefile.zip](https://www.example.com/somefile.zip)
    ```
-   **將下載的檔案另存為指定檔名 (`-O`)：**
    > 注意：正確的選項是大寫的 `-O`。小寫的 `-o` 是將日誌訊息寫入檔案。
    ```bash
    wget -O new-filename.zip [https://www.example.com/somefile.zip](https://www.example.com/somefile.zip)
    ```
    *(範例已修正為使用正確的 `-O` 選項來儲存檔案，並使用 `new-filename.zip` 作為新檔名範例)*
-   **斷點續傳 (`-c`)：**
    如果下載中斷，可以使用此選項從上次中斷的地方繼續下載。
    ```bash
    wget -c [https://www.example.com/somefile.zip](https://www.example.com/somefile.zip)
    ```
-   **背景下載 (`-b`)：**
    下載會在背景執行，釋放你的終端機。
    ```bash
    wget -b [https://www.example.com/somefile.zip](https://www.example.com/somefile.zip)
    ```
    *注意：背景下載的日誌預設會寫入 `wget-log` 檔案。*

#### `curl`
`curl` (client URL) 是一個強大的命令列工具，用於傳輸資料，支援多種協定。

-   **基本下載（使用遠端檔名）：**
    使用 `-O` (大寫字母O) 會使用 URL 中指定的檔案名稱來儲存檔案。
    ```bash
    curl -O [https://www.example.com/document.pdf](https://www.example.com/document.pdf)
    ```
-   **下載檔案並指定檔名 (`-o`)：**
    使用 `-o` (小寫字母o) 可以讓你指定一個不同的檔案名稱來儲存。
    ```bash
    curl -o mydoc.pdf [https://www.example.com/document.pdf](https://www.example.com/document.pdf)
    ```
-   **斷點續傳 (`-C -`)：**
    `-C -` (注意中間的橫線) 告訴 `curl` 自動從上次中斷的位置繼續。
    ```bash
    curl -C - -O [https://www.example.com/bigfile.mkv](https://www.example.com/bigfile.mkv)
    ```
    *如果要搭配 `-o` 指定檔名並斷點續傳：*
    ```bash
    curl -C - -o mybigfile.mkv [https://www.example.com/bigfile.mkv](https://www.example.com/bigfile.mkv)
    ```
-   **安靜模式 (`-s` 或 `--silent`)：**
    此選項會讓 `curl` 在執行時保持靜默，不顯示進度表或錯誤訊息。這在腳本中很有用。
    ```bash
    curl -s -O [https://www.example.com/document.pdf](https://www.example.com/document.pdf)
    ```
    或者，與 `-o` 一起使用：
    ```bash
    curl -s -o mydoc.pdf [https://www.example.com/document.pdf](https://www.example.com/document.pdf)
    ```