# Python 學習筆記 (入門篇)

---

### 1. 輸出 (Output)

Python 中使用 `print()` 函數進行輸出。

- `end` 參數: `print()` 函數預設會在輸出的結尾加上換行符號 `\n`。可以使用 `end=""` 來指定結尾字元，例如 `end=" "` 表示以空格結尾，`end=""` 表示不加任何結尾字元。
- 格式化輸出 (Formatted Output):
  - `%d`: 整數
  - `%s`: 字串
  - `%f`: 浮點數
  - `%5d`: 固定列印五個字元，若數字不足五個字元，則在左側補上空格。若超過五個字元，則完整列印。
  - `%5s`: 與 `%5d` 類似，用於字串。
  - `%8.2f`: 固定列印八個字元 (包含小數點)，小數部分固定列印兩位。若整數部分不足指定位數，在左側補空格；若小數部分不足兩位，在右側補零。

**範例:**

```python
name = "yao"
age = 18
score = 95.5

print("Hello, %s!" % name)
print("Age: %d" % age)
print("Score: %.1f" % score)  # 輸出一位小數
print("Formatted integer: %5d" % age)
print("Formatted float: %8.2f" % score)
```

---

### 2. 變數 (Variables)

#### 變數基本操作

- 多重賦值 (Multiple Assignment):

  - 將相同的值賦予多個變數:
    ```python
    a = b = c = 20
    ```
  - 在同一行指定多個不同值的變數，以逗號 `,` 隔開:
    ```python
    age, name = 18, "yao"
    ```

- 刪除變數 (Deleting Variables):

  使用 `del` 關鍵字刪除不再需要的變數，以釋放記憶體空間。
  
  ```python
  # 刪除變數名稱為 header 的變數
  del header
  ```

#### 變數命名規則

- 由大小寫字母、數字和底線 `_` 組成。
- 不能以數字開頭。
- 名稱中間不能有空格。
- 變數名稱最好能清楚表達其含義。
- 若由多個單字組成，建議使用駝峰式命名法 (首單字小寫，後續單字首字母大寫，例如 `myVariableName`) 或底線分隔法 (例如 `my_variable_name`)。
- 變數名稱區分大小寫 (`myVar` 和 `myvar` 是不同的變數)。
- 避免使用特殊字元。
- 避免使用 Python 的保留關鍵字作為變數名稱。

##### Python 保留關鍵字 (Keywords)

以下是 Python 的保留關鍵字，不能作為變數或函數的名稱:

```python
# Python 關鍵字
True, False, None
as, is, in, or, def, for, try, not, class, elif, else,
from, pass, with, async, await, break, while, yield,
assert, except, global, import, lambda, return,
finally, continue, nonlocal
```

---

### 3. 資料型別 (Data Types)

#### 數值 (Numeric Types)

- 整數 (Integer - `int`): 不包含小數的數值。

  ```python
  num1 = 34
  ```

- 浮點數 (Floating-Point - `float`): 包含小數點的數值。

  ```python
  num2 = 10.23
  num3 = 24.0  # 整數也可以表示為浮點數型別
  ```

#### 布林值 (Boolean Type)

- 布林值 (Boolean - `bool`): 用於表示邏輯值，通常在條件運算中使用。只有兩個值: `True` 和 `False`。

  ```python
  is_active = True
  has_error = False
  ```

#### 字串 (String Type)

- 字串 (String - `str`): 由一對雙引號 `""` 或單引號 `''` 括起來的文字內容。

  ```python
  message1 = "這是一個字串"
  message2 = 'This is also a string.'
  ```

- 脫逸字元 (Escape Characters): 當字串中需要包含特殊字元 (如換行、引號等) 時，可以使用脫逸字元 `\`。

  - `\n`: 換行
  - `\t`: 定位字元 (Tab)
  - `\\`: 反斜線
  - `\'`: 單引號
  - `\"`: 雙引號

  ```python
  multiline_string = "第一行\n第二行"
  path = "C:\\Users\\Default"
  quote = '他說:\'你好！\''
  ```

#### 資料型別查詢與轉換

- 查詢資料型別 (`type()`): 使用 `type()` 函數查詢變數或值的資料型別
  ```python
  x = 10
  y = "Hello"
  print(type(x))  # <class 'int'>
  print(type(y))  # <class 'str'>
  ```

- 資料型別轉換 (Type Conversion):

  - 自動轉換 (Implicit Conversion): Python 會在某些情況下自動進行型別轉換

    ```python
    result1 = 5 + 7.6  # 結果為 12.6 (float)，整數自動轉為浮點數
    result2 = 5 + True  # 結果為 6 (int)，布林值 True 自動轉為數值 1
    # 在數值和布林值運算中，True 會被視為 1，False 會被視為 0。
    ```

  - 強制轉換 (Explicit Conversion): 當無法自動轉換或需要特定型別時，需使用型別轉換函數。

    - `int()`: 轉換為整數
    - `float()`: 轉換為浮點數
    - `str()`: 轉換為字串
    - `bool()`: 轉換為布林值

    ```python
    score = 90
    message = "你的成績是:" + str(score)  # 將整數 score 轉為字串
    print(message)
    
    value_str = "100"
    value_int = int(value_str)
    print(value_int + 50)  # 輸出 150
    ```

---

### 4. 運算式 (Expressions) 與運算子 (Operators)

運算式由運算元 (Operands) 和運算子 (Operators) 組成。

- 單元運算子 (Unary Operators): 只有一個運算元，位於運算元前方 (例如: `-100` 中的 `-`)。
- 二元運算子 (Binary Operators): 有兩個運算元，位於兩個運算元中間 (例如: `100 - 20` 中的 `-`).

#### 輸入函數 (`input()`)

`input()`函數用於從使用者獲取輸入資料，輸入的內容一律為字串型別。

```python
user_name = input("請輸入您的名字：")
age_str = input("請輸入您的年齡：")
age_int = int(age_str) # 需要轉換為整數才能進行數值運算
print("你好，" + user_name + "！你明年 " + str(age_int + 1) + " 歲。")
```

#### 算數運算子 (Arithmetic Operators)

| 運算子 | 功能             | 範例       | 結果 |
|--------|------------------|------------|------|
| +      | 加法             | 12 + 3     | 15   |
| -      | 減法             | 12 - 3     | 9    |
| *      | 乘法             | 12 * 3     | 36   |
| /      | 除法             | 32 / 5     | 6.4  |
| %      | 餘數             | 32 % 5     | 2    |
| //     | 商數             | 32 // 5    | 6    |
| **     | 次方             | 7 ** 2     | 49   |

#### 比較運算子 (Comparison Operators)

比較運算子的結果為布林值 (`True`或`False`)

| 運算子 | 意義     | 範例           | 結果   |
|--------|----------|----------------|--------|
| ==     | 相等     | 1 + 1 == 2     | True   |
| !=     | 不相等   | 20 != 19       | True   |
| >      | 大於     | 10 > 30        | False  |
| <      | 小於     | 20 < 10        | False  |
| >=     | 大於等於 | 100 >= 99      | True   |
| <=     | 小於等於 | 29 <= 30       | True   |

#### 邏輯運算子 (Logical Operators)

用於組合多個條件判斷

| 運算子 | 意義     | 範例                     | 結果   |
|--------|----------|--------------------------|--------|
| not    | 反向邏輯 | not(3 > 5)               | True   |
| and    | 且       | (3 < 4) and (9 < 6)      | False  |
| or     | 或       | (5 > 3) or (8 < 4)       | True   |

#### 複合指派運算子 (Compound Assignment Operators)

簡化變數更新的寫法

| 運算子 | 等效寫法       | 範例 (`i` 初始值為 5) | `i` 的結果 |
|------|-------------|-----------------------|------------|
| +=   | i = i + 3     | i += 3             | 8          |
| -=   | i = i - 3     | i -= 3             | 2          |
| *=   | i = i * 3     | i *= 3             | 15         |
| /=   | i = i / 3     | i /= 3             | 1.666...   |
| %=   | i = i % 3     | i %= 3             | 2          |
| //=  | i = i // 3    | i //=              | 1          |
| **=  | i = i ** 3    | i **= 3            | 125        |

---

### 條件判斷式 (Conditional Statements)

根據條件式的結果 (`True`或`False`) 來決定程式執行的流程。

#### 單向判斷式 (`if`)

如果條件成立，則執行 `if`區塊內的程式碼。

```python
password = input("請輸入密碼：")
if password == "0000":
    print("密碼正確！")
```

#### 雙向判斷式 (`if...else`)

如果條件成立，執行`if`區塊；否則，執行`else`區塊。

```python
password = input("請輸入密碼：")
if password == "0000":
    print("密碼正確！")
else:
    print("密碼錯誤！")
```

#### 多向判斷式 (`if...elif...else`)

依序檢查多個條件，執行第一個成立條件對應的區塊。如果所有`if`和`elif`條件都不成立，則執行`else`區塊。

```python
score_str = input("輸入成績：")
score = int(score_str)

if score >= 90:
    print("A+")
elif score >= 80:
    print("A")
elif score >= 70:
    print("B")
elif score >= 60:
    print("C")
else:
    print("F")
```

#### 巢狀判斷式 (Nested Conditionals)

在一個判斷式中再包含另一個判斷式。

```python
# 以百貨公司折扣為例：
# 滿一萬打八折，五千以上打八五折，三千以上打九折，一千以上九五折
money_str = input("輸入購入金額：")
money = int(money_str)
discounted_money = money

if money >= 1000:
    if money >= 10000:
        discounted_money = money * 0.8
        print("折扣後金額：%d 元" % discounted_money)
    elif money >= 5000:
        discounted_money = money * 0.85
        print("折扣後金額：%d 元" % discounted_money)
    elif money >= 3000:
        discounted_money = money * 0.9
        print("折扣後金額：%d 元" % discounted_money)
    else: # money >= 1000
        discounted_money = money * 0.95
        print("折扣後金額：%d 元" % discounted_money)
else:
    print("購入金額：%d 元 (未達折扣門檻)" % discounted_money)
```

---

### 5.串列 (List)

串列是一種有序、可變的資料集合，可以儲存不同資料型態的元素。類似於其他程式語言中的陣列 (Array)。

#### 建立串列

```python
# 串列名稱 = [元素0, 元素1, 元素2, ...]
list1 = [90, 20, 10, 30, 80, 100, 90, 60]
list2 = [90, "hello", True, 10.5, None] # 元素可以是不同型態
empty_list = [] # 空串列
```

#### 存取串列元素 (Indexing)

透過索引值 (index) 存取串列中的元素，索引從`0`開始。

```python
#       [90, "hello", True, 10.5, None]
# 索引    0      1       2      3      4
# 負索引  -5     -4      -3     -2     -1

print(list2[1])       # 顯示 "hello"
print(list2[-1])      # 顯示 None (最後一個元素)
# print(list2[9])     # 會報錯 (IndexError: list index out of range)
```

#### 巢狀串列 (Nested Lists)

串列中的元素也可以是另一個串列。

```python
user_data = [["joe", "1234"], ["mary", "5678"], ["david", "9876"]]

print(user_data[0])       # 顯示 ["joe", "1234"]
print(user_data[0][1])    # 顯示 "1234" (第一個子串列的第二個元素)
```

#### `range()`函數

`range()`函數用於產生一個整數序列，常與迴圈或轉換為串列一起使用。

- 一個參數`range(stop)`: 產生從`0`到`stop-1`的整數序列。

```python
r1 = range(8)
print(list(r1))  # 輸出: [0, 1, 2, 3, 4, 5, 6, 7]
```

- 兩個參數`range(start, stop)`: 產生從`start`到`stop-1`的整數序列。

```python
r2 = range(2, 10)
print(list(r2))  # 輸出: [2, 3, 4, 5, 6, 7, 8, 9]

r3 = range(-9, -2)
print(list(r3))  # 輸出: [-9, -8, -7, -6, -5, -4, -3]
```

- 三個參數 `range(start, stop, step)`: 產生從`start`到`stop-1`，間隔為`step`的整數序列。

```python
r4 = range(0, 10, 2)
print(list(r4))  # 輸出: [0, 2, 4, 6, 8]

r5 = range(10, 0, -2) # 間隔值也可以為負數
print(list(r5)) # 輸出: [10, 8, 6, 4, 2]
```

---

### 6.迴圈 (Loops)

#### `for`迴圈 (Definite Loop)

通常用於已知迴圈次數的情況，遍歷序列 (如串列、字串、range()`物件) 中的每個元素。

**語法**

```python
for 變數 in 可迭代物件:
    # 迴圈內的程式碼區塊
```

**範例**

計算 1 到 n 的整數和

```python
sum_val = 0
n_str = input("請輸入正整數 n：")
n = int(n_str)

for i in range(1, n + 1): # range(1, n+1) 產生 1, 2, ..., n
    sum_val += i
print("1 到 %d 的整數和是 %d" % (n, sum_val))
```

#### 巢狀`for`迴圈 (Nested for Loops)

在一個`for`迴圈內再包含另一個`for`迴圈。注意執行次數，過多的巢狀迴圈可能導致效能問題。

**範例**

九九乘法表

```python
for i in range(1, 10):      # 外層迴圈控制被乘數
    for j in range(1, 10):  # 內層迴圈控制乘數
        product = i * j
        print("%d * %d = %-2d   " % (i, j, product), end="") # %-2d 表示左對齊佔兩位
    print() # 每輪內層迴圈結束後換行
```

#### `break`和`continue`陳述句

- `break`: 強制結束目前所在的迴圈 (最內層迴圈)。

```python
print("break 範例:")
for i in range(1, 10):
    if i == 5:
        break  # 當 i 等于 5 時，跳出迴圈
    print(i, end=" , ") # 輸出: 1 , 2 , 3 , 4 ,
print("\n迴圈結束")
```

- `continue`: 立即結束本次迴圈的剩餘部分，並跳到下一次迴圈的開始。

```python
print("\ncontinue 範例:")
for i in range(1, 10):
    if i % 2 == 0: # 如果 i 是偶數
        continue   # 跳過本次迴圈的 print
    print(i, end=" , ") # 只會印出奇數: 1 , 3 , 5 , 7 , 9 ,
print("\n迴圈結束")
```

#### `for...else`迴圈

`for`迴圈可以搭配一個可選的`else`區塊。如果迴圈正常執行完畢 (即沒有被`break`中斷)，則會執行`else`區塊。

**範例**

判斷質數

```python
num_str = input("請輸入一個大於 1 的整數：")
num = int(num_str)

if num <= 1:
    print("%d 不是質數。" % num)
elif num == 2:
    print("2 是質數！")
else:
    is_prime = True # 先假設是質數
    for i in range(2, int(num**0.5) + 1): # 檢查到其平方根即可
        if (num % i == 0):
            print("%d 不是質數！(可被 %d 整除)" % (num, i))
            is_prime = False
            break # 找到因子，不是質數，跳出迴圈
    if is_prime: # 如果迴圈正常結束 (沒被 break)，代表沒找到因子
        print("%d 是質數！" % num)

# 使用 for...else 的版本
num_str_else = input("請輸入一個大於 1 的整數 (for...else 版本)：")
num_else = int(num_str_else)

if num_else <= 1:
    print("%d 不是質數。" % num_else)
elif num_else == 2:
    print("2 是質數！")
else:
    for i in range(2, int(num_else**0.5) + 1):
        if (num_else % i == 0):
            print("%d 不是質數！(可被 %d 整除)" % (num_else, i))
            break
    else: # 只有在 for 迴圈正常結束時執行 (沒有 break)
        print("%d 是質數！" % num_else)
```

#### while`迴圈 (Indefinite Loop)

通常用於迴圈次數不確定，依賴某個條件來決定是否繼續執行。

**語法**

```python
while 條件式:
    # 條件成立時執行的程式碼區塊
    # 通常需要在迴圈內更新條件，避免無限迴圈
```

**範例**

計算班級平均成績 (輸入 -1 結束)

```python
total_score = 0
student_count = 0
score_input_str = ""

print("輸入學生分數，輸入 -1 結束。")

while True: # 可以先用 True 建立無限迴圈，再用 break 跳出
    score_input_str = input("請輸入第 %d 位學生的成績：" % (student_count + 1))
    current_score = int(score_input_str)

    if current_score == -1:
        break # 輸入 -1，跳出迴圈

    if 0 <= current_score <= 100:
        total_score += current_score
        student_count += 1
    else:
        print("無效分數，請輸入 0-100 之間的分數。")

if student_count > 0:
    average_score = total_score / student_count
    print("\n班級總成績 %d 分，共 %d 位學生，平均成績： %.2f 分" % (total_score, student_count, average_score))
else:
    print("\n沒有輸入有效成績。")
```

---

### 7.進階串列操作 (Advanced List Operations)

| 操作方式                | 功能                     | 範例                        |
|-------------------------|--------------------------|-----------------------------|
| list * n                | 串列重複 n 次              | list2 = list1 * 2           |
| list[n1:n2]             | 取出索引範圍元素            | list2 = list1[1:4]          |
| list[n1:n2:n3]          | 取出範圍內間隔為 n3 元素     | list2 = list1[1:4:2]        |
| del list1[n1:n2]        | 刪除串列中部分元素          | del list1[1:4]               |
| len(list1)              | 串列長度                   | n = len(list1)              |
| min(list1), max(list1)  | 最小/最大元素              | n = min(list1)               |
| list1.index(n1)         | 元素索引值                 | list1.index(3)              |
| list1.count(n1)         | 元素出現次數               | list1.count(3)              |

_**注意**_
> `append()`和`insert()`用於增加串列元素。`append()`加在尾部，`insert()`可指定位置。

> `sort()`和`reverse()`是原地修改 (in-place)，直接改變原串列，不回傳新的串列。如果需要排序後的新串列而不改變原串列，可以使用`sorted()`函數。

---

### 8.元組 (Tuple)

元組與串列非常相似，都是有序的資料集合。最大的不同點在於：元組是不可變的 (immutable)，一旦建立後，其內容就不能被修改、新增或刪除。

#### 建立元組

使用小括號`()`或不使用括號 (以逗號分隔) 來建立元組。

```python
tuple1 = (10, 20, "hello")
tuple2 = 10, 20, "hello" # 效果同上
single_element_tuple = (10,) # 注意：單一元素的元組後面需要一個逗號
empty_tuple = ()
```

**元組的優勢**

- 速度: 通常比串列稍快，因為其不可變性。
- 安全性: 由於不可變，儲存在元組中的資料較為安全，不會被意外修改。
- 可作為字典的鍵 (Key): 串列是可變的，不能作為字典的鍵；而元組是不可變的，可以。


#### 元組與串列的互相轉換

- `list(tuple_object)`: 將元組轉換為串列。
- `tuple(list_object)`: 將串列轉換為元組。

```python
my_tuple = (1, 2, 3, 4, 5)
my_list = list(my_tuple)  # 轉換為串列
my_list.append(6)         # 串列可以修改
print(my_list)            # [1, 2, 3, 4, 5, 6]

new_tuple = tuple(my_list) # 再轉換回元組
print(new_tuple)          # (1, 2, 3, 4, 5, 6)
```

---

### 字典 (Dictionary)

字典是 Python 中以鍵值對形式儲存資料的資料結構，允許通過唯一的鍵快速存取、新增、修改和刪除資料。本指南整理了字典的特性、創建方式與常用操作，並補充了迭代、檢查鍵存在性等內容，確保格式統一且全面。

#### 字典的特性

- **鍵值對 (Key-Value Pairs)**：
  - 每個元素由一個唯一鍵 (key) 和其對應值 (value) 組成。
  - **鍵**：
    - 必須唯一，否則後續賦值會覆蓋原有值。
    - 必須是不可變資料型態 (immutable)，如字串 (string)、數字 (number)、元組 (tuple，僅限包含不可變元素)。
    - 不可用列表 (list) 或字典作為鍵。
  - **值**：
    - 可為任意 Python 資料型態，如數字、字串、列表、元組或其他字典。
    - 可重複。
- **可變性 (Mutable)**：字典可動態新增、修改或刪除鍵值對。
- **順序性 (Ordering)**：
  - Python 3.7+：字典保留插入順序，迭代時按插入順序返回項目。
  - Python 3.6 及以下：字典無序，迭代順序不可預測。
- **動態性 (Dynamic)**：字典可根據需要增長或縮小。

#### 創建字典

**1. 使用大括號 `{}` 和冒號 `:`**
```python
# 空字典
my_dict_empty = {}
print(f"空字典: {my_dict_empty}")  # 輸出: {}

# 包含鍵值對的字典
my_dict = {
    "name": "Alice",
    "age": 30,
    "city": "New York"
}
print(f"包含鍵值對的字典: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 30, 'city': 'New York'}
```

**2. 使用 `dict()` 建構函式**
- **從鍵值對串列 (list of tuples)**：
  ```python
  my_dict_from_list = dict([("name", "Bob"), ("age", 25)])
  print(f"從串列建立的字典: {my_dict_from_list}")  # 輸出: {'name': 'Bob', 'age': 25}
  ```
- **使用關鍵字參數 (鍵必須是有效 Python 識別字)**：
  ```python
  my_dict_from_kwargs = dict(name="Charlie", age=35, city="London")
  print(f"從關鍵字參數建立的字典: {my_dict_from_kwargs}")  # 輸出: {'name': 'Charlie', 'age': 35, 'city': 'London'}
  ```
- **從另一映射物件 (如字典)**：
  ```python
  original_dict = {"country": "USA", "language": "English"}
  my_dict_from_mapping = dict(original_dict)
  print(f"從映射物件建立的字典: {my_dict_from_mapping}")  # 輸出: {'country': 'USA', 'language': 'English'}
  ```

#### 字典操作

**1. 存取值 (Accessing Values)**
- **使用方括號 `[]`**：
  - 若鍵不存在，會引發 `KeyError`。
  ```python
  my_dict = {"name": "Alice", "age": 30}
  name_value = my_dict["name"]
  print(f"使用方括號存取 'name': {name_value}")  # 輸出: Alice
  # print(my_dict["gender"])  # 引發 KeyError
  ```
- **使用 `get()` 方法**：
  - 若鍵不存在，返回 `None` 或指定預設值。
  ```python
  my_dict = {"name": "Alice", "age": 30}
  age_value = my_dict.get("age")
  print(f"使用 get() 存取 'age': {age_value}")  # 輸出: 30
  gender_value = my_dict.get("gender")
  print(f"使用 get() 存取不存在的 'gender': {gender_value}")  # 輸出: None
  country_value = my_dict.get("country", "Unknown")
  print(f"使用 get() 存取不存在的 'country' 並提供預設值: {country_value}")  # 輸出: Unknown
  ```

**2. 新增或修改鍵值對**
- **使用方括號 `[]` 賦值**：
  - 鍵存在則更新值，不存在則新增鍵值對。
  ```python
  my_dict = {"name": "Alice", "age": 30}
  print(f"修改前的字典: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 30}
  my_dict["age"] = 31
  print(f"修改 'age' 後的字典: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 31}
  my_dict["city"] = "New York"
  print(f"新增 'city' 後的字典: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 31, 'city': 'New York'}
  ```
- **使用 `update()` 方法**：
  - 接受字典、鍵值對迭代器或關鍵字參數，批量更新或新增。
  ```python
  my_dict = {"name": "Alice", "age": 30}
  print(f"update() 前的字典: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 30}
  my_dict.update({"age": 32, "city": "Boston", "occupation": "Engineer"})
  print(f"使用字典 update() 後的字典: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 32, 'city': 'Boston', 'occupation': 'Engineer'}
  my_dict.update([("country", "USA"), ("language", "English")])
  print(f"使用串列 update() 後的字典: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 32, 'city': 'Boston', 'occupation': 'Engineer', 'country': 'USA', 'language': 'English'}
  my_dict.update(zip_code="10001", email="alice@example.com")
  print(f"使用關鍵字參數 update() 後的字典: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 32, 'city': 'Boston', 'occupation': 'Engineer', 'country': 'USA', 'language': 'English', 'zip_code': '10001', 'email': 'alice@example.com'}
  ```

**3. 刪除鍵值對**
- **使用 `del` 關鍵字**：
  - 若鍵不存在，引發 `KeyError`。
  ```python
  my_dict = {"name": "Alice", "age": 30, "city": "New York"}
  print(f"刪除前: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 30, 'city': 'New York'}
  del my_dict["city"]
  print(f"刪除 'city' 後: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 30}
  # del my_dict["country"]  # 引發 KeyError
  ```
- **使用 `pop()` 方法**：
  - 移除並返回鍵的值，若鍵不存在可返回預設值。
  ```python
  my_dict = {"name": "Alice", "age": 30, "city": "New York"}
  print(f"pop() 前: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 30, 'city': 'New York'}
  removed_value_age = my_dict.pop("age")
  print(f"pop('age') 後的字典: {my_dict}")  # 輸出: {'name': 'Alice', 'city': 'New York'}
  print(f"被移除的 'age' 的值: {removed_value_age}")  # 輸出: 30
  removed_value_country = my_dict.pop("country", "Not Found")
  print(f"pop('country') (不存在，有預設值) 後的字典: {my_dict}")  # 輸出: {'name': 'Alice', 'city': 'New York'}
  print(f"pop('country') 的返回值: {removed_value_country}")  # 輸出: Not Found
  ```
- **使用 `popitem()` 方法**：
  - 移除並返回最後插入的鍵值對 (Python 3.7+)，空字典引發 `KeyError`。
  ```python
  my_dict = {"name": "Alice", "age": 30, "city": "New York"}
  print(f"popitem() 前: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 30, 'city': 'New York'}
  removed_item = my_dict.popitem()
  print(f"popitem() 後的字典: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 30}
  print(f"被移除的鍵值對: {removed_item}")  # 輸出: ('city', 'New York')
  ```
- **使用 `clear()` 方法**：
  - 清空字典。
  ```python
  my_dict = {"name": "Alice", "age": 30, "city": "New York"}
  print(f"clear() 前: {my_dict}")  # 輸出: {'name': 'Alice', 'age': 30, 'city': 'New York'}
  my_dict.clear()
  print(f"clear() 後: {my_dict}")  # 輸出: {}
  ```

**4. 檢查鍵是否存在**
- **使用 `in` 運算子**：
  ```python
  my_dict = {"name": "Alice", "age": 30}
  print(f"'name' 是否在字典中: {'name' in my_dict}")  # 輸出: True
  print(f"'city' 是否在字典中: {'city' in my_dict}")  # 輸出: False
  ```

**5. 迭代字典**
- **迭代鍵**：
  ```python
  my_dict = {"name": "Alice", "age": 30, "city": "New York"}
  for key in my_dict:
      print(f"鍵: {key}")  # 輸出: name, age, city
  ```
- **迭代值**：
  ```python
  for value in my_dict.values():
      print(f"值: {value}")  # 輸出: Alice, 30, New York
  ```
- **迭代鍵值對**：
  ```python
  for key, value in my_dict.items():
      print(f"鍵: {key}, 值: {value}")  # 輸出: name: Alice, age: 30, city: New York
  ```

**6. 其他常用方法**
- **`len()`**：返回字典中鍵值對的數量。
  ```python
  my_dict = {"name": "Alice", "age": 30, "city": "New York"}
  print(f"字典長度: {len(my_dict)}")  # 輸出: 3
  ```
- **`keys()`**：返回所有鍵的視圖。
  ```python
  print(f"所有鍵: {my_dict.keys()}")  # 輸出: dict_keys(['name', 'age', 'city'])
  ```
- **`values()`**：返回所有值的視圖。
  ```python
  print(f"所有值: {my_dict.values()}")  # 輸出: dict_values(['Alice', 30, 'New York'])
  ```
- **`items()`**：返回所有鍵值對的視圖。
  ```python
  print(f"所有鍵值對: {my_dict.items()}")  # 輸出: dict_items([('name', 'Alice'), ('age', 30), ('city', 'New York')])
  ```

**注意事項**
- 鍵必須唯一且不可變，避免使用列表或字典作為鍵。
- 使用 `get()` 方法存取值可避免 `KeyError`。
- Python 3.7+ 保證字典插入順序，適用於依賴順序的應用。
- 批量操作建議使用 `update()`，效率高於逐一賦值。

---

### 10.函式 (Functions)

函式是將一段具有特定功能或經常需要重複使用的程式碼組織起來，並給予一個名稱。當需要執行這段程式碼時，只需呼叫其名稱即可。

**使用函式的好處**
- 模組化 (Modularity): 將大型專案分割成較小的、可管理的部分，有助於多人協作，縮短開發時間。
- 程式碼重用 (Code Reusability): 避免重複編寫相同的程式碼，縮短程式長度。開發類似功能時，只需稍作修改即可。
- 可讀性與維護性 (Readability & Maintainability): 使程式碼結構更清晰，更容易理解、除錯和維護。

#### 定義與呼叫函式

**定義函式語法:**

```python
def 函式名稱(參數1, 參數2, ...):
    # 函式內的程式碼區塊
    # ...
    return 回傳值  # 可選，若無 return 或只有 return，則回傳 None
```

**呼叫函式語法:**

```python
變數 = 函式名稱(引數1, 引數2, ...)
```

**範例**

計算矩形面積

```python
# 定義函式
def calculate_rectangle_area(width, height):
    area = width * height
    return area

# 呼叫函式
rect_width = 10
rect_height = 18
result_area = calculate_rectangle_area(rect_width, rect_height)
print(f"寬度 {rect_width}、高度 {rect_height} 的矩形面積為：{result_area}")
```

#### 參數預設值 (Default Parameter Values)

在定義函式時，可以為參數設定預設值。如果在呼叫函式時沒有提供該參數的引數，則會使用預設值。

```python
def greet(name, message="你好"): # message 參數有預設值
    print(f"{message}，{name}！")

greet("小明")               # 輸出: 你好，小明！ (使用 message 的預設值)
greet("小華", "早安")       # 輸出: 早安，小華！ (message 提供新值)

# 有預設值的參數必須放在沒有預設值的參數之後
# def getArea(width=10, height): # 這樣會報錯
#    area = width * height
#    return area

def get_power(base, exponent=2): # exponent 有預設值
    return base ** exponent

print(get_power(5))    # 輸出: 25 (5 的 2 次方)
print(get_power(5, 3)) # 輸出: 125 (5 的 3 次方)
```

#### 變數的有效範圍 (Scope)

變數的有效範圍指的是變數可以被存取的區域
- 全域變數 (Global Variables): 定義在所有函式之外的變數，其有效範圍是整個 Python 檔案。
- 區域變數 (Local Variables): 定義在函式內部的變數，其有效範圍僅限於該函式內部。

```python
global_var = 100 # 全域變數

def my_function():
    local_var = 10   # 區域變數
    print("函式內 - local_var:", local_var)
    print("函式內 - global_var:", global_var) # 可以讀取全域變數

my_function()
print("函式外 - global_var:", global_var)
# print("函式外 - local_var:", local_var) # 這行會報錯 (NameError)，因為 local_var 只在函式內有效
```

- `global`關鍵字: 如果想在函式內部修改全域變數的值，需要在函式內使用global`關鍵字宣告該變數。

```python
count = 0 # 全域變數

def increment_counter():
    global count # 宣告我們要使用的是全域變數 count
    count += 1
    print("函式內 count:", count)

increment_counter() # count 變成 1
increment_counter() # count 變成 2
print("函式外 count:", count) # 輸出: 2
```

> 如果在函式內賦值給一個與全域變數同名的變數，而沒有使用 global 宣告，Python 會將其視為一個新的區域變數。

```python
var1 = 10 # 全域變數
var2 = 20 # 全域變數

def scope_test():
    var1 = 1  # 這裡創建了一個新的區域變數 var1，不會影響全域的 var1
    global var2 # 這裡宣告要修改全域變數 var2
    var2 = 2
    print("函式內 - var1 (區域):", var1, "var2 (全域修改後):", var2)

scope_test()
# 輸出: 函式內 - var1 (區域): 1 var2 (全域修改後): 2

print("函式外 - var1 (全域):", var1, "var2 (全域):", var2)
# 輸出: 函式外 - var1 (全域): 10 var2 (全域): 2
```

#### 常用內建數值函式整理

| 函式         | 功能                 | 範例         | 結果  |
|--------------|----------------------|--------------|-------|
| `abs(x)`     | 取 x 的絕對值       | `abs(-5)`    | 5     |
| `chr(x)`     | 取得整數 x 的字元   | `chr(65)`    | A     |
| `divmod(x, y)` | 取得 x 除以 y 的商及餘數的元組 | `divmod(9x, y)` | (7, 2) |
| `len(x)`     | 取得元素個數       | `len([1, 3, 5, 7])` | 4   |
| `float(x)`   | 將 x 轉換成浮點數   | `float(56)`  | 56.0  |
| `int(x)`     | 將 x 轉換成整數     | `int(34.21)` | 34    |
| `hex(x)`     | 將 x 轉換成十六進位數字 | `hex(34)`    | 0x22  |
| `oct(x)`     | 將 x 轉換成八進位數字 | `oct(34)`    | 0o42  |
| `max(參數串列)` | 取得參數串列中的最大值 | `max(1, 3, 5, 7)` | 7   |
| `min(參數串列)` | 取得參數串列中的最小值 | `min(1, 3, 5, 7)` | 1   |
| `ord(x)`     | 回傳字元 x 的 Unicode 編碼值 | `ord("我")`  | 25105 |
| `pow(x, y)`  | 取得 x 的 y 次方     | `pow(2, 3)`  | 8     |
| `round(x)`   | 以四捨五入法取得 x 的近似值 | `round(45, 8)` | 46  |
| `sorted(串列)` | 由小到大排列         | `sorted([3, 7, 5, 1])` | [1, 3, 5, 7] |
| `str(x)`     | 將 x 轉換成字串     | `str(56)`    | 56 (字串) |
| `sum(x)`     | 計算串列元素的總和   | `sum([1, 3, 5, 7])` | 16  |


**`pow()`函式:**

- `pow(x, y)`: 計算x的y次方。
- `pow(x, y, z)`: 計算 (x 的 y 次方) 再對z取餘數，即`(x ** y) % z`。這在處理大數的模冪運算時更有效率。

**`round()`函式:**

- Python 3 中的`round()`對於`.5`的處理方式是「四捨六入五取偶」(round half to even)，即如果小數部分剛好是`.5`，則會取到最近的偶數。
  - `round(2.5)`結果是`2`
  - `round(3.5)`結果是`4`
- 可以指定第二個參數`ndigits`來控制保留的小數位數。

**`sorted()`函式:**

- `sorted()`會回傳一個新的已排序串列，原始的可迭代物件不會被修改。
- 可以透過`reverse=True`參數來進行降冪排序。

#### 常用字串函式 (String Methods)

字串是不可變的，所以字串的方法通常會回傳一個新的字串，而不會修改原始字串。

| 函式       | 功能描述                                      | 範例                              | 結果         |
|------------|----------------------------------------------|-----------------------------------|--------------|
| center(n)  | 將字串擴充為 n 個字元且居中                 | "book".center(8)                  | "  book  "   |
| find(s)    | 搜尋 s 字串在字串中的位置                   | "book".find("k")                  | 3            |
| len(字串)  | 取的字串長度                                 | len("book")                       | 4            |
| replace(s1, s2) | 將字串中的 s1 字串以 s2 字串取代        | "book".replace("o", "a")          | baak         |
| ljust(n)   | 將字串擴充為 n 個字元且居左                 | "book".ljust(8)                   | "book    "   |
| rjust(n)   | 將字串擴充為 n 個字元且居右                 | "book".rjust(8)                   | "    book"   |
| join(list) | 將串列中元素以 s 字串作為連接字元組成一個字串 | " #".join(["ab", "cd"])           | ab#cd        |
| split(s)   | 將字串以 s 字串為分隔符元分割為串列         | "ab#cd".split("#")                | ["ab", "cd"] |
| startswith(s) | 字串是否以 s 字串開頭                    | "abc".startswith("a")             | True         |
| endswith(s) | 字串是否以 s 字串結尾                    | "abc".endswith("c")               | True         |
| strip()    | 移除字串左右方的空白字元                   | " book ".strip()                  | "book"       |
| rstrip()   | 移除字串右方的空白字元                     | " book".rstrip()                  | " book"      |
| lstrip()   | 移除字串左方的空白字元                     | "book ".lstrip()                  | "book "      |
| isupper()  | 字串是否都是大寫字母                       | "yes".isupper()                   | False        |
| islower()  | 字串是否都是小寫字母                       | "Yes".islower()                   | False        |
| upper()    | 將字串字母都轉換為大寫字母                 | "Yes".upper()                     | YES          |
| lower()    | 將字串字母都轉換為小寫字母                 | "YES".lower()                     | yes          |

**`join()`函式:**

- 將一個可迭代物件 (如串列、元組，其元素必須是字串) 中的所有字串元素，用指定的「連接字串」串接起來，形成一個新的字串。

```python
word_list = ["this", "is", "a", "book"]
sentence1 = " ".join(word_list)  # 用空格連接
print(sentence1)               # 輸出: this is a book

sentence2 = "---".join(word_list) # 用 "---" 連接
print(sentence2)               # 輸出: this---is---a---book
```

**`split()`函式:**

- 將原始字串依照指定的「分隔字串」進行切割，回傳一個包含切割後子字串的串列。
- 如果「分隔字串」未提供，預設會以任何空白字元 (空格` `、換行`\n`、定位`\t`等) 作為分隔符，並且連續的空白字元會被視為單一分隔符。
- 可以指定「最大分割次數」，若指定，則最多只會分割這麼多次。

```python
text1 = "This is a book."
words1 = text1.split() # 預設以空白分割
print(words1)        # 輸出: ['This', 'is', 'a', 'book.']

text2 = "apple,banana,orange"
fruits = text2.split(',') # 以逗號分割
print(fruits)        # 輸出: ['apple', 'banana', 'orange']

text3 = "one two three four"
parts = text3.split(' ', 2) # 以空格分割，最多分割 2 次
print(parts)         # 輸出: ['one', 'two', 'three four']
```

---

### 11.模組 (Modules)

Python 的強大之處在於其豐富的標準庫以及大量的第三方模組，這些模組擴展了 Python 的功能。模組基本上是一個包含 Python 定義和陳述句的檔案。

#### 匯入模組 (Importing Modules)

有幾種方式可以匯入模組：

###### 1.`import 模組名稱`:
匯入整個模組。使用模組內的函式或變數時，需要透過`模組名稱.成員名稱`的方式。

```python
import math
print(math.pi)
print(math.sqrt(16))

import random
print(random.randint(1, 10)) # 產生 1 到 10 之間的隨機整數
```

###### 2.`from 模組名稱 import 成員名稱1, 成員名稱2, ...`:
從模組中只匯入指定的成員 (函式、變數、類別等)。可以直接使用成員名稱，無需加上模組名稱前綴。

```python
from math import pi, sqrt
print(pi)
print(sqrt(25))

from random import randint, choice
print(randint(10, 20))
my_list = ['apple', 'banana', 'cherry']
print(choice(my_list)) # 從串列中隨機選擇一個元素
```

###### 3.`from 模組名稱 import *`:
匯入模組中的所有公開成員 (不建議大量使用)。可以直接使用成員名稱。

- 優點: 使用方便，不用寫模組名稱。
- 缺點: 可能會導致名稱衝突 (如果不同模組中有相同名稱的成員，或者與你自訂的變數/函式同名)，降低程式碼的可讀性，不易追溯成員的來源。

```python
# 不太建議的用法，除非你很清楚模組內容且不會造成衝突
from math import *
print(pi)
print(sqrt(36))
```

###### 4.`import 模組名稱 as 別名`:
匯入整個模組，並給予一個較短或更易記的別名。

```python
import random as rd
print(rd.randint(100, 200))

import numpy as np # numpy 模組常用的別名
# (假設已安裝 numpy: pip install numpy)
arr = np.array([1, 2, 3])
print(arr)
```

###### 5.`from 模組名稱 import 成員名稱 as 別名`:
從模組匯入指定成員，並給予別名。

```python
from datetime import datetime as dt
now = dt.now()
print(now.strftime("%Y-%m-%d %H:%M:%S"))
```

---
