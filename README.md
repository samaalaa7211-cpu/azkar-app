# azkar-app
تطبيق ازكار 
<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>أذكاري</title>

<style>
body {
  margin: 0;
  font-family: Arial;
  background: linear-gradient(#ff9a9e, #fad0c4);
  text-align: center;
  color: #333;
}

/* الصفحات */
.page {
  display: none;
  padding: 20px;
}

.active {
  display: block;
  animation: fade 0.5s;
}

@keyframes fade {
  from {opacity:0;}
  to {opacity:1;}
}

/* أزرار */
.btn {
  background: #ff6f91;
  color: white;
  padding: 15px;
  margin: 10px;
  border-radius: 15px;
  border: none;
  width: 80%;
  font-size: 18px;
}

/* سبحة */
.counter {
  font-size: 40px;
  margin: 20px;
  color: #ff3b6f;
}

.circle {
  width: 150px;
  height: 150px;
  background: #ff6f91;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
  color: white;
  font-size: 20px;
}

/* أزرار تحت */
.bottom {
  position: fixed;
  bottom: 20px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  padding: 0 20px;
}

.small-btn {
  background: #ff3b6f;
  color: white;
  border: none;
  padding: 10px;
  border-radius: 50%;
}
</style>

</head>

<body>

<!-- الصفحة الرئيسية -->
<div id="home" class="page active">
  <h2>🌸 أذكاري</h2>

  <button class="btn" onclick="go('azkar')">📿 أذكار</button>
  <button class="btn" onclick="go('tasbeeh')">🔢 تسبيح</button>
</div>

<!-- صفحة الأذكار -->
<div id="azkar" class="page">
  <h2>📿 الأذكار</h2>

  <button class="btn" onclick="go('morning')">🌅 أذكار الصباح</button>
  <button class="btn" onclick="go('evening')">🌙 أذكار المساء</button>
  <button class="btn" onclick="go('sleep')">😴 أذكار النوم</button>
  <button class="btn" onclick="go('prayer')">🕌 أذكار الصلاة</button>

  <button class="btn" onclick="go('home')">⬅ رجوع</button>
</div>

<!-- صفحات الأذكار -->
<div id="morning" class="page">
<h3>🌅 أذكار الصباح</h3>
<p>اللهم بك أصبحنا وبك أمسينا...</p>
<button class="btn" onclick="go('azkar')">رجوع</button>
</div>

<div id="evening" class="page">
<h3>🌙 أذكار المساء</h3>
<p>اللهم بك أمسينا وبك أصبحنا...</p>
<button class="btn" onclick="go('azkar')">رجوع</button>
</div>

<div id="sleep" class="page">
<h3>😴 أذكار النوم</h3>
<p>باسمك اللهم أموت وأحيا...</p>
<button class="btn" onclick="go('azkar')">رجوع</button>
</div>

<div id="prayer" class="page">
<h3>🕌 أذكار الصلاة</h3>
<p>أستغفر الله، أستغفر الله...</p>
<button class="btn" onclick="go('azkar')">رجوع</button>
</div>

<!-- صفحة التسبيح -->
<div id="tasbeeh" class="page">
<h2 id="zekrName">سبحان الله</h2>

<div class="circle" onclick="countTasbeeh()">
  تسبيح
</div>

<div class="counter" id="count">0</div>

<div class="bottom">
  <button class="small-btn" onclick="changeZekr()">🔄</button>
  <button class="small-btn" onclick="addCount()">➕</button>
</div>

<button class="btn" onclick="go('home')">⬅ رجوع</button>
</div>

<script>
let count = 0;
let azkar = [
"سبحان الله",
"الحمد لله",
"الله أكبر",
"لا إله إلا الله",
"سبحان الله وبحمده سبحان الله العظيم",
"ربي اهدني فيمن هديت"
];
let index = 0;

function go(page){
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.getElementById(page).classList.add('active');
}

function countTasbeeh(){
  count++;
  document.getElementById("count").innerText = count;
}

function addCount(){
  count += 10;
  document.getElementById("count").innerText = count;
}

function changeZekr(){
  index = (index + 1) % azkar.length;
  document.getElementById("zekrName").innerText = azkar[index];
}
</script>

</body>
</html>
