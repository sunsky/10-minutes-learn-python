# 10-minutes-learn-python
10分钟学会 python


---

```markdown
> 一份简洁、清晰、实用的 Python 入门速查手册，涵盖基础语法、数据结构、函数、类与常用技巧。

---

## 🐍 一、基础语法

### 1. 打印输出
```python
print("Hello, World!")
print(f"Name: {name}")  # f-string（Python 3.6+）
```

### 2. 变量定义（动态类型）
```python
x = 10          # int
y = 3.14        # float
name = "Alice"  # str
is_ok = True    # bool
```

> ✅ Python 是动态类型语言，变量无需声明类型。

### 3. 注释
```python
# 单行注释

"""
多行注释（字符串）
常用于函数或模块说明
"""
```

---

## 🧩 二、数据类型与结构

### 1. 数字与运算
```python
a = 5 + 3      # 8
b = 5 - 3      # 2
c = 5 * 3      # 15
d = 6 / 3      # 2.0（浮点除法）
e = 6 // 3     # 2（整除）
f = 5 % 2      # 1（取余）
g = 2 ** 3     # 8（幂运算）
```

### 2. 字符串（str）
```python
s = "hello"
s.upper()           # "HELLO"
s.lower()           # "hello"
s[0]                # 'h'
s[1:4]              # 'ell'（切片）
len(s)              # 5
s.replace("h", "H") # "Hello"
f"{s} world"        # "hello world"
```

### 3. 列表（List）—— 可变、有序
```python
lst = [1, 2, 3]
lst.append(4)       # [1,2,3,4]
lst[0] = 0          # 修改元素
lst[1:3]            # [2,3]（切片）
lst.pop()           # 移除并返回最后一个
for x in lst:       # 遍历
    print(x)
```

### 4. 元组（Tuple）—— 不可变、有序
```python
t = (1, 2, 3)
t[0]                # 1
# t[0] = 10         # ❌ 错误！不能修改
a, b, c = t         # 解包
```

### 5. 字典（Dict）—— 键值对（Hash Map）
```python
d = {"name": "Alice", "age": 25}
d["name"]            # "Alice"
d["city"] = "Beijing" # 添加键值对
for k, v in d.items():
    print(k, v)
```

### 6. 集合（Set）—— 无序、不重复
```python
s = {1, 2, 3}
s.add(4)
s.remove(1)
if 2 in s:           # 成员检测
    print("Yes")
```

---

## 🔁 三、控制流

### 1. 条件判断
```python
if x > 10:
    print("Big")
elif x == 10:
    print("Equal")
else:
    print("Small")
```

### 2. 循环
```python
# for 循环
for i in range(5):        # 0,1,2,3,4
    print(i)

for item in lst:
    print(item)

# while 循环
while x < 10:
    x += 1
```

### 3. 列表推导式（List Comprehension）
```python
squares = [x**2 for x in range(5)]
# 结果: [0, 1, 4, 9, 16]

evens = [x for x in range(10) if x % 2 == 0]
# 结果: [0, 2, 4, 6, 8]
```

> ✅ 推荐用于简单逻辑，提升代码简洁性。

---

## 📦 四、函数

### 1. 定义函数
```python
def greet(name="World"):
    return f"Hello, {name}!"

greet()        # "Hello, World!"
greet("Bob")   # "Hello, Bob!"
```

### 2. 默认参数与关键字参数
```python
def func(a, b=2, c=3):
    return a + b + c

func(1)           # 6
func(1, c=10)     # 13（跳过 b）
```

### 3. 可变参数
```python
def sum_all(*args):      # 接收任意位置参数 → tuple
    return sum(args)

def print_kvs(**kwargs): # 接收任意关键字参数 → dict
    for k, v in kwargs.items():
        print(f"{k}: {v}")
```

---

## 🏗️ 五、类与面向对象

### 1. 定义类
```python
class Person:
    def __init__(self, name, age):  # 构造函数
        self.name = name
        self.age = age

    def introduce(self):
        print(f"I'm {self.name}, {self.age} years old.")

# 使用
p = Person("Alice", 25)
p.introduce()
```

### 2. 继承
```python
class Student(Person):
    def __init__(self, name, age, grade):
        super().__init__(name, age)
        self.grade = grade

    def introduce(self):
        super().introduce()
        print(f"Grade: {self.grade}")
```

---

## ⚙️ 六、常用内置函数

| 函数 | 说明 |
|------|------|
| `len(obj)` | 返回长度 |
| `type(obj)` | 返回类型 |
| `str()`, `int()`, `float()` | 类型转换 |
| `range(5)` | 生成 0~4 的序列 |
| `enumerate(lst)` | 带索引遍历 |
| `zip(a, b)` | 合并两个序列 |
| `map(func, lst)` | 映射 |
| `filter(cond, lst)` | 过滤 |
| `sorted(lst)` | 排序（返回新列表） |
| `sum(lst)` | 求和 |

**示例：**
```python
list(map(lambda x: x*2, [1,2,3]))   # [2,4,6]
list(filter(lambda x: x>2, [1,2,3])) # [3]
```

---

## 🔐 七、异常处理

```python
try:
    result = 10 / 0
except ZeroDivisionError:
    print("不能除以零")
except Exception as e:
    print(f"错误: {e}")
else:
    print("无异常时执行")
finally:
    print("总是执行")
```

---

## 💡 八、实用技巧

### 1. 解包（Unpacking）
```python
a, b = 1, 2
x, y, z = [1, 2, 3]

# 忽略某些值
_, _, z = [1, 2, 3]
```

### 2. 三元表达式
```python
result = "Yes" if x > 0 else "No"
```

### 3. `with` 上下文管理（自动资源释放）
```python
with open("file.txt", "r") as f:
    content = f.read()
# 文件自动关闭
```

### 4. `__name__ == "__main__"` 模块保护
```python
if __name__ == "__main__":
    print("程序入口")
```

> ✅ 保证脚本可导入又可独立运行。

---

## 📚 九、常用模块导入

```python
import math
math.sqrt(4)

from datetime import datetime
now = datetime.now()

import requests  # 需 pip install requests
response = requests.get("https://httpbin.org/get")
```

---

## ✅ 附录：Python 核心特点

| 特性 | 说明 |
|------|------|
| 语法简洁 | 缩进代替大括号，代码可读性强 |
| 动态类型 | 不需声明变量类型 |
| 高级数据结构 | list、dict、set 内置 |
| 支持函数式编程 | lambda、map、filter |
| 面向对象 | 类、继承、多态 |
| 丰富的标准库 | 开箱即用 |

---

> 🚀 **学习建议**：
> - 多写代码，动手实践
> - 使用 `print()` 调试
> - 学会查官方文档：[https://docs.python.org/zh-cn/3/](https://docs.python.org/zh-cn/3/)

---

📝 **本教程持续更新中，欢迎收藏、分享！**
```
