
# Javascriptで時計を作成してみよう

## Javascriptのコードの部分はこちらを参照してください。

---

## スライド P.10
### まずは32行目に下記を入力してみよう

```javascript
const now = new Date();
let hour = now.getHours();
alert(hour); 
```

#### 今が13時の場合
![アラートの表示](./img/alert.png)

---

## スライド P.19
### 先程のコードに追記してみよう

```javascript
const time = document.querySelector('#time');

const now = new Date();
let hour = now.getHours();
// alert(hour); 
time.innerHTML = `${hour}:00:00`;

```
## 下記のような表示になります


![アラートの表示](./img/degital01.png)
#### 今が14時の場合
---

## スライド P.24
### コードを修正してみよう

```javascript
// alert(hour); 
let min = now.getMinutes();
let sec = now.getSeconds();

time.innerHTML = `${hour}:${min}:${sec}`;
```
## 下記のような表示になります


![アラートの表示](./img/degital02.png)
#### 今が14時13分43秒の場合

---

## スライド P.29
### コードを修正してみよう

```javascript
const clock = () => {
    const now = new Date();
    let hour = now.getHours();
    // alert(hour); 
    let min = now.getMinutes();
    let sec = now.getSeconds();

    time.innerHTML = `${hour}:${min}:${sec}`;
    requestAnimationFrame(clock);
}
clock();
```
### デジタル時計が動きだします  


---

## スライド P.32
### コードを修正してみよう

```javascript

time.innerHTML = `${`0${hour}`.slice(-2)}:${`0${min}`.slice(-2)}:${`0${sec}`.slice(-2)}`;

```
### 全て二桁表示になります

---

# アナログ時計の針を動かそう

## スライド P.33

```javascript

hourHand.style.transform = `rotate(30deg)`;

```
### 短針が30度傾きます


---

## スライド P.34
### ３つの針を好きな傾きに動かしてみよう  

```javascript

hourHand.style.transform = `rotate(30deg)`;
minHand.style.transform = `rotate(80deg)`;
secHand.style.transform = `rotate(240deg)`;

```
### ３つの針が別々に傾きます

---

---

## スライド P.36
### ３つの針を時刻に合わせて動かしてみよう  

```javascript

hourHand.style.transform = `rotate(${hour*30}deg)`;
minHand.style.transform = `rotate(${min*6}deg)`;
secHand.style.transform = `rotate(${sec*6}deg)`;

```
### ３つの針が別々に傾きます

---

## スライド P.3
### 短針を正確な位置に合わせよう  

```javascript

hourHand.style.transform = `rotate(${(hour+min/60)*30}deg)`;

```

---

