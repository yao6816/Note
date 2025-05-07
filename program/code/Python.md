---

---

---

- 輸出：
	end="" ：結束字元，預設後面是加 \n （換行）
	%d代表整數，%s代表字串，%f代表浮點數
	%5d：固定列印五個字元，少五個會在數字左邊補空格（大於五個字元會全部列印）
	%5s：同上意思
	%8.2f：固定列印八個字元（含小數點），小數固定列印兩位，如整數小於五位，在數字左方填入空格，如小數少於兩位，在數字右方填入零
---
- 變數:
	多個數如果有相同值：
	```python
		a = b = c = 20
	```
	在同一列指定多個變數，中間以「 , 」隔開：
	```python
		age, name = 18, "yao"
	```
	刪除不用的變數以節省記憶體：
	```python
		del header
	```
    變數的命名規則：
     
     ```python
		# python keyword 
		True
		None
		False
		
		as
		is
		in
		or
		def
		for
		try
		not 
		class # 因為 class 後面的詞會被認為是 class 的名稱會變色，所以標注起來 
		elif
		else
		from
		pass
		with
		async
		await
		break
		while
		yield
		assert
		except
		global
		import
		lambda
		return
		finally
		continue
		nonlocal
		```
		
