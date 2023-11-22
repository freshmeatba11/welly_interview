# Welly 面試題目
### 1. JavaScript: 字串反轉
答案：
```javascript
1 function reverseString(str = "") {
2   return str.split("").toReversed().join("");
3 };
```

***
### 2. JavaScript: 陣列過濾
問題：寫一個JavaScript函式，接受一個數字陣列，並返回該陣列中所有大於5的數字。

答案：
```javascript
1 function filterNumbersGreaterThanFive(numbers = []) {
2   return numbers.filter((number) => number > 5);
3 }
```
***
### 3. JavaScript: 重構
問題：重構這段程式碼並說明原因
```javascript
function formatName(firstName, lastName) {

let formattedName = '';

if (firstName) {

formattedName += firstName;

}

if (lastName) {

formattedName += ' ' + lastName;

}

return formattedName;

}
```
答案：
```javascript
1 function formatName(firstName = "", lastName = "") {
2   // 根據程式碼推測，需求應該是在有輸入的情況下返回合併的結果:
3   // 1.為變數加上預設值，防止非預期的錯誤
4   // 2.為了提升閱讀性，只需要使用 Template literals 簡化合併的過程，不需要多一個變數儲存結果
5   // 3.透過三元運算子也可以取代冗長的 if 判斷
6   return `${firstName ? firstName : ""}${lastName ? ` ${lastName}` : ""}`;
7 }
```
***
### 4. React: 條件渲染
問題：在React中，如何根據條件渲染兩種不同的內容？

答案：
```javascript
1 function ConditionalRendering({ isLoggedIn }) {
2   // 如果 isLoggedIn 為 boolean 且情況是有 return 東西或是 null 的話可以使用邏輯運算子
3   return isLoggedIn && <p>LoggedIn === true</p>;
4 }
```
```javascript
1 function ConditionalRendering({ isLoggedIn }) {
2   // 如果 isLoggedIn 為 boolean 的話可以直接應用三元運算子
3   return isLoggedIn ? <p>LoggedIn === true</p> : <p>LoggedIn === false</p>;
4 }
```
```javascript
1 function ConditionalRendering({ isLoggedIn }) {
2   // 如果 isLoggedIn 為 string 的話可以使用物件取值的方式
3   const option = {
4     true: <p>LoggedIn === `true`</p>,
5     false: <p>LoggedIn === `false`</p>,
6   };
7   return option[isLoggedIn];
8 }
```
***
### 5. React: 組件
問題：使用React創建一個簡單的計數器組件，具有增加和減少計數的按鈕。

答案：
```javascript
1 const Counter = () => {
2   const [count, setCount] = useState(0);
3   const plusCount = () => setCount((prev) => prev + 1);
4   const minusCount = () => setCount((prev) => prev - 1);
5   return (
6     <div>
7       <button onClick={plusCount}>+</button>
8       {count}
9       <button onClick={minusCount}>-</button>
10    </div>
11  );
12};
```
***
