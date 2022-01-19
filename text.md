#    這是測試用的
#     基本介紹

##    關注點分離

![](https://i.imgur.com/gji0Wk4.png)


生命週期 > 渲染 > 資料 > 印出文字

>資料是獨立的區塊，不會混用在渲染或生命週期裡面。

-- 

###    事件觸發

![](https://i.imgur.com/0eHe5s4.png)


按下按鈕 > 按鈕事件觸發 >　事件觸發更動資料內容 > 
事件觸發渲染畫面 > 將更新後的文字渲染到畫面上

--

###    MVVM

Vue 是透過 MVVM 的機制來處理關注點分離。
MVVM 的機制，會讓整個元件的結構更好管理。

MVVM 會透過資料繫節器把資料渲染到畫面，如果資料有任何改變的話，
**vue model** 會自動把資料綁定到畫面上。




![](https://i.imgur.com/SDfy5MJ.png)

>視圖是 HTML ，資料狀態是data

如果左邊的文字欄位，文字有更動的話，右邊資料狀態也會跟著變動，
相對的，如果資料狀態變動了，左邊文字也會跟著變動。

--

###    v-model 會綁定一個資料狀態
![](https://i.imgur.com/tQTTepK.png)

--

使用 vue 會透過 v-model 的機制，直接將資料綁定到畫面上，不需要寫渲染功能。

如果要在特定的時間點修改文字的話，可以使用生命週期將資料內容調整，
而調整後的內容也會直接更新畫面。

![](https://i.imgur.com/7nhiBcN.png)

--

*    事件觸發

當點擊按鈕觸發事件行為時，可以修改資料裡面的內容，當資料內容被調整之後一樣會透過 v-model 的機制直接修改畫面上的內容，

![](https://i.imgur.com/idgstoV.png)


#    指令語法全介紹

![](https://i.imgur.com/8I0sT7i.png)




---





##    chechbox 勾選顯示底色



![](https://i.imgur.com/bJYbUDU.gif)


![](https://i.imgur.com/HNvWeUs.jpg)


![](https://i.imgur.com/cvfqkkk.jpg)









---

##    checkbox 點名字也可以勾選功能

label 的 for 要對應到 checkbox 的 id，
兩者都是要對應相同唯一的值

不懂可參考：
指令語法全介紹｜操作畫面超容易 >>＞  HTML 屬性綁定 v-bind ( 5:45 )
![](https://i.imgur.com/MPvR8vp.jpg)


![](https://i.imgur.com/a3kjvp0.jpg)


![](https://i.imgur.com/T6jNV4o.gif)




---





## mount

使用 .mount 將元件掛在一個區塊

*    將元件掛在 app 中

![](https://i.imgur.com/GgXEYtJ.jpg)

--

![](https://i.imgur.com/3bGzhVB.jpg)



---


##    渲染

```htmlembedded=
const App = {
  name: 'Hexschool Component',
  data() {
    return {
      name: '小明',
      position: '早餐店',
      text: '小明在早餐店吃早餐',
      }
      rawHtml: '<p>小明在早餐店吃早餐</p>',
}}
```
###    v-text
```htmlembedded=
<p><span v-text='name'></span>在<span v-text='position'></span>吃早餐</p>
```

###    {{ }} (Mustache)
```htmlembedded=
  <p>{{ name }}在{{ position }}吃早餐</p>
```

>以上印出來結果都是 "小明在早餐店吃早餐"


###     v-html  
```htmlembedded=
  <div v-html='rawHtml'></div>
```
###    單次綁定 v-once

```htmlembedded=
  <p v-once>{{ name }}在{{ position }}吃早餐</p>
```

>使用此方法就不會被雙向綁定

###    v-model 

* 操作資料的同時，畫面上的內容也會跟著做變化。

--

*    樣板字面值
```htmlembedded=
樣板字面值： {{ `${name}在${position}吃早餐` }}
```
*    反轉字串
```htmlembedded=
{{text.split('').reverse().join('') }}
```
>餐早吃店餐早在明小
