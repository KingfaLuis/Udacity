# Break、Continue

有时候我们需要更精准地控制何时循环应该结束，或者跳过某个迭代。在这些情况下，我们使用关键字 `break` 和 `continue`，这两个关键字可以用于 `for` 和 `while` 循环。

- `break` 使循环终止
- `continue` 跳过循环的一次迭代

请观看视频并尝试下面的示例，看看这两个关键字的作用。



# 尝试一下！

你将在下面找到解决视频中的货物装载问题的两个方法。第一个方法是视频中提到的方法，当重量达到上限时，终止循环。但是，我们发现该方法存在多个问题。第二个方法通过修改条件语句并添加 `continue` 解决了这些问题。请运行下面的代码，看看结果如何，你可以随意实验该代码！

```
manifest = [("bananas", 15), ("mattresses", 24), ("dog kennels", 42), ("machine", 120), ("cheeses", 5)]

# the code breaks the loop when weight exceeds or reaches the limit
print("METHOD 1")
weight = 0
items = []
for cargo_name, cargo_weight in manifest:
    print("current weight: {}".format(weight))
    if weight >= 100:
        print("  breaking loop now!")
        break
    else:
        print("  adding {} ({})".format(cargo_name, cargo_weight))
        items.append(cargo_name)
        weight += cargo_weight

print("\nFinal Weight: {}".format(weight))
print("Final Items: {}".format(items))

# skips an iteration when adding an item would exceed the limit
# breaks the loop if weight is exactly the value of the limit
print("\nMETHOD 2")
weight = 0
items = []
for cargo_name, cargo_weight in manifest:
    print("current weight: {}".format(weight))
    if weight >= 100:
        print("  breaking from the loop now!")
        break
    elif weight + cargo_weight > 100:
        print("  skipping {} ({})".format(cargo_name, cargo_weight))
        continue
    else:
        print("  adding {} ({})".format(cargo_name, cargo_weight))
        items.append(cargo_name)
        weight += cargo_weight

print("\nFinal Weight: {}".format(weight))
print("Final Items: {}".format(items))
```

测试输出结果：

```
METHOD 1
current weight: 0
  adding bananas (15)
current weight: 15
  adding mattresses (24)
current weight: 39
  adding dog kennels (42)
current weight: 81
  adding machine (120)
current weight: 201
  breaking loop now!

Final Weight: 201
Final Items: ['bananas', 'mattresses', 'dog kennels', 'machine']

METHOD 2
current weight: 0
  adding bananas (15)
current weight: 15
  adding mattresses (24)
current weight: 39
  adding dog kennels (42)
current weight: 81
  skipping machine (120)
current weight: 81
  adding cheeses (5)

Final Weight: 86
Final Items: ['bananas', 'mattresses', 'dog kennels', 'cheeses']
```

# 练习：截断字符串

用 `break` 语句写一个循环，用于创建刚好长 140 个字符的字符串 `news_ticker`。你应该通过添加 `headlines` 列表中的新闻标题创建新闻提醒，在每个新闻标题之间插入空格。如果有必要的话，从中间截断最后一个新闻标题，使 `news_ticker` 刚好长 140 个字符。

注意，`break` 同时适用于 `for` 和 `while` 循环。使用你认为最合适的循环。考虑向代码中添加 `print` 语句以帮助你解决 bug。

```
# HINT: modify the headlines list to verify your loop works with different inputs
headlines = ["Local Bear Eaten by Man",
             "Legislature Announces New Laws",
             "Peasant Discovers Violence Inherent in System",
             "Cat Rescues Fireman Stuck in Tree",
             "Brave Knight Runs Away",
             "Papperbok Review: Totally Triffic"]

news_ticker = ""
# write your loop here
for i in range(len(headlines)):
    news_ticker += headlines[i] + " "
    if len(news_ticker) >= 140:
        news_ticker = news_ticker[:140]
        break

print(news_ticker)
```

```
Local Bear Eaten by Man Legislature Announces New Laws Peasant Discovers Violence Inherent in System Cat Rescues Fireman Stuck in Tree Brave
```



# 练习解决方案：截断字符串

你可以采用以下方式。

```
headlines = ["Local Bear Eaten by Man",
             "Legislature Announces New Laws",
             "Peasant Discovers Violence Inherent in System",
             "Cat Rescues Fireman Stuck in Tree",
             "Brave Knight Runs Away",
             "Papperbok Review: Totally Triffic"]

news_ticker = ""
for headline in headlines:
    news_ticker += headline + " "
    if len(news_ticker) >= 140:
        news_ticker = news_ticker[:140]
        break

print(news_ticker)
```

### 输出：

```
Local Bear Eaten by Man Legislature Announces New Laws Peasant Discovers Violence Inherent in System Cat Rescues Fireman Stuck in Tree Brave
```