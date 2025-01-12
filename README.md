# junyiacademy_qa 蔡鎮宇

### 1. (A)請寫一個程式把裡面的字串反過來。


```python
def q1_a(str):
    return str[::-1]
```


```python
assert '123' == q1_a('321'), 'should be 123'
```

### 1.(B)請寫一個程式把裡面的字串,每個單字本身做反轉,但是單字的順序不變。


```python
def q1_b(str):
    return ' '.join([rev[::-1] for rev in str.split(' ')])
```


```python
assert 'abc    def' == q1_b('cba    fed'), 'abc def'
```

### 2. 請寫一個程式,Input 是一個數字,Output 是從 1 到這個數字,扣除掉所有 3 的倍數以及 5 的倍數,但是需要保留同時是 3 和 5 的倍數的總數字數。


```python
def q2(n):
    return n - (n//3 + n//5) + 2*(n//15)
```


```python
assert 9 == q2(15), 'should be 9'
```

### 3. 房間裡有三個袋子,一個只裝鉛筆,一個只裝原子筆,第三個有鉛筆也有原子筆。袋子是不透明的,單從袋子的外表上看不出任何差異,你不知道哪個袋子裝什麼。除了袋子上各貼了一個標示("鉛筆"、"原子筆"、"混和"),且標示都是錯的(e.g. 標示鉛筆的袋子可能是混和的或是只裝原子筆)。你只能選一個袋子,拿出裡面一支筆,看是鉛筆還是原子筆,然後你要推論出這三個袋子分別的情況。請列出你的作法,以及解釋為什麼這樣可以找到答案。

    我們可以分成兩種情況討論：

                | 真正狀況 	| 鉛筆   	| 原子筆 	| 混合   	|
                |----------	|--------	|--------	|--------	|
                | 貼法一   	| 原子筆 	| 混合   	| 鉛筆   	|
                | 貼法二   	| 混合   	| 鉛筆   	| 原子筆 	|
                
     我們選擇貼著混合的那一袋，只要拿出來是原子筆（貼法一），就代表貼著原子筆的那一袋是鉛筆，貼著鉛筆的那一袋是混合。
                                     鉛筆  （貼法二）         鉛筆         原子筆     遠子筆      混合。

### 4. 有三個人一起到迪士尼遊玩,中午肚子餓了,去餐廳點了一份現在最夯的冰雪奇緣雙人組,要價 900 元,付錢後,服務生發現今天套餐大特價,只要 750 元,因此服務生應該退還 150 元給這三個人,但是這位服務生一時鬼迷心竅,決定暗槓 60元,只退了 90 元給這三個遊客。那麼:三人各出 300 元 - 服務生還給他們一人 30 元 = 三人各出 270 元。270元 × 3 人+ 服務生私吞的 60 元 = 810 + 60 = 870 !? 怎麼不是 900 元呢?還有 30 元去哪了呢?請用敘述的方式,儘量清楚解釋問題出在哪裡。

    依照題目的講法：三人各出 300 元 - 服務生還給他們一人 30 元 = 三人各出 270 元
    我們可以分析這270元的組成： 270 = 250(商品原價/3) + 20(每個人被坑20元，三個人總共被坑60元)
    因此，被坑的60元已經包含在每個人付出的錢裡面了，如果要列出等式的話，應該是 900 = (250(原價) + 20(被坑的) + 30(退回來的)) * 3
    才是正確的寫法。

