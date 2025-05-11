# Python 學習筆記 (進階篇)

---

### 12.檔案系統 (File System)

- 先跳過，還沒讀

---

### 13.物件導向程式開發 (Object-Oriented Programming - OOP)

#### 類別 (Class) 與 物件 (Object)

- 類別 (Class): 是一個藍圖或模板，用於建立物件。類別定義了物件的共同屬性 (attributes) 和方法 (methods)。類別名稱的第一個字母建議使用大寫 (駝峰式命名法)。
- 物件 (Object): 是類別的實例 (instance)。每個物件都擁有類別所定義的屬性和方法。

#### 建立類別的語法:

```python
class 類別名稱:
    # 類別屬性 (Class Attributes) - 可選

    # 初始化方法 (Constructor) - __init__
    def __init__(self, 參數1, 參數2, ...):
        # 實例屬性 (Instance Attributes)
        self.屬性1 = 參數1
        self.屬性2 = 參數2
        # ...

    # 實例方法 (Instance Methods)
    def 方法名稱1(self, 其他參數...):
        # 方法的實作
        # 可以存取 self.屬性
        pass

    def 方法名稱2(self, 其他參數...):
        # ...
        pass

# 標準寫法，可以繼承自 object (Python 3 中預設如此)
class Num(object):
    pass

# 可以省略括號 (若沒有要繼承其他類別)
class Num:
    pass
```

- `self`參數: 在類別中定義方法時，第一個參數通常命名為`self`。它代表物件本身 (實例)。Python 會自動將物件實例傳遞給`self`參數，因此在呼叫物件的方法時不需要明確傳遞`self。
- 屬性 (Attributes): 代表物件的狀態或資料。
  - 類別屬性: 屬於類別本身，所有該類別的物件共享。
  - 實例屬性: 屬於每個物件實例，每個物件有自己的一份。通常在`__init__`方法中透過 `elf.屬性名 = 值`的方式定義。
- 方法 (Methods): 代表物件可以執行的動作或功能。它們是定義在類別中的函式。

**範例**

```python
class Dog:
    # 類別屬性
    species = "Canis familiaris"

    # 初始化方法
    def __init__(self, name, age):
        # 實例屬性
        self.name = name
        self.age = age

    # 實例方法
    def bark(self):
        return f"{self.name} says Woof!"

    def describe(self):
        return f"{self.name} is {self.age} years old."

# 建立物件 (實例化)
dog1 = Dog("Buddy", 3)
dog2 = Dog("Lucy", 5)

# 存取屬性
print(dog1.name)        # Buddy
print(dog2.age)         # 5
print(Dog.species)      # Canis familiaris (透過類別存取類別屬性)
print(dog1.species)     # Canis familiaris (也可以透過實例存取)

# 呼叫方法
print(dog1.bark())      # Buddy says Woof!
print(dog2.describe())  # Lucy is 5 years old.
```




