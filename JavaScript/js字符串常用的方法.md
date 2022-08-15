## 1.includes

> 语法：includes（valueStr, [fromIndex] ）

> valueStr：搜索的[字符串]

> fromIndex：从当前字符串的哪个索引位置开始搜索，默认值为0

> 返回值：如果当前字符串包含搜索的字符串就返回true，否则返回false

```
const str = 'hello word'

str.includes('o')  // true

str.includes('e', 5)  // false
```



## 2.startsWith

> 语法：startsWith（valueStr, [ fromIndex ]）

> valueStr：要搜索的字符串

> fromIndex：从当前字符串的哪个索引位置开始搜索，默认值为0

> 返回值：如果当前字符串以搜索的字符串开头返回true否则返回false



```
const str = 'hello word'

str.startsWith('he')  // true

str.startsWith('he', 5)  // false

str.startsWith('wo', 6)  // true
```



## 3.endsWith

> 语法：str.endsWith（valueStr，[fromIndex]）

> valueStr：要搜索的字符串

> fromIndex：在当前的字符串中的哪个索引位置向前搜索，默认为str.length

> 返回值：当前字符串是否以要搜索的字符串结束，如果是返回true否则返回false

```
const str = 'hello word'

str.endsWith('rd')  // true

str.endsWith('lo', 5)  // true

str.endsWith('lo', 6)  // false
```



### 4.字符串大小写转换

> 字符串小写：**str.toLowerCase()**

>  字符串大写：**str.toUpperCase()**





### 5.复制字符串

```js
//使用repeat之后会将原来的字符串复制n次

let str="qwe"

let str2=srt.repeat(2)

console.log(str2) //qweqwe
```



## 6.字符串反转

**str.split('').reverse().join('')**
