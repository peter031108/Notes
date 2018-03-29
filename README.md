# Notes
Learning notes

### JS：
  + 監聽鍵盤
    
  ```js
  window.addEventListener('keydown', e => {
    console.log(e.key);        // `A`
    console.log(e.keycode);    // 65
  })
  ```  
    
  - 播放聲音
    
  ```js
  const audio = document.querySelector("audio[data-key='65']");
  audio.currentTime = 0; // 設定當前播放時間歸零
  audio.play(); //  播放
  ```  
    
  - 新增/移除/切換 class

  ```js
  const container = document.querySelector('.container');
  container.classList.add('shrink');
  container.classList.remove('shrink');
  container.classList.toggle('shrink');
  //or e.target.classList
  ```  
    
  - 監聽轉場動畫結束
    
  ```js
  const xd = document.querySelector('.xd');
  // 監聽有 transition 效果的 properties
  xd.addEventListener('transitionend', e => {
    console.log(e.propertyName);
  })
  ```  
    
  - 動態改變 CSS 變數的值
    
  ```js
  const suffix = this.dataset.sizing || '';
  document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix);
  ```  
    
  - Spread Operator(...)：
    
  ```js
  //不確定的傳入參數值
  function sum(…numbers) {
    var result = 0;
    numbers.forEach(function (number) {
      result += number;
    });
    return result;
  }
  console.log(sum(1)); // 1
  console.log(sum(1, 2, 3, 4, 5)); // 15
    
  //打開矩陣
  var params = [ "hello", true, 7 ]
  var other = [ 1, 2, ...params ] // [ 1, 2, "hello", true, 7 ]
    
  //分開字串
  var str = "foo"
  var chars = [ ...str ] // [ "f", "o", "o" 
    
  // Rest Properties
  let { x, y, ...z } = { x: 1, y: 2, a: 3, b: 4 };
  x; // 1
  y; // 2
  z; // { a: 3, b: 4 }
    
  // Spread Properties
  let n = { x, y, ...z };
  n; // { x: 1, y: 2, a: 3, b: 4 }
  ```  
    
  - Array：
    
  ```js
  var arr = [1, 2, 3];
  # 累加
  var total = arr.reduce((accumlator, currentValue) => (accumlator + currentValue), initialValue);
  console.log(total); //6
  arr.forEach(element => console.log(element));
  //1
  //2
  //3
  var newArr = arr.map(element => element * 2);
  console.log(newArr); //[2, 4, 6]
  # forEach 回傳 undefined
  # map 回傳新矩陣
  ```  
         
### HTML：

 - Data attribute
    
  ```html
  <!-- HTML -->
  <div class="wow" data-magic="XD"></div>
  ```
    
  ```js
  //JS
  var wow = document.querySelector('.wow');    
  console.log(wow.dataset.magic); // XD
  ```

### Git：  

 - 與 remote Repo 使用 SSH 連線

 ```sh  
 $ ssh-keygen  
 將產生的 id_rsa.pub 裡的金鑰貼至 project -> setting -> SSH keys。  
 ```

### 百題斬：

 1. console.log 的值為？  

  ```js  
  var num = '9' * '9'; //81  
  ```

 2. 如何用 JS 實作「回上頁」功能  

  ```js  
  window.history.back();  
  ```
    
### CSS：

  * [em(參考所有外層) & rem(只參考最外層)](http://www.hexschool.com/2016/01/02/2016-08-08-em-vs-rem/)  
  
  * [display: flex](https://wcc723.github.io/css/2017/07/21/css-flex/)  
  
  ![flex](https://firebasestorage.googleapis.com/v0/b/casper-de5d5.appspot.com/o/images%2Fblog%2Falign-items.png?alt=media&token=8cba0693-c9bc-4bcd-8d92-0055efa1a83c)  
  
  * [transition-timing-function: cubic-bezier(x1, y1, x2, y2)](https://developer.mozilla.org/zh-TW/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)  
    
  ![cubic-bezier](https://developer.mozilla.org/@api/deki/files/5226/=transition-timing-function.png)  
  
  * [:root define variables(--\<name\>: \<value\>), "var(--\<name\>)" for using](https://developer.mozilla.org/en-US/docs/Web/CSS/:root)  
    
